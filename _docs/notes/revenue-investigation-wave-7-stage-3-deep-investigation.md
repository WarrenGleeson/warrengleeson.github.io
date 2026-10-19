---
title: Revenue Investigation — Wave 7 Stage 3 Deep Investigation
summary: Deep investigation of five Wave 7 finalists, including competition checks and promotion of a less-crowded website document-version monitoring concept.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 239
permalink: /projects/notes/revenue-investigation-wave-7-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-7, deep-investigation]
---

# Wave 7 Stage 3 — Deep Investigation

## 1. YouTube podcast RSS preflight checker

### Problem
YouTube accepts podcast RSS ingestion but has platform-specific behavior that generic RSS validators do not fully address. Current YouTube guidance says invalid characters such as `<`, `>` or HTML in titles/descriptions are not allowed; show-detail changes in the RSS feed do not automatically update YouTube; replacement audio does not automatically replace an existing RSS-ingested video; and branded content requires disclosure.

### Product
Paste an RSS URL and receive a YouTube-specific readiness report:

- invalid title/description characters;
- ownership-email presence/readability;
- artwork and episode metadata checks;
- likely duplicate/back-catalog upload risks;
- episodes whose audio changed since a stored prior scan;
- branded-content declaration checklist;
- clear warnings about fields that YouTube will not automatically resync.

### Distribution
Search terms around “YouTube podcast RSS not working,” “submit podcast RSS to YouTube,” creator communities and a free checker with downloadable report.

### Monetization hypothesis
Free one-time scan; CA$8–15/month monitored feed with change alerts; CA$10 one-off migration/readiness report.

### Competition
Generic podcast RSS validators exist, but the current search did not surface a strong exact YouTube-specific preflight product covering these ingestion quirks.

### Risk
YouTube can change ingestion behavior, so checks must be source-versioned and factual rather than claiming guaranteed acceptance.

### Verdict
**Advance.** Strong current platform-specific wedge.

---

## 2. Shopify app upgrade-readiness scanner

### Problem
Shopify’s quarterly API/platform changes increasingly include action-required migrations. Current 2026 examples include removed inventory mutations, customer-account metafield definition/access requirements, JSON metafield write limits, shipping-profile behavior changes, and a forthcoming requirement for `owner_type` in customer-account extension metafield declarations in 2027-01.

### Product
A repository scanner/GitHub Action for Shopify app developers that reads `shopify.app.toml`, extension TOML, GraphQL queries/mutations and selected source files, compares usage against a versioned ruleset derived from Shopify release notes, and produces an upgrade-readiness report for a target API version.

### Distribution
GitHub Marketplace, Shopify developer search/content, free CLI/Action as acquisition, paid organization/history features.

### Monetization hypothesis
Free local/CI scan; CA$10–25/month team history/policy pack; paid one-off upgrade report for private repositories if hosted usage is needed.

### Competition
Generic code/deprecation scanners exist, but a narrow continuously updated Shopify action-required ruleset remains more differentiated than generic metafield tooling. Customer-account metafield access auditing should be incorporated as one rule family rather than treated as a standalone business.

### Risk
Ongoing maintenance is tied directly to Shopify releases. Rules must distinguish “action required” from optional/new functionality.

### Verdict
**Advance.** Strong marketplace/product-led acquisition fit.

---

## 3. Website downloadable-form / PDF version mismatch monitor

### Problem
Organizations frequently publish downloadable forms, price lists, policies and PDFs while maintaining newer versions elsewhere on the same site or CMS. Current help documentation from multiple form/download platforms warns about stale or duplicate file versions, and support cases show PDFs can fall out of sync with updated web forms.

### Product
A website monitor focused specifically on downloadable-document freshness:

- inventory linked PDFs/DOCX/XLSX/forms;
- detect near-duplicate filenames and multiple versions;
- extract visible revision dates/version identifiers when available;
- flag pages linking an older version while a newer likely replacement is publicly present;
- detect changed web-form fields when an associated downloadable PDF appears unchanged;
- keep evidence/citations rather than automatically replacing files.

### Distribution
Search around stale PDF/forms, WordPress/plugin ecosystem, website-governance and association/nonprofit communities, free one-domain scan.

### Monetization hypothesis
Free small scan; CA$9 one-off full report; CA$12–29/month recurring monitoring.

### Competition
Download-management systems provide versioning inside their own platforms, but the current search did not identify a strong cross-site crawler focused on detecting publicly served **wrong/outdated document versions** across an existing website.

### Risk
Version inference can be uncertain. Findings need confidence levels and exact evidence; the tool cannot claim that the newest-looking file is legally/currently authoritative without explicit site evidence.

### Verdict
**Advance.** Less crowded than generic broken-link/file monitoring.

---

## 4. Merchant sale-window structured-data validator

### Problem
Google clarified merchant-listing sale-duration markup in July 2026 using `validFrom`, `validThrough` and `priceValidUntil`, aligning structured data more closely with Merchant Center sale periods.

### Competition finding
A current Chrome Web Store product already audits the exact 2026 sale-duration fields along with category, price, shipping, returns and variants. Broader e-commerce schema and mismatch tools also cover adjacent needs.

### Verdict
**Drop as a standalone product.** Useful feature, insufficient wedge.

---

## 5. Shopify customer-account metafield access auditor

### Problem
Shopify now requires definitions and appropriate customer-account permissions for certain metafields, with additional extension declaration requirements arriving in 2027-01.

### Competition / scope finding
The problem is real and current, but the audience is Shopify app developers and the logic fits naturally inside the broader upgrade-readiness scanner.

### Verdict
**Merge into candidate 2** rather than maintain a separate product.

## Stage 3 ranking

1. YouTube podcast RSS preflight checker
2. Shopify app upgrade-readiness scanner
3. Website downloadable-form / PDF version mismatch monitor

## Advance to Stage 4

Advance those three only.

## Verification record

- Last verified: 2026-10-19
- Stage 3 status: complete
- Stage 5: out of scope
