---
title: Revenue Investigation — Wave 7 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest Wave 7 concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 240
permalink: /projects/notes/revenue-investigation-wave-7-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-7, stage-4, acquisition]
---

# Wave 7 Stage 4 — Implementation Plans

This document is planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — YouTube podcast RSS preflight checker

### Core promise
Tell a podcaster whether an RSS feed is ready for YouTube ingestion and highlight YouTube-specific problems that generic RSS validators may not explain.

### MVP plan
- Accept public RSS URL.
- Check show and episode titles/descriptions for unsupported characters/HTML.
- Verify ownership/contact email presence where exposed by the feed.
- Inspect artwork URLs and common metadata fields.
- Identify back-catalog date ranges that may create duplicate-upload risk.
- Record episode GUID/enclosure metadata so a later scan can detect changed audio URLs/files.
- Provide branded-content disclosure checklist.
- Explain fields that YouTube will not automatically resync after ingestion.
- Every rule references the relevant current YouTube Help guidance/version.

### Likely stack
- Python feed parser and deterministic rules.
- Static/search landing pages.
- Serverless scheduled monitor for recurring scans.
- Optional email alerts for monitored feeds.

### Pricing hypothesis
- Free one-time scan.
- CA$10 one-off migration/readiness report.
- CA$8–15/month monitored feed and change alerts.

### Semi-automated acquisition pipeline
1. Monitor YouTube podcast/RSS Help pages for rule or behavior changes.
2. Diff guidance changes and queue rule updates for human verification before publishing.
3. Generate factual search pages around specific errors/behaviors: invalid RSS characters, ownership email, re-upload behavior, duplicate back-catalog planning and branded-content declarations.
4. Score pages by impressions, checker starts, completed scans and repeat monitoring intent.
5. Discover public podcast directories/feeds for market research and identify common factual feed problems in aggregate.
6. For tightly controlled validation only, create factual sample scans for public feeds; do not make claims about policy violations where a feed alone cannot prove them.
7. Keep any direct outreach low-volume, manually approved and compliant; the intended model is search/product-led acquisition.
8. Alert the owner only for qualified creator/hosting-platform interest.

### Main risks
- Platform behavior changes.
- Generic RSS validators can copy individual checks.
- Some YouTube readiness steps occur only inside YouTube Studio and cannot be validated externally.

### Stage 4 verdict
**Strongest Wave 7 concept.**

---

## Rank 2 — Shopify app upgrade-readiness scanner

### Core promise
Scan a Shopify app repository before an API-version upgrade and identify code/config that conflicts with Shopify’s documented action-required changes.

### MVP plan
- Repository/CLI scan of `shopify.app.toml`, extension TOML and selected source files.
- Target Shopify API version chosen by user.
- Versioned rule packs derived only from official Shopify release notes/changelog.
- Detect known removed/deprecated mutations and configuration requirements.
- Check customer-account metafield definitions/access and extension declaration changes.
- Check JSON metafield size-risk patterns where statically identifiable.
- Flag carrier-service/profile behavior assumptions and selected webhook/event migration issues.
- GitHub PR annotation / Markdown report.
- Never read/store secret values.

### Likely stack
- TypeScript or Python CLI/GitHub Action.
- YAML rule packs keyed to Shopify API versions.
- Optional lightweight hosted history/dashboard later.

### Pricing hypothesis
- Free local/GitHub scan.
- CA$10–25/month team history/policies.
- Optional organization tier for multi-repo reporting.

### Semi-automated acquisition pipeline
1. Monitor official Shopify release notes/changelog for posts marked action-required, deprecated or removed.
2. Convert candidate changes into rule proposals; require human verification against official docs before rule-pack release.
3. Publish searchable release-specific pages such as “Shopify 2027-01 app upgrade checklist.”
4. Free GitHub Action/CLI acts as the primary acquisition channel.
5. Monitor public GitHub issues/discussions for recurring migration failures to prioritize new checks; do not post automated issues to unrelated repositories.
6. For validation, discover public Shopify-app repositories only where licensing/contribution rules permit analysis, generate factual local reports, and prepare manually approved suggestions rather than automated spam.
7. Triage opt-in hosted-feature requests and alert owner only for qualified team/organization interest.

### Main risks
- Continuous maintenance each Shopify release.
- Static analysis can produce false positives if rules are too broad.
- Free scanner may be useful but difficult to monetize; paid value likely sits at organization/history/policy level.

### Stage 4 verdict
**Strong marketplace/product-led developer-tool candidate.**

---

## Rank 3 — Website downloadable-form / PDF version mismatch monitor

### Core promise
Find websites that are still linking stale or inconsistent downloadable forms, PDFs, policies, price lists or document versions.

### MVP plan
- Crawl one domain and inventory linked PDF/DOCX/XLSX files plus identified web forms.
- Record hashes, filenames, titles, document metadata and visible revision/version dates where extractable.
- Group likely versions by filename/content similarity.
- Flag pages that link an older likely version while a newer related file is publicly present.
- Detect repeated links to inconsistent versions across different pages.
- Optional comparison of form field labels against an associated downloadable PDF where mapping confidence is high.
- Confidence score and exact evidence for every finding.
- Never automatically delete/replace documents.

### Likely stack
- Python crawler/document metadata extractor.
- Scheduled serverless scans.
- SQLite/Postgres for snapshots/history.
- WordPress plugin or simple domain-monitoring SaaS could be later distribution surfaces.

### Pricing hypothesis
- Free small-domain scan.
- CA$9 one-off full report.
- CA$12–29/month scheduled monitoring/history.

### Semi-automated acquisition pipeline
1. Build SEO pages around stale PDF, outdated forms, duplicate document versions and website document governance.
2. Free scan acts as primary acquisition funnel.
3. Aggregate anonymized/opt-in issue categories to determine which document types create repeat demand.
4. Discover public association, nonprofit, municipal and professional-service sites with large download libraries for market sizing.
5. For limited validation, create factual sample reports from public links with exact evidence and no assertion that a newer-looking document is legally authoritative unless the site says so.
6. Any outreach remains small, manually approved and compliant; ongoing business should rely on search, plugin discovery and recurring monitoring.
7. Product usage and repeat scan behavior drive upgrade prompts; qualified inbound replies alert owner.

### Main risks
- Version inference is probabilistic when filenames/revision dates are poor.
- Crawling large sites creates cost and robots/terms considerations.
- Some CMSs already handle internal versioning, though cross-site public-link drift remains the wedge.

### Stage 4 verdict
**Promising low-touch website-governance utility if confidence handling is disciplined.**

## Wave 7 conclusion

Top three:

1. YouTube podcast RSS preflight checker
2. Shopify app upgrade-readiness scanner
3. Website downloadable-form / PDF version mismatch monitor

These add three different low-touch opportunity classes to the overall pool: creator distribution infrastructure, developer marketplace tooling and website/document governance.

## Verification record

- Last verified: 2026-10-19
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
