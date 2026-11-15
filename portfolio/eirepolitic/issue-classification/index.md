---
layout: case-study
title: Classifying Parliamentary Speeches Without Reprocessing Everything
permalink: /portfolio/eirepolitic/issue-classification/
presentation: editorial
kicker: Eirepolitic deep dive
summary: The mechanics behind deterministic label reuse, safe legacy migration, bounded model inference, and candidate validation.
---

<a class="deep-dive-back" href="{{ '/portfolio/eirepolitic/' | relative_url }}">← Back to the Eirepolitic flagship case study</a>

<section class="deep-dive-intro">
  <p class="editorial-kicker">What this page adds</p>
  <h2>The interesting part is not the taxonomy. It is deciding when classification should happen at all.</h2>
  <p>The flagship explains the high-level rule: reuse and deterministic handling come before model inference. This page focuses on the implementation mechanics behind that decision—how unchanged rows are identified, how historical labels are migrated safely, how model calls are constrained, and how candidate outputs are prevented from silently becoming production data.</p>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">1 · Reuse contract</p>
    <h2>An old label is reusable only if the speech itself is still the same.</h2>
  </div>
  <div class="deep-dive-two-column">
    <div>
      <p>The classifier compares both the stable <code>speech_id</code> and a hash of the current speech text. A matching ID is not enough: if the text changed, the previous classification is treated as stale.</p>
      <p>This makes reuse explicit rather than accidental. The classifier can preserve trustworthy historical work without assuming that row identity guarantees unchanged content.</p>
    </div>
    <div class="deep-dive-rule-list">
      <div><strong>Same ID + same text hash</strong><span>Reuse the existing unified label.</span></div>
      <div><strong>Same ID + changed text</strong><span>Do not inherit the old label.</span></div>
      <div><strong>No current label</strong><span>Attempt safe historical migration before inference.</span></div>
    </div>
  </div>
</section>

<section class="deep-dive-visual-pair" aria-label="Suggested issue-classification visuals">
  <div class="deep-dive-visual-placeholder">
    <span class="deep-dive-visual-number">Visual 01</span>
    <strong>Classification decision-path diagram</strong>
    <p>Show a single speech moving through: unchanged reuse → unique legacy match → short-text rule → bounded model inference → candidate validation.</p>
    <small>Best source: purpose-built diagram using the actual classifier decision order. Highlight model inference as the final branch rather than the centre of the system.</small>
  </div>
  <div class="deep-dive-visual-placeholder">
    <span class="deep-dive-visual-number">Visual 02</span>
    <strong>Readiness / migration coverage screenshot</strong>
    <p>Capture a real classifier readiness or dry-run output showing reused, migrated, pending and failed counts before model execution.</p>
    <small>Best source: terminal output, GitHub Actions summary, or generated readiness report from the classifier workflow.</small>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">2 · Historical migration</p>
    <h2>Legacy labels move forward only when identity can be proven.</h2>
  </div>
  <div class="deep-dive-two-column">
    <div>
      <p>The previous dataset used different identifiers, so migration cannot rely on row position or an old speech ID. The preferred match combines debate date, speech order, speaker name and exact speech-text hash.</p>
      <p>A second path is allowed only where debate date plus the exact text hash uniquely identifies one historical speech. Ambiguous matches remain unresolved and move on through the decision process.</p>
    </div>
    <div class="deep-dive-emphasis">
      <span>Migration principle</span>
      <strong>Ambiguity is a reason to classify again—not a reason to guess.</strong>
    </div>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">3 · Bounded inference</p>
    <h2>The model chooses from a schema; it does not create one.</h2>
  </div>
  <div class="deep-dive-two-column">
    <div>
      <p>Only unresolved speeches reach model inference. The response is structured JSON and <code>issue_label</code> is constrained to the approved 25-category taxonomy. The prompt explicitly excludes party position, sentiment, intent and importance.</p>
      <p>Very short speeches are handled deterministically as <code>NONE</code>, so low-information rows do not consume inference simply because they exist.</p>
    </div>
    <div class="taxonomy-sample" aria-label="Examples from the issue taxonomy">
      <span>Health</span><span>Housing</span><span>Education</span><span>Environment</span><span>Macroeconomics</span><span>International Affairs</span><span>Government Operations</span><span>NONE</span>
    </div>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">4 · Candidate safety</p>
    <h2>Testing classification and changing production are separate actions.</h2>
  </div>
  <div class="deep-dive-sequence">
    <div><span>01</span><strong>Readiness</strong><small>Measure reuse, migration and pending work. No model calls or writes.</small></div>
    <div><span>02</span><strong>Dry run</strong><small>Build the complete decision plan without mutation.</small></div>
    <div><span>03</span><strong>Capped classification</strong><small>Classify a review sample without production writes.</small></div>
    <div><span>04</span><strong>Candidate run</strong><small>Write completed results only into an active candidate batch.</small></div>
    <div><span>05</span><strong>Validation</strong><small>Require zero pending and zero failed rows before the candidate can pass.</small></div>
  </div>
  <p>The classifier itself cannot promote a candidate. That keeps model-driven enrichment inside the same promotion boundary as the rest of the pipeline.</p>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">Recorded provenance</p>
    <h2>Every label carries enough metadata to explain how it got there.</h2>
  </div>
  <div class="deep-dive-field-list">
    <div><strong>speech_id</strong><span>Stable row identity</span></div>
    <div><strong>source_speech_text_hash</strong><span>Detect changed source text</span></div>
    <div><strong>issue_label</strong><span>Controlled taxonomy value</span></div>
    <div><strong>issue_label_source</strong><span>Reuse, migration, rule or model</span></div>
    <div><strong>model_name</strong><span>Recorded where inference was used</span></div>
    <div><strong>classification_status</strong><span>classified · none · skipped · pending · failed</span></div>
  </div>
</section>

<section class="case-study-section technical-links-section">
  <p class="editorial-kicker">Implementation detail</p>
  <h2>Canonical technical sources</h2>
  <div class="technical-link-grid">
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/oireachtas_speech_issue_classifier_v2.md"><strong>Classifier v2 design</strong><span>Reuse order, safety controls, workflows and required test sequence</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/process/oireachtas_speech_issue_classifier.py"><strong>Classifier implementation</strong><span>Python implementation of migration, classification, validation and candidate writes</span></a>
  </div>
  <a class="deep-dive-return" href="{{ '/portfolio/eirepolitic/' | relative_url }}">Return to the Eirepolitic flagship →</a>
</section>
