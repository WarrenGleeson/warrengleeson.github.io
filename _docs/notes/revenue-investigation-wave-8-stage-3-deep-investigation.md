---
title: Revenue Investigation — Wave 8 Stage 3 Deep Investigation
summary: Deep investigation of the strongest Wave 8 platform-change readiness opportunities after direct-substitute checks.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 243
permalink: /projects/notes/revenue-investigation-wave-8-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-8, deep-investigation]
---

# Wave 8 Stage 3 — Deep Investigation

## 1. Google Ads API version-upgrade source scanner

### Problem
Google Ads API v26 shipped on October 14, 2026 with breaking changes, while older versions have published sunset dates. Google provides excellent version diffs and upgrade documentation, but developers still have to determine which removed/changed services, fields, enums and behaviors their own integration actually uses.

### Product
A repository scanner/GitHub Action that detects Google Ads API usage, current client-library/API version, GAQL fields, service/method references and selected config patterns, then maps them to a target version's official breaking changes/deprecations.

### Distribution
GitHub Marketplace, developer search, release-specific SEO pages and free CLI/Action.

### Monetization hypothesis
Free single-repo scan; CA$10–25/month organization history/multi-repo policy dashboard; optional one-off upgrade report.

### Competition
Official Google docs provide diffs and upgrade guidance, but the current search did not surface a strong exact source-code impact scanner. The wedge is not explaining the release notes—it is answering “which of these changes affect this repository?”

### Risks
Rules require maintenance every major release; static analysis must be conservative and source-cited.

### Verdict
**Advance.** Strongest Wave 8 concept.

---

## 2. Amazon.ca lithium-battery seller readiness workspace

### Problem
Amazon.ca introduced current compliance requirements for rechargeable lithium-battery smart-home, consumer-electronics and home-appliance categories. Sellers may need listing attributes, authorized TIC validation, recent accredited test reports and, for some lithium-ion products, UN 38.3 and Battery Test Summary documentation. Amazon can suppress noncompliant listings.

### Product
A read-only readiness workspace that lets a seller import a catalog/export, classify likely affected SKUs based on Amazon's published scope, record whether required model/manufacturer attributes and evidence exist, track report dates, and generate a per-SKU evidence checklist for the authorized TIC process.

The product must never alter, fabricate or “improve” compliance documents and must never claim a product is legally compliant.

### Distribution
Amazon seller search/content, seller communities, app/integration directories where permitted, and self-serve CSV audit.

### Monetization hypothesis
Free small catalog check; CA$19–49 one-off readiness report; CA$15–39/month evidence-expiry/status monitoring for larger catalogs.

### Competition
Amazon supplies policy/help pages and TIC providers perform actual validation, but the current search did not reveal a strong exact seller-side inventory/readiness workspace for this new Canada-specific rule. TIC services are complements rather than substitutes.

### Risks
High compliance sensitivity, policy changes and product-scope ambiguity. Classification must be presented as “likely affected / review required,” not authoritative.

### Verdict
**Advance cautiously.** Clear pain and timing, but higher policy/legal risk than rank 1.

---

## 3. IRIS schema/business-rule local diff + impact report

### Problem
FIRE is retiring and IRIS becomes the filing system for affected information returns in filing season 2027. IRS publishes multiple schema/business-rule versions and known issues. The actual schema/business-rule package is distributed through the Secure Object Repository to authorized developers/transmitters and can change during the year.

### Product
A local-only developer utility into which an authorized user drops two legitimately obtained IRIS schema/business-rule packages. It produces structural diffs, new/removed/changed rule IDs, effective-version notes and an impact checklist. Optional repository scan can map known field/form references to likely affected code paths.

### Distribution
Developer/tax-software search, GitHub CLI, IRS filing-software communities. No redistribution of restricted SOR packages.

### Monetization hypothesis
Free local diff; CA$15–30 per team/month for version history, repository impact mapping and collaborative annotations.

### Competition
IRS QuickAlerts already provides notifications, and third parties already validate IRIS files. The surviving wedge is **private local comparison of the authorized rule packages plus code-impact mapping**, not alerts or filing validation.

### Risks
Small specialized market. Tool must never upload or redistribute restricted IRS packages or taxpayer data by default. Local processing is preferable.

### Verdict
**Advance.** Niche but technically specific and recurring.

---

## 4. Amazon category policy-change impact scanner

### Problem
Amazon seller policies change frequently across titles, bundles, insurance and category-specific compliance. Operators need to know which catalog items are plausibly affected.

### Finding
The pain is real, but policy-specific tools can appear quickly—as demonstrated by the exact Bundle Watch competitor for the January 2027 bundle rule. A broad policy engine would have a high maintenance burden and risks overclaiming applicability.

### Verdict
**Hold.** Individual narrowly scoped policy tools may be viable; a broad scanner is not a first choice.

---

## 5. Stripe API changelog impact scanner

### Problem
Stripe ships regular API/platform changes and maintains an OpenAPI specification.

### Competition finding
Stripe's current release process and developer changelog already emphasizes version-specific impact and step-by-step upgrade guidance. The open specification also makes generic diffing straightforward.

### Verdict
**Drop/hold.** Insufficient differentiation relative to official tooling unless a future narrower use case emerges.

## Stage 3 ranking

1. Google Ads API version-upgrade source scanner
2. Amazon.ca lithium-battery seller readiness workspace
3. IRIS schema/business-rule local diff + impact report

## Advance to Stage 4

Advance those three only.

## Verification record

- Last verified: 2026-10-19
- Stage 3 status: complete
- Stage 5: out of scope
