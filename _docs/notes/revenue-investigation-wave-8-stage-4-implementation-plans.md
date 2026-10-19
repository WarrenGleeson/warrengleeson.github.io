---
title: Revenue Investigation — Wave 8 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest Wave 8 concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 244
permalink: /projects/notes/revenue-investigation-wave-8-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-8, stage-4, acquisition]
---

# Wave 8 Stage 4 — Implementation Plans

This document is planning only. No ads, outreach campaigns, payments, product launch or Stage 5 development should be executed from this chat.

## Rank 1 — Google Ads API version-upgrade source scanner

### Core promise
Scan a repository and show which Google Ads API breaking changes, deprecations and sunset risks actually affect that codebase.

### MVP plan
- CLI/GitHub Action.
- Detect Google Ads client-library/API versions from dependency/config files.
- Identify service, method, resource, enum and GAQL field usage in supported languages.
- User selects target API version.
- Versioned rules map source usage to official release notes, proto diffs, deprecations and sunset dates.
- Output exact file/line evidence where feasible plus official source link.
- Distinguish definite match from heuristic review-needed findings.

### Likely stack
- Python or TypeScript static scanner.
- YAML/JSON versioned rule packs.
- GitHub Action and local CLI.
- Optional hosted history/multi-repo dashboard later.

### Pricing hypothesis
- Free: local/single-repository scan.
- CA$10–25/month: multi-repo history, scheduled upgrade readiness and team reports.
- Optional one-off upgrade readiness export.

### Semi-automated acquisition pipeline
1. Monitor official Google Ads API release notes, deprecation pages and sunset schedules.
2. Parse candidate breaking changes into rule proposals; human-verify against official docs before publishing.
3. Generate version-specific search pages such as “Google Ads API v25 to v26 upgrade scanner” with factual examples.
4. Free GitHub Action/CLI becomes the primary product-led acquisition channel.
5. Use public GitHub search only for aggregate market research on API-version usage and recurring migration patterns; do not automatically open issues or PRs.
6. For tightly controlled validation, identify public repositories with clearly detectable old Google Ads API versions, create factual local scan samples, and queue only manually approved contribution/contact opportunities consistent with repository rules.
7. Track opt-in scanner usage, repeat scans and multi-repo needs; alert owner only on qualified team interest.

### Main risks
- Language-specific static analysis complexity.
- False positives if Google terminology appears outside executable usage.
- Continuous rule maintenance every release.

### Stage 4 verdict
**Highest-priority Wave 8 concept.**

---

## Rank 2 — Amazon.ca lithium-battery seller readiness workspace

### Core promise
Help Amazon.ca sellers organize product/listing evidence for the new lithium-battery validation process without pretending to certify compliance.

### MVP plan
- Import seller CSV/catalog extract.
- Rules based only on Amazon's published affected/excluded product scope.
- Flag “likely affected,” “likely excluded” and “manual review required.”
- Check presence of model/part/item number and manufacturer/brand fields.
- User-maintained evidence checklist for TIC provider, lab report date, UN 38.3/BTS where applicable, language/instruction evidence and review status.
- Expiry reminders for test reports.
- Export per-SKU readiness packet/checklist.
- No editing, generation or alteration of compliance/test documents.

### Likely stack
- Browser-first CSV tool or Shopify/Amazon-adjacent SaaS.
- Rule definitions stored in versioned YAML.
- Lightweight database only for monitored catalogs/evidence dates.

### Pricing hypothesis
- Free: small catalog/one-time checklist.
- CA$19–49: one-off catalog readiness report.
- CA$15–39/month: evidence-expiry/status monitoring.

### Semi-automated acquisition pipeline
1. Monitor Amazon.ca policy/help pages and Seller Forums announcements for scoped lithium-battery compliance changes.
2. Diff policy text and queue every rule change for human approval before updating classifications.
3. Publish factual, narrowly scoped search pages by affected product class and documentation type.
4. Offer a free CSV readiness scan as the primary inbound conversion path.
5. Discover public Amazon seller communities/directories only for market sizing and recurring-question analysis.
6. For controlled validation, generate sample checklists using fictional/synthetic catalog data or a seller's voluntarily supplied data; never scrape private Seller Central information.
7. If outreach is ever used in a future validation chat, keep it low-volume, manually approved and compliant; the intended model remains inbound/self-serve.
8. Route only qualified seller/TIC-provider partnership interest to the owner.

### Main risks
- Compliance/legal sensitivity.
- Amazon policy scope can change quickly.
- Product-category classification from catalog text can be uncertain.

### Stage 4 verdict
**Strong timing and operational pain, but higher risk than rank 1.**

---

## Rank 3 — IRIS schema/business-rule local diff + impact report

### Core promise
Let authorized tax-software teams privately compare two IRIS rule/schema releases and understand what changed without uploading restricted packages or taxpayer data.

### MVP plan
- Local desktop/CLI utility.
- User supplies legitimately obtained prior/current IRIS schema/business-rule packages.
- Structural XML/schema diff.
- Detect added/removed/changed rule IDs and descriptions where represented.
- Version/effective-date inventory.
- Optional repository scan for referenced form fields/elements.
- Export human-readable migration checklist.
- No network upload by default.
- No redistribution of SOR packages.

### Likely stack
- Python CLI/local web UI.
- XML/XSD parsing and deterministic diff engine.
- Optional GitHub Action only for repositories that do not contain restricted source packages/secrets.

### Pricing hypothesis
- Free: local package-to-package diff.
- CA$15–30/month/team: version history, collaborative notes, repository impact mapping and recurring workflow support.

### Semi-automated acquisition pipeline
1. Monitor public IRS IRIS schema/business-rule release metadata, QuickAlerts, known-issues pages and ATS schedules.
2. Generate public release timelines/metadata only; do not mirror restricted schema packages.
3. Publish search pages explaining version transitions and how local comparison works, with synthetic examples.
4. Free local CLI is the acquisition channel for authorized software developers/transmitters.
5. Use public IRS working-group topics and developer forums to rank recurring migration pain points.
6. For validation, create synthetic sample packages mirroring structural change classes rather than using or redistributing protected IRS materials.
7. Any outreach to tax-software vendors in a future chat must be low-volume, factual, manually approved and legally compliant.
8. Alert owner only when a team requests collaboration/history/repository-impact features.

### Main risks
- Small addressable market.
- Access rules around SOR materials require disciplined local-only handling.
- Business-rule formats may not diff cleanly without authorized sample access.

### Stage 4 verdict
**Niche but defensible technical utility with recurring annual/versioned demand.**

## Wave 8 conclusion

Top three:

1. Google Ads API version-upgrade source scanner
2. Amazon.ca lithium-battery seller readiness workspace
3. IRIS schema/business-rule local diff + impact report

Wave 8 adds three opportunity classes that were not prominent in earlier waves: integration-specific code impact scanning, seller-side evidence readiness for a newly changed marketplace rule, and private local tooling for a mandated tax-system transition.

## Verification record

- Last verified: 2026-10-19
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
