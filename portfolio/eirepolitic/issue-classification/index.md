---
layout: case-study
title: Classifying Parliamentary Speeches Without Reprocessing Everything
permalink: /portfolio/eirepolitic/issue-classification/
presentation: editorial
kicker: Eirepolitic deep dive
summary: A controlled speech-classification workflow that reuses trustworthy historical labels, detects changed text, limits model calls, and keeps new classifications behind candidate validation.
tags:
  - Data Engineering
  - Classification
  - Validation
---

<section class="case-study-section case-study-two-column">
  <div>
    <p class="editorial-kicker">The problem</p>
    <h2>The data pipeline had moved on. The classifier had not.</h2>
  </div>
  <div>
    <p>The original speech classifier was built against an older debate dataset. When the wider Oireachtas pipeline was redesigned around the unified data model, parliamentary speeches continued to refresh correctly—but issue labels could remain frozen because the old classifier was still reading a stale source path.</p>
    <p>Simply rerunning every historical speech through a model would have been expensive, slow, and unnecessary. More importantly, it would have thrown away years of usable classifications without proving that the replacement labels were any better.</p>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">The design</p>
  <h2>Reuse what can be proven, classify only what is genuinely new.</h2>
  <div class="classification-flow" role="img" aria-label="Speech classification decision flow">
    <div><strong>Current speech</strong><span>Unified silver dataset</span></div>
    <b>→</b>
    <div><strong>Same speech ID + same text hash?</strong><span>Reuse unified label</span></div>
    <b>→</b>
    <div><strong>Safe historical match?</strong><span>Migrate legacy label</span></div>
    <b>→</b>
    <div><strong>Under 20 words?</strong><span>Assign NONE by rule</span></div>
    <b>→</b>
    <div><strong>Anything left</strong><span>Model classification</span></div>
  </div>
</section>

<section class="case-study-section case-study-two-column">
  <div>
    <p class="editorial-kicker">1 · Stable reuse</p>
    <h2>Existing labels survive only when the underlying speech is unchanged.</h2>
  </div>
  <div>
    <p>For speeches already present in the unified enrichment table, the classifier compares both the stable <code>speech_id</code> and a hash of the source speech text. If both still match, the existing issue label can be reused without contacting the model.</p>
    <p>If the speech text has changed, the old label is not trusted automatically. That prevents a corrected or reprocessed source record from inheriting a classification that was made against different text.</p>
  </div>
</section>

<section class="case-study-section case-study-two-column">
  <div>
    <p class="editorial-kicker">2 · Historical migration</p>
    <h2>Legacy labels are migrated by evidence, not row position.</h2>
  </div>
  <div>
    <p>The legacy dataset used different identifiers, so migration cannot safely rely on an old speech ID or on the row happening to appear in the same position.</p>
    <p>The new workflow first looks for an exact match using debate date, speech order, speaker name and speech-text hash. A second migration path is allowed only where debate date plus the exact text hash uniquely identify one historical speech. Ambiguous matches are deliberately left unresolved.</p>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">3 · Cost control</p>
  <h2>Rules and reuse come before model inference.</h2>
  <div class="cost-control-grid">
    <div><strong>Reuse</strong><span>Unchanged unified labels require no model call.</span></div>
    <div><strong>Migrate</strong><span>Safely matched historical labels require no model call.</span></div>
    <div><strong>Short text</strong><span>Speeches below 20 words are assigned <code>NONE</code> by rule.</span></div>
    <div><strong>Classify</strong><span>Only remaining pending speeches are sent to the model.</span></div>
  </div>
  <p>This is a useful pattern beyond this project: expensive inference should be the final step in a deterministic decision process, not the first response to every row.</p>
</section>

<section class="case-study-section case-study-two-column">
  <div>
    <p class="editorial-kicker">4 · Bounded model output</p>
    <h2>The model is allowed to choose a label—not invent the schema.</h2>
  </div>
  <div>
    <p>When model classification is required, the speech is assigned exactly one label from a fixed 25-category taxonomy. The classifier uses structured JSON output, and the schema itself constrains <code>issue_label</code> to the approved list.</p>
    <p>The prompt also explicitly tells the model not to infer party position, intent, sentiment, or importance. Its job is deliberately narrow: identify the single core policy topic, or return <code>NONE</code> where there is no sufficiently clear topic.</p>
    <div class="taxonomy-sample" aria-label="Examples from the issue taxonomy">
      <span>Health</span><span>Housing</span><span>Education</span><span>Environment</span><span>Macroeconomics</span><span>International Affairs</span><span>Government Operations</span><span>NONE</span>
    </div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">5 · Production safety</p>
  <h2>Testing a classifier is separate from changing production data.</h2>
  <div class="safety-mode-grid">
    <div><strong>Readiness</strong><span>Inventory migration coverage and pending work. No model calls. No writes.</span></div>
    <div><strong>Dry run</strong><span>Build the full reuse/migration plan. No model calls. No writes.</span></div>
    <div><strong>Capped classification</strong><span>Classify a small review sample. Cannot write to S3.</span></div>
    <div><strong>Full candidate run</strong><span>Classify all remaining rows and write only into an active candidate batch.</span></div>
    <div><strong>Validation</strong><span>Require zero pending and zero failed rows before a complete write can pass.</span></div>
    <div><strong>Promotion</strong><span>The classifier itself cannot promote a candidate into production.</span></div>
  </div>
</section>

<section class="case-study-section case-study-two-column">
  <div>
    <p class="editorial-kicker">Why that matters</p>
    <h2>A model-driven enrichment should fail safely.</h2>
  </div>
  <div>
    <p>The classification step is deliberately integrated into the same candidate-build model as the rest of the Oireachtas pipeline. That means I can inspect readiness, review a small live sample, run a larger non-writing test, build a complete historical candidate, and validate downstream consumers before deciding whether anything should be promoted.</p>
    <p>The scheduled refresh integration also exists but remains disabled by default until those quality gates are passed. In other words, implementation and production enablement are separate decisions.</p>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">Implementation pattern</p>
  <h2>The classifier records why every row has the label it has.</h2>
  <div class="classifier-record-grid">
    <div><strong>speech_id</strong><span>Stable row identity</span></div>
    <div><strong>source_speech_text_hash</strong><span>Detect changed source text</span></div>
    <div><strong>issue_label</strong><span>Controlled taxonomy value</span></div>
    <div><strong>issue_label_source</strong><span>Reuse, migration, rule or model</span></div>
    <div><strong>model_name</strong><span>Recorded where model inference was used</span></div>
    <div><strong>classification_status</strong><span>classified · none · skipped · pending · failed</span></div>
  </div>
</section>

<section class="case-study-section case-study-two-column">
  <div>
    <p class="editorial-kicker">Current state</p>
    <h2>Implemented and integrated, with historical backfill still gated.</h2>
  </div>
  <div>
    <p>The unified classifier code and workflow are implemented and wired into the candidate pipeline. The remaining work is operational validation: measure migration coverage, review live model samples, run a complete candidate backfill, validate downstream consumers, and only then enable classification in the scheduled production refresh.</p>
    <p>I prefer showing that distinction explicitly rather than presenting “code complete” as equivalent to “fully enabled in production.”</p>
  </div>
</section>

<section class="case-study-section technical-links-section">
  <p class="editorial-kicker">Go deeper</p>
  <h2>Canonical technical documentation</h2>
  <div class="technical-link-grid">
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/oireachtas_speech_issue_classifier_v2.md"><strong>Classifier v2 design</strong><span>Reuse order, safety controls, workflows and required test sequence</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/process/oireachtas_speech_issue_classifier.py"><strong>Classifier implementation</strong><span>Python implementation of migration, classification, validation and candidate writes</span></a>
    <a href="{{ '/portfolio/eirepolitic/' | relative_url }}"><strong>Back to Eirepolitic</strong><span>Return to the end-to-end project case study</span></a>
  </div>
</section>
