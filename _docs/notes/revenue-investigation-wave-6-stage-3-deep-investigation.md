---
title: Revenue Investigation — Wave 6 Stage 3 Deep Investigation
summary: Deep investigation of five Wave 6 finalists across demand timing, competition, low-touch acquisition and implementation risk.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 235
permalink: /projects/notes/revenue-investigation-wave-6-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-6, deep-investigation]
---

# Wave 6 Stage 3 — Deep Investigation

## 1. DPP API / payload preflight validator

### Problem
Battery manufacturers and importers preparing for the 18 February 2027 battery-passport requirement need to understand whether their product records contain the required data and whether identifiers / payloads are structurally ready. Full DPP platforms already exist, but a neutral preflight tool can sit before vendor selection.

### Product
Upload or paste a CSV/JSON payload, choose battery category, and receive a deterministic readiness report against the current Commission guidance: required, conditional, later-applicable and missing fields; identifier format checks; duplicate/invalid references; and an exportable issue list.

### Distribution
Search-driven pages around battery-passport data fields, schema validation and February 2027 readiness; developer/API directories; possible freemium web checker.

### Monetization hypothesis
Free single-record check; €9–19 bulk file check; €29–49/month saved schemas/API/batch validation.

### Risk
The regulation and technical guidance are still evolving. The tool must version every rule and avoid presenting itself as legal certification or as an official EU validator.

### Verdict
Strongest Wave 6 concept because timing is immediate and the scope can remain narrow.

---

## 2. Battery DPP field-completeness checker

### Problem
Commission guidance distinguishes fields required in February 2027, conditional fields and information whose legal application comes later. This makes spreadsheet readiness difficult for smaller operators.

### Product
A browser-first spreadsheet checker focused only on completeness/applicability, with a clear evidence trail to the relevant guidance version.

### Distribution
SEO around battery-passport checklist, data points and readiness; downloadable sample templates.

### Monetization hypothesis
Free checklist; paid bulk workbook audit or team template pack.

### Risk
Substantial overlap with the broader payload-validator concept. Better treated as the nontechnical front end of the same product rather than a separate business.

### Verdict
Merge into candidate 1 for Stage 4.

---

## 3. Canadian tariff-table diff notifier

### Problem
CBSA’s Customs Tariff can change during the year. In 2026 the public tariff page already lists T2026, T2026-1 and T2026-2 with different effective dates. Importers and customs-adjacent businesses need to notice changes affecting relevant HS codes without manually diffing large tariff files.

### Product
Track selected HS chapters/codes and produce a factual before/after change report when CBSA publishes a revision: text changes, rates/treatments where machine-readable, effective date and direct official source links.

### Distribution
Search pages for “Canada tariff change [HS code]”; self-serve watchlists; trade/compliance communities; possible API/feed.

### Monetization hypothesis
Free 1-code watch; CA$9–19/month for 25–100 codes; one-off CA$10 diff report.

### Risk
Customs brokers and enterprise trade platforms already monitor tariff changes. Need to target the low-cost self-serve gap and avoid interpreting classification or legal effect.

### Verdict
Advance.

---

## 4. Procurement addendum change detector

### Problem
Public RFPs may accumulate several addenda before close. Vendors must determine what changed across PDFs/attachments and whether deadlines, forms, requirements or pricing instructions were affected.

### Product
User supplies a procurement opportunity URL. The service monitors the public page, captures new addenda, produces a cited change summary and highlights changed dates/files/requirements. It does not write the proposal.

### Distribution
Search around RFP addendum monitoring, browser bookmarklet/extension, procurement communities and self-serve watch URLs.

### Monetization hypothesis
CA$5–10 per watched opportunity or CA$19–39/month for a small watchlist.

### Risk
Portal diversity and anti-bot restrictions create maintenance burden. A narrow initial source set is required.

### Verdict
Advance, but only with bounded source coverage.

---

## 5. Product dimensions / weight sanity checker

### Problem
Bad dimensions and weights create shipping-rate, fulfillment and marketplace-feed problems. Existing catalog tools often flag missing values but do not focus on plausibility and peer anomalies.

### Product
Upload catalog CSV or connect a store; identify missing values, impossible units, large outliers within product families and dimensional-weight anomalies. No automated correction without user approval.

### Distribution
Shopify App Store/search, free CSV checker, fulfillment/shipping content.

### Monetization hypothesis
Free small catalog audit; CA$9 one-off export; CA$15–29/month scheduled audits.

### Risk
Adjacent catalog-health and shipping-optimization apps are plentiful. Need a very clear anomaly-detection wedge.

### Verdict
Hold as fourth-ranked candidate.

## Stage 3 ranking

1. DPP readiness/payload validator (including field-completeness checker)
2. Canadian tariff-table diff notifier
3. Procurement addendum change detector
4. Product dimensions/weight sanity checker

## Advance to Stage 4

Advance the top three only.

## Verification record

- Last verified: 2026-10-19
- Stage 3 status: complete
- Stage 5: out of scope
