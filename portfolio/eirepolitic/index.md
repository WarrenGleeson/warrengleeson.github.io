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

<section class="case-study-section eirepolitic-brand-panel">
  <div class="eirepolitic-brand-copy">
    <p class="editorial-kicker">The system</p>
    <h2>From public political data to reviewed, scheduled content.</h2>
    <p>I built Eirepolitic as one connected system rather than a collection of isolated scripts. It collects political data, validates and restructures it into a stable model, enriches it, calculates reusable metrics, turns selected outputs into visual content, and can publish approved content automatically.</p>
  </div>
  <div class="eirepolitic-flow" role="img" aria-label="Eirepolitic end-to-end data flow">
    <div><strong>Sources</strong><span>Oireachtas API<br>Polling sources</span></div>
    <i>→</i>
    <div><strong>Process</strong><span>Python<br>validation</span></div>
    <i>→</i>
    <div><strong>Store</strong><span>S3<br>canonical model</span></div>
    <i>→</i>
    <div><strong>Enrich</strong><span>classification<br>context</span></div>
    <i>→</i>
    <div><strong>Analyse</strong><span>metrics<br>research</span></div>
    <i>→</i>
    <div><strong>Create</strong><span>rendering<br>review</span></div>
    <i>→</i>
    <div><strong>Publish</strong><span>DynamoDB<br>Lambda · Meta</span></div>
  </div>
</section>

<figure class="case-study-inline-image case-study-lead-image">
  <img src="{{ '/assets/images/portfolio/eirepolitic-project-card.png' | relative_url }}" alt="Representative Eirepolitic visual output" />
  <figcaption>A representative Eirepolitic output showing the kind of finished content produced from the underlying data pipeline.</figcaption>
</figure>

<section class="case-study-section case-study-two-column">
  <div>
    <p class="editorial-kicker">Why I built it</p>
    <h2>A reliable layer between raw political records and public-facing analysis.</h2>
  </div>
  <div>
    <p>Irish parliamentary data is rich, but the useful information is spread across different record types, historical relationships and source structures. A public chart or post may look simple, but producing it responsibly means knowing which source record it came from, which political context applied on that date, what denominator was used, and whether the result is safe to compare.</p>
    <p>The pipeline makes those decisions explicit and repeatable so downstream analysis and content do not need to reinvent them.</p>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">01 · Sources</p>
  <h2>Start with traceable source data.</h2>
  <div class="case-study-two-column compact-gap">
    <p>The main parliamentary source is Oireachtas data, covering records such as members, debates, speeches, divisions, legislation and parliamentary questions. Separate ingestion work also supports polling data, including the Irish Polling Indicator source, with source-version and reuse controls built into the process.</p>
    <div class="eirepolitic-tech-note"><strong>Tools in context</strong><span>APIs · Python · GitHub Actions · source hashes · manifests</span></div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">02 · Ingestion &amp; processing</p>
  <h2>Validate before treating data as usable.</h2>
  <div class="case-study-two-column compact-gap">
    <p>Extraction is only the first step. The pipeline checks schemas, keys, dates, duplicate conditions, historical ranges and source-specific quality rules before data can move forward. Scheduled workflows handle recurring refreshes, while candidate builds allow new versions to be tested before becoming the promoted dataset.</p>
    <div class="eirepolitic-tech-note"><strong>Tools in context</strong><span>Python · GitHub Actions · scheduled workflows · candidate validation</span></div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">03 · Canonical data model</p>
  <h2>Turn source records into one stable analytical model.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>The processed Oireachtas layer is organized into validated silver and gold datasets, plus compatibility outputs for existing consumers. Data is written into immutable batch locations and only promoted after validation, which gives downstream systems a stable production view without losing the ability to audit or roll back previous versions.</p>
      <p>This model is the foundation for everything that follows: historical political context, metrics, content generation and publishing all depend on consistent identifiers and relationships here.</p>
    </div>
    <div class="model-stack" aria-label="Simplified canonical data model">
      <div><strong>Source records</strong><span>debates · members · votes · bills · questions</span></div>
      <div><strong>Silver tables</strong><span>normalized facts and relationships</span></div>
      <div><strong>Gold / enrichment</strong><span>context, labels and derived datasets</span></div>
      <div><strong>Consumer outputs</strong><span>metrics · visuals · compatibility datasets</span></div>
    </div>
  </div>
  <figure class="case-study-inline-image">
    <img src="{{ '/assets/images/portfolio/eirepolitic-data-model-docs.png' | relative_url }}" alt="Eirepolitic data model documentation showing output tables grouped by category" loading="lazy" />
    <figcaption>Canonical data-model documentation showing the output tables grouped by their downstream role.</figcaption>
  </figure>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">04 · Classification &amp; enrichment</p>
  <h2>Add meaning without losing provenance.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>One of the heavier enrichment components classifies parliamentary speeches into a controlled issue taxonomy. The current classifier design reuses existing labels where the underlying speech has not changed, migrates historical labels only when a safe match can be proven, skips very short text, and sends only genuinely new or changed speeches for model classification.</p>
      <p>The newer unified classifier is implemented and integrated into the candidate workflow, with explicit validation and historical-backfill gates before full production use. That separation is intentional: expensive or model-driven processing should be testable without quietly changing production data.</p>
      <p><a href="{{ '/portfolio/eirepolitic/issue-classification/' | relative_url }}"><strong>Read the issue-classification deep dive →</strong></a></p>
    </div>
    <div class="eirepolitic-tech-note"><strong>Tools in context</strong><span>OpenAI Responses API · structured outputs · text hashes · controlled taxonomy · candidate batches</span></div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">05 · Analysis &amp; political metrics</p>
  <h2>Make analytical definitions reusable and explainable.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>The metrics layer sits between canonical data and presentation. It handles details such as event-date party and constituency attribution, eligible populations, denominators, reliability thresholds and completed-period rules.</p>
      <p>That means a metric such as voting participation, party focus on an issue, or speeches per debate day carries both a public explanation and a precise technical definition. The system also explicitly avoids unsupported interpretations—for example, a missing recorded vote is not treated as proof that a TD was physically absent.</p>
      <p><a href="{{ '/portfolio/eirepolitic/political-metrics/' | relative_url }}"><strong>Read the political-metrics deep dive →</strong></a></p>
    </div>
    <div class="metric-example-list">
      <span>Speech activity</span><span>Issue emphasis</span><span>Voting participation</span><span>Party voting unity</span><span>Parliamentary questions</span><span>Constituency measures</span>
    </div>
  </div>
  <figure class="case-study-inline-image">
    <img src="{{ '/assets/images/portfolio/eirepolitic-metrics-example.png' | relative_url }}" alt="Example Eirepolitic political metrics output" loading="lazy" />
    <figcaption>A real analytical result produced from the political-metrics layer.</figcaption>
  </figure>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">06 · Content factory &amp; review</p>
  <h2>Turn analysis into repeatable visual content.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>The Instagram content factory renders publication-ready slides from structured project inputs rather than designing every post manually. The render path includes deterministic layouts, reusable house-style assets, QA checks, previews and review artifacts.</p>
      <p>I interact with that system conversationally when iterating on designs: a render is generated through the real repository workflow, I review the exact output in a browser-friendly preview, then request specific changes and rerender. The production asset remains the repository-generated output rather than an ad-hoc image created in chat.</p>
      <p><a href="{{ '/portfolio/eirepolitic/content-factory/' | relative_url }}"><strong>Read the content-factory deep dive →</strong></a></p>
    </div>
    <figure class="case-study-inline-image compact-image">
      <img src="{{ '/assets/images/portfolio/eirepolitic-render-preview.png' | relative_url }}" alt="Preview of generated Eirepolitic visual content before publication" loading="lazy" />
      <figcaption>Repository-generated content presented for review before approval and publishing.</figcaption>
    </figure>
  </div>
  <div class="case-study-image-grid case-study-section-image-grid">
    <figure>
      <img src="{{ '/assets/images/portfolio/eirepolitic-content-review.png' | relative_url }}" alt="Eirepolitic browser-based content review page" loading="lazy" />
      <figcaption>The browser-based review surface showing the real rendered carousel assets.</figcaption>
    </figure>
    <figure>
      <img src="{{ '/assets/images/portfolio/eirepolitic-chat-iteration.png' | relative_url }}" alt="Conversational iteration of an Eirepolitic visual design" loading="lazy" />
      <figcaption>Natural-language design feedback translated into a repository change and rerender.</figcaption>
    </figure>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">07 · Scheduling &amp; publishing</p>
  <h2>Separate content approval from publication execution.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>Once a render is reviewed, the publishing workflow promotes the exact approved assets, records the publication request and approval fingerprint, and either publishes immediately or creates a one-time schedule.</p>
      <p>DynamoDB is the authoritative publication ledger. EventBridge Scheduler mirrors upcoming execution jobs. A Lambda reloads the approved request and immutable assets from AWS before contacting Meta, while durable execution state prevents duplicate publication across retries.</p>
      <p>The complete path was proven against the real Instagram Professional account with successful immediate and scheduled canary publications in September 2026.</p>
      <p><a href="{{ '/portfolio/eirepolitic/automated-publishing/' | relative_url }}"><strong>Read the automated-publishing deep dive →</strong></a></p>
    </div>
    <div class="publishing-stack" aria-label="Instagram publishing architecture">
      <div><strong>Reviewed render</strong><span>exact artifact</span></div>
      <b>↓</b>
      <div><strong>S3 + DynamoDB</strong><span>immutable assets + approval ledger</span></div>
      <b>↓</b>
      <div><strong>EventBridge Scheduler</strong><span>one-time execution</span></div>
      <b>↓</b>
      <div><strong>AWS Lambda</strong><span>idempotent publisher</span></div>
      <b>↓</b>
      <div><strong>Meta / Instagram</strong><span>published media</span></div>
    </div>
  </div>
  <div class="case-study-image-grid case-study-section-image-grid">
    <figure>
      <img src="{{ '/assets/images/portfolio/eirepolitic-schedule-inventory.png' | relative_url }}" alt="Eirepolitic publishing schedule inventory" loading="lazy" />
      <figcaption>The scheduling and publication-control view used to inspect upcoming posts and execution state.</figcaption>
    </figure>
    <figure>
      <img src="{{ '/assets/images/portfolio/eirepolitic-published-instagram.png' | relative_url }}" alt="Eirepolitic content published on Instagram" loading="lazy" />
      <figcaption>A real pipeline-generated Eirepolitic output after publication to Instagram.</figcaption>
    </figure>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">What this project demonstrates</p>
  <h2>One project, several engineering disciplines.</h2>
  <div class="capability-grid">
    <div><strong>Data engineering</strong><span>ingestion, validation, modelling, versioned datasets</span></div>
    <div><strong>Analytics</strong><span>metrics, historical attribution, denominators, reliability rules</span></div>
    <div><strong>Automation</strong><span>scheduled workflows, candidate promotion, publishing orchestration</span></div>
    <div><strong>Cloud infrastructure</strong><span>S3, DynamoDB, Lambda, EventBridge Scheduler, Secrets Manager</span></div>
    <div><strong>Applied language models</strong><span>bounded classification with structured outputs and reuse controls</span></div>
    <div><strong>Product workflow</strong><span>rendering, human review, conversational iteration, approval and publishing</span></div>
  </div>
</section>

<section class="case-study-section technical-links-section">
  <p class="editorial-kicker">Go deeper</p>
  <h2>Canonical technical documentation</h2>
  <p>The portfolio page is intentionally a presentation layer. The implementation detail remains in the project repository.</p>
  <div class="technical-link-grid">
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/oireachtas_final_production_readiness_handoff.md"><strong>Unified Oireachtas pipeline</strong><span>Production-readiness and orchestration state</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/oireachtas_speech_issue_classifier_v2.md"><strong>Speech issue classifier</strong><span>Classifier design, reuse policy and validation gates</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/political_metrics_foundation.md"><strong>Political metrics foundation</strong><span>Metric definitions, historical correctness and candidate materialization</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/operations/instagram_publishing_standard.md"><strong>Instagram publishing standard</strong><span>Approval, scheduling, AWS runtime and Meta publishing</span></a>
  </div>
</section>
