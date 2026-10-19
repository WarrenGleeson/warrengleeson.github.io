---
title: Revenue Investigation — Wave 6 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the top three Wave 6 concepts. No Stage 5 development or customer testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 236
permalink: /projects/notes/revenue-investigation-wave-6-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-6, stage-4, acquisition]
---

# Wave 6 Stage 4 — Implementation Plans

This document stops at planning. No product, ad campaign, outreach campaign, checkout flow or validation test should be launched from this chat.

## Rank 1 — Battery DPP readiness / payload validator

### Core promise
Check whether battery-passport data is structurally complete and consistent against a versioned interpretation of current European Commission guidance before committing to a DPP platform or registry workflow.

### MVP plan
- Browser upload / paste for CSV and JSON.
- Select battery category.
- Versioned rule pack based on current Commission battery-passport guidance.
- Required / conditional / later-applicable field classification.
- Identifier, duplicate-reference and basic format checks.
- Exportable issue report with rule/source version.
- Explicit disclaimer: readiness aid, not legal certification or official EU approval.

### Likely stack
- Static front end.
- Python rule engine packaged as serverless function or client-side WASM where practical.
- Versioned YAML/JSON rule definitions.
- Optional API later if demand justifies it.

### Pricing hypothesis
- Free: one record / sample payload.
- €9–19: one bulk validation.
- €29–49/month: saved schemas, history, API or recurring batch checks.

### Semi-automated acquisition pipeline
1. Maintain a source watcher for European Commission DPP/battery guidance pages and published guidance revisions.
2. When guidance changes, create a factual diff queue for human review before any rule/content update.
3. Generate search pages around specific readiness questions such as required battery-passport fields, identifier checks and February 2027 data preparation.
4. Rank pages by impressions, tool starts, completed validations and paid-intent events.
5. Discover public battery-industry directories, manufacturer associations and relevant marketplace listings; score prospects only for research/validation relevance.
6. Generate a factual personalized sample showing publicly visible product-data gaps only where the evidence is clear; never infer compliance failure from missing public data.
7. Any outreach must be manually approved, legally compliant and low volume; opt-out/unsubscribe requirements apply where commercial messaging laws require them.
8. Route only qualified replies or repeated tool usage to the owner.

### Stage 5 validation concept for a future chat
A future chat could test demand with a static checklist/sample validator before building registry integrations.

### Main risks
- Regulatory guidance can change.
- Full DPP software market is crowded.
- Legal/compliance positioning must remain conservative and source-versioned.

### Stage 4 verdict
**Highest-priority Wave 6 candidate.**

---

## Rank 2 — Canadian tariff-table diff notifier

### Core promise
Watch selected Canadian HS codes or chapters and tell users exactly what changed when CBSA publishes a new tariff revision.

### MVP plan
- Ingest official CBSA tariff releases and effective dates.
- User watchlist of HS codes/chapters.
- Deterministic before/after diff.
- Direct official source links.
- Email/RSS/webhook alert option.
- No tariff classification advice or legal interpretation.

### Likely stack
- Python ingestion/diff pipeline.
- Scheduled GitHub Actions or AWS Lambda.
- Small relational/SQLite store for versions/watchlists.
- Static searchable public change pages where licensing/public-source rules permit.

### Pricing hypothesis
- Free: one watched code.
- CA$9/month: up to 25 codes.
- CA$19/month: up to 100 codes and export/webhook.
- CA$10 one-off historical diff report.

### Semi-automated acquisition pipeline
1. Monitor CBSA tariff-release pages and official notices for new versions.
2. Parse each new release into a change inventory by chapter/code.
3. Automatically create factual public change summaries for affected codes after human verification.
4. Use search-console/on-site queries to identify codes with recurring interest and prioritize those pages.
5. Discover public directories of Canadian importers, customs-adjacent consultants and trade associations; score by likely relevance to affected chapters.
6. Create factual examples referencing only public tariff changes and the prospect's publicly stated product categories.
7. Queue a small, compliant, manually approved outreach batch only when useful for validation; continuous cold outreach is not part of the intended business model.
8. Triage replies automatically and alert the owner only on qualified interest.

### Main risks
- Established customs/trade suites offer broader monitoring.
- CBSA source formats may change.
- Must avoid implying that a tariff-text change automatically changes a customer’s legal classification or duty outcome.

### Stage 4 verdict
**Strong low-touch monitoring concept with a clear Canadian source.**

---

## Rank 3 — Procurement addendum change detector

### Core promise
Watch a public procurement opportunity and show bidders what changed whenever a new addendum or revised attachment appears.

### MVP plan
- User supplies a supported public RFP opportunity URL.
- Store page/file fingerprints and metadata.
- Detect new/replaced addenda and attachments.
- Produce a cited change summary: deadlines, forms, requirements, quantities or pricing instructions when deterministically identifiable.
- Link every finding to source document/page.
- Do not draft proposals or claim legal completeness.

### Likely stack
- Python fetch/diff workers.
- Source adapters for a deliberately small set of procurement portals.
- Object storage for permitted public snapshots/hashes.
- Email/RSS notifications.

### Pricing hypothesis
- CA$5–10 per watched opportunity.
- CA$19/month: small active watchlist.
- CA$39/month: larger watchlist / team alerts.

### Semi-automated acquisition pipeline
1. Monitor supported procurement portals for opportunities with multiple addenda or frequent document revisions.
2. Score opportunity categories by number of bidders/vendors, addendum frequency and repeat use potential.
3. Publish factual examples using closed/public opportunities, demonstrating before/after document changes with citations.
4. Use search traffic and procurement communities as the primary acquisition channel.
5. Discover public vendor directories only for tightly targeted validation; generate samples for relevant closed opportunities rather than fabricating hypothetical savings.
6. Keep any outreach low-volume, manually approved and compliant with applicable commercial-email rules.
7. Track watch creation, repeat watches and alert engagement; surface only qualified interest to the owner.

### Main risks
- Portal-specific maintenance burden.
- Terms of use and robots/access rules vary by source.
- PDF changes can be noisy; exact citation and confidence levels are important.

### Stage 4 verdict
**Viable if source coverage stays narrow and disciplined.**

## Wave 6 conclusion

Top three:

1. Battery DPP readiness / payload validator
2. Canadian tariff-table diff notifier
3. Procurement addendum change detector

All three fit the current preference better than service-heavy concepts because their primary acquisition can be search, monitoring, marketplace/API discovery or product-led usage rather than constant lead chasing.

## Verification record

- Last verified: 2026-10-19
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
