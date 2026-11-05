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
  <div class="ep-system-map" role="img" aria-label="Eirepolitic end-to-end system flow">
    <div class="ep-system-node"><span>01</span><strong>Sources</strong><small>Oireachtas API<br>Polling sources</small></div>
    <div class="ep-system-node"><span>02</span><strong>Process</strong><small>Python<br>validation</small></div>
    <div class="ep-system-node"><span>03</span><strong>Store</strong><small>S3<br>canonical model</small></div>
    <div class="ep-system-node"><span>04</span><strong>Enrich</strong><small>classification<br>context</small></div>
    <div class="ep-system-node"><span>05</span><strong>Analyse</strong><small>metrics<br>research</small></div>
    <div class="ep-system-node"><span>06</span><strong>Create</strong><small>rendering<br>review</small></div>
    <div class="ep-system-node"><span>07</span><strong>Publish</strong><small>AWS<br>Meta</small></div>
  </div>
</section>

<section class="ep-outcome-strip">
  <div>
    <p class="editorial-kicker">The outcome</p>
    <h2>One pipeline, visible all the way to the public result.</h2>
    <p>The technical work is designed to stay traceable from source records through to the content that a reader eventually sees.</p>
  </div>
  <a class="ep-image-card ep-image-card-result" href="{{ '/assets/images/portfolio/eirepolitic-project-card.png' | relative_url }}">
    <img src="{{ '/assets/images/portfolio/eirepolitic-project-card.png' | relative_url }}" alt="Representative Eirepolitic visual output" />
    <span>View full image ↗</span>
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
  <div class="ep-stage-grid">
    <div class="ep-process-card">
      <strong>Acquire</strong>
      <span>APIs and source datasets are captured with version and provenance information.</span>
    </div>
    <div class="ep-process-card">
      <strong>Validate</strong>
      <span>Schemas, keys, dates, duplicate conditions and historical ranges are checked before promotion.</span>
    </div>
    <div class="ep-process-card">
      <strong>Candidate build</strong>
      <span>New data versions can be tested before becoming the promoted production view.</span>
    </div>
  </div>
  <div class="ep-evidence-split">
    <div class="ep-tech-strip"><strong>Tools in context</strong><span>APIs · Python · GitHub Actions · source hashes · manifests · candidate validation</span></div>
    <a class="ep-image-card" href="{{ '/assets/images/portfolio/eirepolitic-metrics-example.png' | relative_url }}">
      <img src="{{ '/assets/images/portfolio/eirepolitic-metrics-example.png' | relative_url }}" alt="Example polling output generated from an ingested polling source" loading="lazy" />
      <span>Polling is a separate source stream handled alongside parliamentary data. View full image ↗</span>
    </a>
  </div>
</section>

<section class="ep-stage ep-stage-model">
  <div class="ep-stage-heading ep-stage-heading-wide">
    <p class="editorial-kicker">03 · Canonical data model</p>
    <h2>Turn source records into one stable analytical model.</h2>
    <p>The processed Oireachtas layer is organized into validated silver and gold datasets, plus compatibility outputs for existing consumers. Immutable batches preserve auditability while a promoted pointer gives downstream systems a stable production view.</p>
  </div>
  <div class="ep-model-flow" aria-label="Simplified canonical data model">
    <div><span>Source</span><strong>Raw records</strong><small>debates · members · votes · bills · questions</small></div>
    <b>→</b>
    <div><span>Silver</span><strong>Normalized facts</strong><small>stable identifiers and relationships</small></div>
    <b>→</b>
    <div><span>Gold</span><strong>Enrichment</strong><small>context · labels · derived datasets</small></div>
    <b>→</b>
    <div><span>Consumer</span><strong>Outputs</strong><small>metrics · visuals · compatibility data</small></div>
  </div>
  <a class="ep-image-card ep-image-card-wide" href="{{ '/assets/images/portfolio/eirepolitic-data-model-docs.png' | relative_url }}">
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
  <div class="ep-decision-flow" role="img" aria-label="Speech classification decision flow">
    <div><strong>Unchanged?</strong><span>Reuse label</span></div>
    <i>→</i>
    <div><strong>Safe legacy match?</strong><span>Migrate label</span></div>
    <i>→</i>
    <div><strong>Very short text?</strong><span>Rule-based NONE</span></div>
    <i>→</i>
    <div><strong>Still pending?</strong><span>Model classification</span></div>
    <i>→</i>
    <div><strong>Candidate</strong><span>Validate before promotion</span></div>
  </div>
  <div class="ep-inline-cta">
    <div><strong>Applied language models, bounded by deterministic controls.</strong><span>Structured outputs · text hashes · controlled taxonomy · candidate batches</span></div>
    <a href="{{ '/portfolio/eirepolitic/issue-classification/' | relative_url }}">Explore the classification deep dive →</a>
  </div>
</section>

<section class="ep-stage ep-stage-metrics">
  <div class="ep-stage-heading">
    <p class="editorial-kicker">05 · Analysis &amp; political metrics</p>
    <h2>Make analytical definitions reusable and explainable.</h2>
    <p>The metrics layer resolves historical context, eligible populations, denominators, reliability thresholds and completed-period rules before producing a public-facing number.</p>
  </div>
  <div class="ep-metric-contracts">
    <div><strong>Historical attribution</strong><span>Party and constituency as they were on the event date.</span></div>
    <div><strong>Explicit denominators</strong><span>Eligible events and populations defined as part of the metric.</span></div>
    <div><strong>Reliability rules</strong><span>Small or ambiguous samples can be withheld from comparison.</span></div>
    <div><strong>Conservative claims</strong><span>A missing recorded vote is not labelled physical absence.</span></div>
  </div>
  <div class="ep-inline-cta">
    <div><strong>Examples</strong><span>Speech activity · issue emphasis · voting participation · party unity · parliamentary questions</span></div>
    <a href="{{ '/portfolio/eirepolitic/political-metrics/' | relative_url }}">Explore the political-metrics deep dive →</a>
  </div>
</section>

<section class="ep-stage ep-stage-factory">
  <div class="ep-stage-heading ep-stage-heading-wide">
    <p class="editorial-kicker">06 · Content factory &amp; review</p>
    <h2>Render, review, iterate.</h2>
    <p>The content factory turns structured project inputs into publication-ready visuals. The production asset always comes from the repository renderer; conversation is used to operate and improve that system, not to replace it.</p>
  </div>
  <div class="ep-sequence-grid">
    <article>
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
  <div class="ep-inline-cta">
    <div><strong>Human in the loop, production system in the repository.</strong><span>Deterministic layouts · QA · browser review · conversational iteration</span></div>
    <a href="{{ '/portfolio/eirepolitic/content-factory/' | relative_url }}">Explore the Content Factory deep dive →</a>
  </div>
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
  <div class="ep-publish-flow" role="img" aria-label="Instagram publishing architecture">
    <div><strong>Reviewed render</strong><span>exact artifact</span></div>
    <i>→</i>
    <div><strong>S3 + DynamoDB</strong><span>assets + approval ledger</span></div>
    <i>→</i>
    <div><strong>EventBridge</strong><span>scheduled execution</span></div>
    <i>→</i>
    <div><strong>Lambda</strong><span>idempotent worker</span></div>
    <i>→</i>
    <div><strong>Instagram</strong><span>published result</span></div>
  </div>
  <div class="ep-publish-proof">
    <a class="ep-image-card" href="{{ '/assets/images/portfolio/eirepolitic-schedule-inventory.png' | relative_url }}">
      <img src="{{ '/assets/images/portfolio/eirepolitic-schedule-inventory.png' | relative_url }}" alt="Eirepolitic publishing schedule inventory" loading="lazy" />
      <span>Operational state: schedule inventory ↗</span>
    </a>
    <a class="ep-image-card ep-image-card-result" href="{{ '/assets/images/portfolio/eirepolitic-published-instagram.png' | relative_url }}">
      <img src="{{ '/assets/images/portfolio/eirepolitic-published-instagram.png' | relative_url }}" alt="Eirepolitic content published on Instagram" loading="lazy" />
      <span>Public result: pipeline-generated Instagram output ↗</span>
    </a>
  </div>
  <div class="ep-inline-cta">
    <div><strong>Production-proven execution path.</strong><span>Immediate and scheduled canaries completed against the real account in September 2026.</span></div>
    <a href="{{ '/portfolio/eirepolitic/automated-publishing/' | relative_url }}">Explore the automated-publishing deep dive →</a>
  </div>
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
  <div class="ep-next-grid">
    <a href="{{ '/portfolio/eirepolitic/issue-classification/' | relative_url }}"><strong>Portfolio deep dives</strong><span>Explore classification, political metrics, the Content Factory and automated publishing.</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline"><strong>Technical documentation</strong><span>Go to the canonical repository for implementation detail and operational documentation.</span></a>
  </div>
</section>
