---
layout: case-study
title: Eirepolitic Data Pipeline
permalink: /portfolio/eirepolitic/
presentation: editorial
kicker: Featured project
summary: An end-to-end political data, analysis and automated publishing platform.
---

<section class="ep-opening">
  <div class="ep-opening-copy">
    <p class="editorial-kicker">The system</p>
    <h2>From public political data to reviewed, scheduled content.</h2>
    <p>I built Eirepolitic as one connected system rather than a collection of isolated scripts. It collects political data, validates and restructures it into a stable model, enriches it, calculates reusable metrics, turns selected outputs into visual content, and can publish approved content automatically.</p>
  </div>
  <a class="ep-system-visual" href="{{ '/assets/images/portfolio/eirepolitic-homepage-flow.png' | relative_url }}">
    <img src="{{ '/assets/images/portfolio/eirepolitic-homepage-flow.png' | relative_url }}" alt="Eirepolitic end-to-end political data, analysis and publishing system flow" />
    <span>View full system flow ↗</span>
  </a>
</section>

<section class="ep-outcome-strip">
  <div class="ep-outcome-copy">
    <p class="editorial-kicker">The outcome</p>
    <h2>One pipeline, visible all the way to the public result.</h2>
    <p>The technical work is designed to stay traceable from source records through to the content that a reader eventually sees. The representative output shown here is not a separate design exercise: it is the end of the same governed workflow that starts with source data.</p>
    <p>The source record, historical context, analytical definition, rendered asset and approval state all remain connected. That traceability is what makes the public-facing result useful as evidence of the underlying engineering rather than just a finished graphic.</p>
  </div>
  <a class="ep-outcome-proof" href="{{ '/assets/images/portfolio/eirepolitic-project-card.png' | relative_url }}">
    <img src="{{ '/assets/images/portfolio/eirepolitic-project-card.png' | relative_url }}" alt="Representative Eirepolitic visual output" />
    <span>Representative public output produced from the governed pipeline ↗</span>
  </a>
</section>

<section class="ep-story-split ep-story-intro">
  <div>
    <p class="editorial-kicker">Why I built it</p>
    <h2>A reliable layer between raw political records and public-facing analysis.</h2>
  </div>
  <div class="ep-prose">
    <p>Irish parliamentary data is rich, but the useful information is spread across different record types, historical relationships and source structures. A public chart or post may look simple, but producing it responsibly means knowing which source record it came from, which political context applied on that date, what denominator was used, and whether the result is safe to compare.</p>
    <p>The pipeline makes those decisions explicit and repeatable so downstream analysis and content do not need to reinvent them.</p>
  </div>
</section>

<section class="ep-stage ep-stage-sources">
  <div class="ep-source-layout">
    <div class="ep-source-copy">
      <div class="ep-stage-heading">
        <p class="editorial-kicker">01–02 · Sources &amp; ingestion</p>
        <h2>Start with traceable data, then validate it before use.</h2>
        <p>The main parliamentary source is Oireachtas data, covering members, debates, speeches, divisions, legislation and parliamentary questions. Separate ingestion work supports polling data, including the Irish Polling Indicator source.</p>
      </div>
      <div class="ep-process-list" aria-label="Source ingestion process">
        <div><span>01</span><strong>Acquire</strong><p>APIs and source datasets are captured with version and provenance information.</p></div>
        <div><span>02</span><strong>Validate</strong><p>Schemas, keys, dates, duplicate conditions and historical ranges are checked before promotion.</p></div>
        <div><span>03</span><strong>Candidate build</strong><p>New data versions can be tested before becoming the promoted production view.</p></div>
      </div>
      <div class="ep-context-note">
        <span>Tools in context</span>
        <strong>APIs · Python · GitHub Actions · source hashes · manifests · candidate validation</strong>
      </div>
    </div>
    <a class="ep-image-evidence ep-source-proof" href="{{ '/assets/images/portfolio/eirepolitic-metrics-example.png' | relative_url }}">
      <img src="{{ '/assets/images/portfolio/eirepolitic-metrics-example.png' | relative_url }}" alt="Example polling output generated from an ingested polling source" loading="lazy" />
      <span>Polling is a separate source stream. This six-month polling view is an example of a downstream visual built from that independently ingested source. View full image ↗</span>
    </a>
  </div>
</section>

<section class="ep-stage ep-stage-model">
  <div class="ep-stage-heading ep-stage-heading-wide">
    <p class="editorial-kicker">03 · Canonical data model</p>
    <h2>Turn source records into one stable analytical model.</h2>
    <p>The processed Oireachtas layer is organized into validated silver and gold datasets, plus compatibility outputs for existing consumers. Immutable batches preserve auditability while a promoted pointer gives downstream systems a stable production view.</p>
  </div>
  <div class="ep-model-line" aria-label="Simplified canonical data model">
    <div><span>Source</span><strong>Raw records</strong><small>debates · members · votes · bills · questions</small></div>
    <div><span>Silver</span><strong>Normalized facts</strong><small>stable identifiers and relationships</small></div>
    <div><span>Gold</span><strong>Enrichment</strong><small>context · labels · derived datasets</small></div>
    <div><span>Consumer</span><strong>Outputs</strong><small>metrics · visuals · compatibility data</small></div>
  </div>
  <a class="ep-image-evidence ep-image-evidence-wide" href="{{ '/assets/images/portfolio/eirepolitic-canonical-data-model.png' | relative_url }}">
    <img src="{{ '/assets/images/portfolio/eirepolitic-canonical-data-model.png' | relative_url }}" alt="Eirepolitic canonical data model showing source records converging into normalized Silver facts, Gold enrichment and downstream outputs" loading="lazy" />
    <span>Canonical data model: source records → Silver → Gold → downstream outputs. View full graphic ↗</span>
  </a>
  <div class="ep-supporting-evidence">
    <div>
      <span class="ep-sequence-number">Supporting evidence</span>
      <h3>The detailed output-table map is useful once the higher-level model is clear.</h3>
      <p>This documentation view groups the real canonical outputs by role. It is intentionally secondary to the simplified model above, but it shows the breadth of tables behind the Silver, Gold and compatibility layers without sending the reader to a standalone image.</p>
    </div>
    <a class="ep-image-evidence" href="{{ '/assets/images/portfolio/eirepolitic-data-model-docs.png' | relative_url }}">
      <img src="{{ '/assets/images/portfolio/eirepolitic-data-model-docs.png' | relative_url }}" alt="Detailed Eirepolitic output-table documentation grouped by canonical data role" loading="lazy" />
      <span>Detailed output-table documentation. View full image ↗</span>
    </a>
  </div>
</section>

<section class="ep-stage ep-stage-scale">
  <div class="ep-scale-heading">
    <div class="ep-stage-heading ep-stage-heading-wide">
      <p class="editorial-kicker">Scale of the system</p>
      <h2>Large enough that the engineering has to be repeatable.</h2>
      <p>These figures are a conservative snapshot of repository-backed project evidence rather than live counters. They show the scale of the data, processing and publication workflow without summing derived tables into an inflated “total rows” figure.</p>
    </div>
    <p class="ep-scale-updated">Snapshot updated {{ site.data.eirepolitic-scale.updated | date: "%B %Y" }}</p>
  </div>
  <div class="ep-scale-grid">
    {% for metric in site.data.eirepolitic-scale.metrics %}
    <div class="ep-scale-metric">
      <strong>{{ metric.value }}</strong>
      <span>{{ metric.label }}</span>
      <small>{{ metric.note }}</small>
    </div>
    {% endfor %}
  </div>
</section>

<section class="ep-stage ep-stage-classifier">
  <div class="ep-stage-heading ep-stage-heading-wide">
    <p class="editorial-kicker">04 · Classification &amp; enrichment</p>
    <h2>Add meaning without losing provenance.</h2>
    <p>Parliamentary speeches are classified into a controlled issue taxonomy, but model inference is deliberately the final option rather than the default. Existing labels are reused where the underlying speech is unchanged, historical labels are migrated only when a safe match can be proven, and short text is handled deterministically.</p>
  </div>
  <div class="ep-decision-path" aria-label="Speech classification decision flow">
    <div><span>01</span><strong>Reuse when unchanged</strong><small>Text hashes preserve deterministic reuse.</small></div>
    <div><span>02</span><strong>Migrate only safe legacy matches</strong><small>Historical labels move forward only when identity can be proven.</small></div>
    <div><span>03</span><strong>Handle trivial cases deterministically</strong><small>Very short text can resolve to rule-based NONE.</small></div>
    <div class="ep-decision-model"><span>04</span><strong>Use model inference last</strong><small>Only unresolved speeches reach bounded classification.</small></div>
    <div><span>05</span><strong>Validate the candidate</strong><small>Structured outputs are checked before promotion.</small></div>
  </div>
  <a class="ep-deep-dive-cta" href="{{ '/portfolio/eirepolitic/issue-classification/' | relative_url }}">
    <span>Deep dive page</span><strong>Issue classification</strong><small>See the reuse contract, safe historical migration, bounded inference and candidate-safety mechanics.</small><b>Open deep dive →</b>
  </a>
</section>

<section class="ep-stage ep-stage-metrics">
  <div class="ep-stage-heading ep-stage-heading-wide">
    <p class="editorial-kicker">05 · Analysis &amp; political metrics</p>
    <h2>Make analytical definitions reusable and explainable.</h2>
    <p>The metrics layer resolves historical context, eligible populations, denominators, reliability thresholds and completed-period rules before producing a public-facing number.</p>
  </div>
  <div class="ep-metrics-principle">
    <span>Metric contract</span>
    <strong>Define the comparison before calculating the value.</strong>
    <p>Historical attribution, denominator rules and reliability thresholds are part of the metric definition, not cleanup applied after the result.</p>
  </div>
  <ol class="ep-principle-list">
    <li><strong>Historical attribution</strong><span>Party and constituency as they were on the event date.</span></li>
    <li><strong>Explicit denominators</strong><span>Eligible events and populations defined as part of the metric.</span></li>
    <li><strong>Reliability rules</strong><span>Small or ambiguous samples can be withheld from comparison.</span></li>
    <li><strong>Conservative claims</strong><span>A missing recorded vote is not labelled physical absence.</span></li>
  </ol>
  <div class="ep-metrics-footer"><span>Examples: speech activity · issue emphasis · voting participation · party unity · parliamentary questions</span></div>
  <a class="ep-deep-dive-cta" href="{{ '/portfolio/eirepolitic/political-metrics/' | relative_url }}">
    <span>Deep dive page</span><strong>Political metrics</strong><small>See the historical joins, certified legislation bridge, denominator contracts and reliability/materialisation rules.</small><b>Open deep dive →</b>
  </a>
</section>

<section class="ep-stage ep-stage-factory">
  <div class="ep-stage-heading ep-stage-heading-wide">
    <p class="editorial-kicker">06 · Content factory &amp; review</p>
    <h2>Render, review, iterate.</h2>
    <p>The content factory turns structured project inputs into publication-ready visuals. The production asset always comes from the repository renderer; conversation is used to operate and improve that system, not to replace it.</p>
  </div>

  <article class="ep-evidence-story">
    <div class="ep-evidence-copy">
      <span class="ep-sequence-number">01 · Render</span>
      <h3>Generate the exact publication asset from versioned project inputs.</h3>
      <p>The renderer turns structured content and approved design rules into the image that is actually intended for publication. This preview is evidence of the real repository-generated output rather than a mock-up created separately for the portfolio.</p>
    </div>
    <a class="ep-image-card ep-image-card-full" href="{{ '/assets/images/portfolio/eirepolitic-render-preview.png' | relative_url }}">
      <img src="{{ '/assets/images/portfolio/eirepolitic-render-preview.png' | relative_url }}" alt="Preview of generated Eirepolitic visual content" loading="lazy" />
      <span>Repository-generated output. View the full image ↗</span>
    </a>
  </article>

  <article class="ep-evidence-story">
    <div class="ep-evidence-copy">
      <span class="ep-sequence-number">02 · Review</span>
      <h3>Inspect the exact rendered assets before anything is approved.</h3>
      <p>The browser review surface makes the generated output easy to inspect as a set rather than treating publication as a blind automation step. The point is to review the real candidate assets that the publishing workflow will later promote.</p>
    </div>
    <a class="ep-image-card ep-image-card-full" href="{{ '/assets/images/portfolio/eirepolitic-content-review.png' | relative_url }}">
      <img src="{{ '/assets/images/portfolio/eirepolitic-content-review.png' | relative_url }}" alt="Eirepolitic browser-based content review page" loading="lazy" />
      <span>Browser-based review of the generated candidate assets. View full image ↗</span>
    </a>
  </article>

  <article class="ep-evidence-story">
    <div class="ep-evidence-copy">
      <span class="ep-sequence-number">03 · Iterate</span>
      <h3>Turn review feedback into a reproducible, versioned change.</h3>
      <p>Conversation is used to describe the required adjustment and operate the repository workflow. The durable result remains a code or configuration change in the project, so the next render can be reproduced rather than depending on a one-off manual edit.</p>
    </div>
    <a class="ep-image-card ep-image-card-full" href="{{ '/assets/images/portfolio/eirepolitic-chat-iteration.png' | relative_url }}">
      <img src="{{ '/assets/images/portfolio/eirepolitic-chat-iteration.png' | relative_url }}" alt="Conversational iteration of an Eirepolitic visual design" loading="lazy" />
      <span>Feedback and iteration captured as part of the development workflow. View full image ↗</span>
    </a>
  </article>

  <a class="ep-deep-dive-cta" href="{{ '/portfolio/eirepolitic/content-factory/' | relative_url }}">
    <span>Deep dive page</span><strong>Content Factory</strong><small>See the project adapters, deterministic renderer, review-state model, QA gates and reusable design-feedback loop.</small><b>Open deep dive →</b>
  </a>
</section>

<section class="ep-stage ep-stage-publishing">
  <div class="ep-stage-heading ep-stage-heading-wide">
    <p class="editorial-kicker">07 · Scheduling &amp; publishing</p>
    <h2>Separate content approval from publication execution.</h2>
    <p>Once a render is reviewed, the publishing workflow promotes the exact approved assets, records an approval fingerprint, and either publishes immediately or creates a one-time schedule. DynamoDB remains the authoritative publication ledger while EventBridge Scheduler and Lambda handle future execution. Durable provider state prevents duplicate publication across retries.</p>
  </div>

  <div class="ep-publish-schedule-row">
    <div class="ep-evidence-copy">
      <span class="ep-sequence-number">Operational schedule</span>
      <h3>The publication inventory is part of the control plane, not an afterthought.</h3>
      <p>This schedule view shows the operational state used to manage future publication. Approved content can be assigned a one-time execution time while the publication ledger keeps the durable state required for retries and duplicate protection.</p>
    </div>
    <a class="ep-image-evidence ep-schedule-proof" href="{{ '/assets/images/portfolio/eirepolitic-schedule-inventory.png' | relative_url }}">
      <img src="{{ '/assets/images/portfolio/eirepolitic-schedule-inventory.png' | relative_url }}" alt="Eirepolitic publishing schedule inventory" loading="lazy" />
      <span>Publishing schedule inventory. View full image ↗</span>
    </a>
  </div>

  <div class="ep-publish-line" aria-label="Instagram publishing architecture">
    <div><span>01</span><strong>Approved</strong><small>Exact reviewed artifact and approval fingerprint</small></div>
    <div><span>02</span><strong>Scheduled / executed</strong><small>S3 · DynamoDB · EventBridge Scheduler · Lambda</small></div>
    <div><span>03</span><strong>Published</strong><small>Durable provider state and public delivery</small></div>
  </div>

  <article class="ep-evidence-story ep-published-story">
    <div class="ep-evidence-copy">
      <span class="ep-sequence-number">Public result</span>
      <h3>The final post is the visible endpoint of the same controlled workflow.</h3>
      <p>The published result shown here is the artifact that passed through rendering, review, approval and execution. Keeping the publication state alongside the approved asset makes the public output traceable to the exact candidate that was reviewed.</p>
    </div>
    <a class="ep-image-evidence ep-publish-result" href="{{ '/assets/images/portfolio/eirepolitic-published-instagram.png' | relative_url }}">
      <img src="{{ '/assets/images/portfolio/eirepolitic-published-instagram.png' | relative_url }}" alt="Eirepolitic content published on Instagram" loading="lazy" />
      <span>Pipeline-generated content published to Instagram. View full image ↗</span>
    </a>
  </article>

  <div class="ep-publishing-footer"><span>Immediate and scheduled canaries completed against the real account in September 2026.</span></div>
  <a class="ep-deep-dive-cta" href="{{ '/portfolio/eirepolitic/automated-publishing/' | relative_url }}">
    <span>Deep dive page</span><strong>Automated publishing</strong><small>See immutable handoff, approval fingerprints, durable state, scheduler payloads, idempotency and runtime secrets.</small><b>Open deep dive →</b>
  </a>
</section>

<section class="ep-summary">
  <div class="ep-stage-heading ep-stage-heading-wide">
    <p class="editorial-kicker">What this project demonstrates</p>
    <h2>One project spanning data, analysis and operational delivery.</h2>
  </div>
  <div class="ep-summary-grid">
    <div><strong>Data &amp; modelling</strong><span>Ingestion · validation · canonical datasets · historical relationships · versioned batches</span></div>
    <div><strong>Analysis &amp; applied models</strong><span>Metrics · contextual joins · bounded classification · reliability rules · explainable definitions</span></div>
    <div><strong>Automation &amp; cloud</strong><span>GitHub Actions · S3 · DynamoDB · EventBridge Scheduler · Lambda · Meta publishing</span></div>
  </div>
</section>

<section class="ep-next-steps">
  <div>
    <p class="editorial-kicker">Continue exploring</p>
    <h2>Four technical deep dives.</h2>
    <p>Each page focuses on implementation detail that is deliberately omitted from the flagship overview.</p>
  </div>
  <div class="ep-link-list ep-deep-dive-directory">
    <a href="{{ '/portfolio/eirepolitic/issue-classification/' | relative_url }}"><strong>Issue classification</strong><span>Reuse contracts, safe migration, bounded inference and candidate safety.</span></a>
    <a href="{{ '/portfolio/eirepolitic/political-metrics/' | relative_url }}"><strong>Political metrics</strong><span>Historical joins, certified relationships, denominators and reliability.</span></a>
    <a href="{{ '/portfolio/eirepolitic/content-factory/' | relative_url }}"><strong>Content Factory</strong><span>Adapters, deterministic rendering, review state, QA and feedback loops.</span></a>
    <a href="{{ '/portfolio/eirepolitic/automated-publishing/' | relative_url }}"><strong>Automated publishing</strong><span>Approval fingerprints, durable state, scheduling and idempotent execution.</span></a>
    <a class="ep-next-docs" href="https://github.com/warrengleeson/eirepolitic-data-pipeline"><strong>Technical documentation</strong><span>Canonical implementation detail and operational documentation in the source repository.</span></a>
  </div>
</section>
