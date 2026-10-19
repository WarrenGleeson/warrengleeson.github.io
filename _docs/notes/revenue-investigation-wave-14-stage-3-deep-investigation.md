---
title: Revenue Investigation — Wave 14 Stage 3 Deep Investigation
summary: Deep investigation of Wave 14 finalists after direct competition checks across Android verification, packaging artwork, and marketplace trader identity operations.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 267
permalink: /projects/notes/revenue-investigation-wave-14-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-14, deep-investigation]
---

# Wave 14 Stage 3 — Deep Investigation

## 1. Android off-Play verification portfolio manager

### Problem
Android developer verification is now enforced in selected regions and expands globally in 2027. Google offers status/registration APIs, but organizations distributing multiple apps outside Play still need a portfolio view of package names, signing certificates, channels, registration state, duplicate-package cases and rollout exposure.

### Product
A local/admin workspace that imports a portfolio of Android apps, queries official registration status where authorized, records signing-certificate fingerprints and distribution channels, and produces a registration/action matrix. CI checks can fail a release when the artifact's package/certificate no longer matches the recorded registration state.

### Distribution
Android developer search, GitHub/CI integration, enterprise Android communities and alternative-store operators.

### Monetization hypothesis
Free small portfolio; CA$10–25/month for monitored portfolios/CI history; higher tier for alternative stores or enterprise app teams.

### Competition
Free single-app checkers already exist and Google provides the underlying APIs. The surviving wedge is **portfolio administration + CI consistency + multi-channel exposure**, not status lookup.

### Risk
Google can expand native portfolio UI/API tooling. Most Play-only developers already have automatic registration, so target users must be off-Play, enterprise, multi-store or mixed-distribution teams.

### Verdict
**Advance.** Strongest Wave 14 concept if tightly targeted.

---

## 2. Cross-marketplace trader/contact consistency checker

### Problem
App stores and online marketplaces increasingly require verified trader/business identity and public contact information. A company distributing through multiple platforms can end up with inconsistent legal names, addresses, support contacts or public trader details across storefronts and compliance portals.

### Product
A user-maintained canonical trader/business profile plus platform-specific evidence snapshots. The checker compares declared/public details across supported stores and flags mismatches, missing verification evidence, stale contacts and app/storefronts not linked to the intended legal entity.

### Distribution
App developer/seller operations search, marketplace consultants, templates and self-serve profile audits.

### Monetization hypothesis
Free 1–2 storefront audit; CA$15–30 one-off portfolio report; CA$10–25/month for monitored profiles/evidence renewal.

### Competition
Marketplaces perform their own verification, but that does not solve cross-platform consistency. The current review did not surface a strong lightweight product focused on maintaining one canonical trader identity across multiple app/commerce marketplaces.

### Risk
The tool cannot determine legal trader status and must not replace marketplace verification. Public scraping/access varies by platform, so manual/API-assisted evidence may be necessary.

### Verdict
**Advance.** More durable than a platform-specific DSA checklist.

---

## 3. Android Enterprise/private-app verification exposure mapper

### Problem
Android verification treatment differs by distribution path and device-management state. Private apps on fully managed devices or Work Profiles can be exempt while apps on unmanaged certified devices may require verified registration. IT teams can therefore misclassify which private/internal apps need action before broader 2027 rollout.

### Product
A self-serve inventory that maps each internal/private app to distribution source, device ownership/management mode, user population, package registration status and signing key, then outputs “registration required / currently exempt / review required” with official source references.

### Distribution
Android Enterprise/MDM administrator search, MSP communities and downloadable migration worksheet.

### Monetization hypothesis
Free small inventory; CA$20–40 one-off estate report; CA$15–30/month for MSP/multi-estate tracking.

### Competition
Google provides detailed guidance but the current review did not identify a dedicated estate-level applicability mapper. This is more operationally specific than a generic registration checker.

### Risk
MDM/device state can change and must be supplied accurately. The commercial window is strongest during the 2026–2027 rollout.

### Verdict
**Advance cautiously.** Narrow but timely enterprise niche.

---

## 4. Packaging artwork vs material/spec consistency checker

### Competition finding
Current products already perform direct artwork-to-product-spec comparisons. GoVisually documents a live-text product-spec comparison workflow, while TraceGains and Esko connect packaging specifications to artwork approval. Broader PPWR platforms also cover packaging records and declarations.

### Verdict
**Drop as standalone.** Insufficient differentiation.

---

## 5. Packaging supplier-material data gap report

### Competition finding
Supplier-data collection is a core feature of current PPWR platforms, including enterprise supplier networks and newer self-serve tools. The category is already crowded.

### Verdict
**Drop/hold.** No clean wedge identified.

## Stage 3 ranking

1. Android off-Play verification portfolio manager
2. Cross-marketplace trader/contact consistency checker
3. Android Enterprise/private-app verification exposure mapper

## Advance to Stage 4

Advance those three only.

## Verification record

- Last verified: 2026-10-19
- Stage 3 status: complete
- Stage 5: out of scope
