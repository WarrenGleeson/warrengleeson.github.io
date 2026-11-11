---
layout: case-study
title: Eirepolitic Data Pipeline
permalink: /portfolio/eirepolitic/
presentation: editorial
kicker: Featured project
summary: An end-to-end political data, analysis and automated publishing platform.
tags:
  - Data Engineering
  - Analytics
  - Automation
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
    <p>The technical work is designed to stay traceable from source records through to the content that a reader eventually sees.</p>
  </div>
  <a class="ep-outcome-proof" href="{{ '/assets/images/portfolio/eirepolitic-project-card.png' | relative_url }}">
    <img src="{{ '/assets/images/portfolio/eirepolitic-project-card.png' | relative_url }}" alt="Representative Eirepolitic visual output" />
    <span>Representative public output ↗</span>
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
  <div class="ep-source-evidence-row">
    <div class="ep-context-note">
      <span>Tools in context</span>
      <strong>APIs · Python · GitHub Actions · source hashes · manifests · candidate validation</strong>
    </div>
    <a class="ep-image-evidence ep-image-evidence-compact" href="{{ '/assets/images/portfolio/eirepolitic-metrics-example.png' | relative_url }}">
      <img src="{{ '/assets/images/portfolio/eirepolitic-metrics-example.png' | relative_url }}" alt="Example polling output generated from an ingested polling source" loading="lazy" />
      <span>Polling is a separate source stream. View full image ↗</span>
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
  <a class="ep-image-evidence ep-image-evidence-wide" href="{{ '/assets/images/portfolio/eirepolitic-data-model-docs.png' | relative_url }}">
    <img src="{{ '/assets/images/portfolio/eirepolitic-data-model-docs.png' | relative_url }}" alt="Eirepolitic data model documentation showing output tables grouped by category" loading="lazy" />
    <span>Canonical output tables grouped by downstream role. View full-size documentation ↗</span>
  </a>
</section>

<section class="ep-stage ep-stage-classifier">
  <div class="ep-story-split">
    <div>
      <p class="editorial-kicker">04 · Classification &amp; enrichment</p>
      <h2>Add meaning without losing provenance.</h2>
    </div>
    <div class="ep-prose">
      <p>Parliamentary speeches are classified into a controlled issue taxonomy, but model inference is deliberately the final option rather than the default.</p>
      <p>Existing labels are reused where the underlying speech is unchanged, historical labels are migrated only when a safe match can be proven, and short text is handled deterministically.</p>
    </div>
  </div>
  <div class="ep-decision-path" aria-label="Speech classification decision flow">
    <div><span>01</span><strong>Reuse when unchanged</strong><small>Text hashes preserve deterministic reuse.</small></div>
    <div><span>02</span><strong>Migrate only safe legacy matches</strong><small>Historical labels move forward only when identity can be proven.</small></div>
    <div><span>03</span><strong>Handle trivial cases deterministically</strong><small>Very short text can resolve to rule-based NONE.</small></div>
    <div class="ep-decision-model"><span>04</span><strong>Use model inference last</strong><small>Only unresolved speeches reach bounded classification.</small></div>
    <div><span>05</span><strong>Validate the candidate</strong><small>Structured outputs are checked before promotion.</small></div>
  </div>
  <p class="ep-stage-link"><a href="{{ '/portfolio/eirepolitic/issue-classification/' | relative_url }}">Explore the classification deep dive →</a></p>
</section>

<section class="ep-stage ep-stage-metrics">
  <div class="ep-stage-heading">
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
  <div class="ep-metrics-footer"><span>Examples: speech activity · issue emphasis · voting participation · party unity · parliamentary questions</span><a href="{{ '/portfolio/eirepolitic/political-metrics/' | relative_url }}">Explore the political-metrics deep dive →</a></div>
</section>

<section class="ep-stage ep-stage-factory">
  <div class="ep-stage-heading ep-stage-heading-wide">
    <p class="editorial-kicker">06 · Content factory &amp; review</p>
    <h2>Render, review, iterate.</h2>
    <p>The content factory turns structured project inputs into publication-ready visuals. The production asset always comes from the repository renderer; conversation is used to operate and improve that system, not to replace it.</p>
  </div>
  <div class="ep-sequence-grid">
    <article class="ep-sequence-primary">
      <span class="ep-sequence-number">01</span>
      <h3>Render</h3>
      <a class="ep-image-card" href="{{ '/assets/images/portfolio/eirepolitic-render-preview.png' | relative_url }}">
        <img src="{{ '/assets/images/portfolio/eirepolitic-render-preview.png' | relative_url }}" alt="Preview of generated Eirepolitic visual content" loading="lazy" />
        <span>Repository-generated output ↗</span>
      </a>
    </article>
    <article>
      <span class="ep-sequence-number">02</span>
      <h3>Review</h3>
      <a class="ep-image-card" href="{{ '/assets/images/portfolio/eirepolitic-content-review.png' | relative_url }}">
        <img src="{{ '/assets/images/portfolio/eirepolitic-content-review.png' | relative_url }}" alt="Eirepolitic browser-based content review page" loading="lazy" />
        <span>Review the exact rendered assets ↗</span>
      </a>
    </article>
    <article>
      <span class="ep-sequence-number">03</span>
      <h3>Iterate</h3>
      <a class="ep-image-card" href="{{ '/assets/images/portfolio/eirepolitic-chat-iteration.png' | relative_url }}">
        <img src="{{ '/assets/images/portfolio/eirepolitic-chat-iteration.png' | relative_url }}" alt="Conversational iteration of an Eirepolitic visual design" loading="lazy" />
        <span>Feedback becomes a versioned change ↗</span>
      </a>
    </article>
  </div>
  <p class="ep-stage-link"><a href="{{ '/portfolio/eirepolitic/content-factory/' | relative_url }}">Explore the Content Factory deep dive →</a></p>
</section>

<section class="ep-stage ep-stage-publishing">
  <div class="ep-story-split">
    <div>
      <p class="editorial-kicker">07 · Scheduling &amp; publishing</p>
      <h2>Separate content approval from publication execution.</h2>
    </div>
    <div class="ep-prose">
      <p>Once a render is reviewed, the publishing workflow promotes the exact approved assets, records an approval fingerprint, and either publishes immediately or creates a one-time schedule.</p>
      <p>DynamoDB remains the authoritative publication ledger while EventBridge Scheduler and Lambda handle future execution. Durable provider state prevents duplicate publication across retries.</p>
    </div>
  </div>
  <div class="ep-publish-line" aria-label="Instagram publishing architecture">
    <div><span>01</span><strong>Approved</strong><small>Exact reviewed artifact and approval fingerprint</small></div>
    <div><span>02</span><strong>Scheduled / executed</strong><small>S3 · DynamoDB · EventBridge Scheduler · Lambda</small></div>
    <div><span>03</span><strong>Published</strong><small>Durable provider state and public delivery</small></div>
  </div>
  <div class="ep-publish-proof">
    <a class="ep-image-evidence ep-image-evidence-compact" href="{{ '/assets/images/portfolio/eirepolitic-schedule-inventory.png' | relative_url }}">
      <img src="{{ '/assets/images/portfolio/eirepolitic-schedule-inventory.png' | relative_url }}" alt="Eirepolitic publishing schedule inventory" loading="lazy" />
      <span>Operational evidence: schedule inventory ↗</span>
    </a>
    <a class="ep-image-evidence ep-publish-result" href="{{ '/assets/images/portfolio/eirepolitic-published-instagram.png' | relative_url }}">
      <img src="{{ '/assets/images/portfolio/eirepolitic-published-instagram.png' | relative_url }}" alt="Eirepolitic content published on Instagram" loading="lazy" />
      <span>Public result: pipeline-generated Instagram output ↗</span>
    </a>
  </div>
  <div class="ep-publishing-footer"><span>Immediate and scheduled canaries completed against the real account in September 2026.</span><a href="{{ '/portfolio/eirepolitic/automated-publishing/' | relative_url }}">Explore the automated-publishing deep dive →</a></div>
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
    <h2>Choose the level of detail.</h2>
  </div>
  <div class="ep-link-list">
    <a href="{{ '/portfolio/eirepolitic/issue-classification/' | relative_url }}"><strong>Issue classification</strong><span>Controlled taxonomy, deterministic reuse and bounded model inference.</span></a>
    <a href="{{ '/portfolio/eirepolitic/political-metrics/' | relative_url }}"><strong>Political metrics</strong><span>Historical attribution, denominators and reusable metric contracts.</span></a>
    <a href="{{ '/portfolio/eirepolitic/content-factory/' | relative_url }}"><strong>Content Factory</strong><span>Repository rendering, browser review and iterative design workflow.</span></a>
    <a href="{{ '/portfolio/eirepolitic/automated-publishing/' | relative_url }}"><strong>Automated publishing</strong><span>Approval, scheduling, idempotent execution and publication state.</span></a>
    <a class="ep-next-docs" href="https://github.com/warrengleeson/eirepolitic-data-pipeline"><strong>Technical documentation</strong><span>Canonical implementation detail and operational documentation in the source repository.</span></a>
  </div>
</section>
