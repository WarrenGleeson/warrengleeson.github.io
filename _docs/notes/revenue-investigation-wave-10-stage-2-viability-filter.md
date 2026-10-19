---
title: Revenue Investigation — Wave 10 Stage 2 Viability Filter
summary: Evidence-based filtering of Wave 10 ideas across e-invoicing, app-store commercial terms, Play reporting changes, accessibility operations and payment integration tooling.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 250
permalink: /projects/notes/revenue-investigation-wave-10-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-10, viability]
---

# Wave 10 Stage 2 — Viability Filter

## Evidence that changed scoring

- Apple introduced unified EU business terms effective 1 October 2026 with materially different commissions for Apple IAP, alternative payment processing, out-of-app offers and alternative distribution. Developers choosing payment options must maintain those choices for 12 months.
- Google Play now requires US external-content-link participants to report transactions / download events and pay applicable service fees, with reporting/payment deadlines and multiple fee cases based on transaction/install type.
- Google Play also changed financial-report fee-description values in October 2026, creating a concrete schema-regression risk for automated finance pipelines.
- Germany/Europe e-invoicing is already served by many mature platforms and EN 16931 validators, so generic validation/readiness products are crowded. Narrow reconciliation/explanation utilities remain more plausible.
- Accessibility monitoring is heavily served by established products and W3C-listed tools; generic site scanning and statement monitoring are not attractive standalone entries.
- Adyen already provides API release notes and an API Diff Tool, reducing the value of generic payment-API diff products.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Apple EU payment-option margin/commitment modeller | 81 | Advance |
| 2 | Google Play external-content-link reporting/fee reconciler | 80 | Advance |
| 3 | Google Play financial-report schema regression checker | 77 | Advance |
| 4 | PDF invoice vs structured e-invoice reconciliation checker | 75 | Advance |
| 5 | App Review guideline change impact scanner | 74 | Advance |
| 6 | Google Play destination-requirements checker | 72 | Advance cautiously |
| 7 | Apple alternative-payment support-obligations checklist | 71 | Advance cautiously; feature of #1 |
| 8 | E-invoice rejection-reason normalizer | 70 | Advance cautiously |
| 9 | Apple payment-option commitment tracker | 69 | Merge into #1 |
| 10 | Play external-transaction preflight | 69 | Merge into #2 |
| 11 | Merchant/app fee scenario comparer | 67 | Hold; broad |
| 12 | Payment webhook schema-drift monitor | 66 | Hold; established tools exist |
| 13 | Adyen API/component compatibility checker | 64 | Hold; official diff tooling strong |
| 14 | Germany e-invoice readiness checker | 61 | Hold; crowded |
| 15 | EN 16931 generic validator | 58 | Drop; mature category |
| 16 | Accessibility statement freshness monitor | 56 | Drop; low willingness to pay / broad monitoring substitutes |
| 17 | Generic accessibility site monitor | 52 | Drop; crowded |
| 18 | Payment release-note scanner | 51 | Drop; too broad |

## Stage 3 shortlist

1. Apple EU payment-option margin/commitment modeller
2. Google Play external-content-link reporting/fee reconciler
3. Google Play financial-report schema regression checker
4. PDF invoice vs structured e-invoice reconciliation checker
5. App Review guideline change impact scanner

## Verification record

- Last verified: 2026-10-19
- Stage 2 status: complete
- Stage 5: out of scope
