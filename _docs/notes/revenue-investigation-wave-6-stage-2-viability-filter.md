---
title: Revenue Investigation — Wave 6 Stage 2 Viability Filter
summary: Evidence-based filter of Wave 6 candidates, emphasizing low-touch acquisition, current regulatory timing, competition and implementation simplicity.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 234
permalink: /projects/notes/revenue-investigation-wave-6-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-6, viability]
---

# Wave 6 Stage 2 — Viability Filter

## Evidence that changed scoring

- The EU DPP Registry is operational and certain battery passports become mandatory on 18 February 2027. The Commission has already published battery data-point guidance. This creates a near-term readiness market, but the full DPP-platform category is already crowded.
- Canada’s 2026 Customs Tariff has already received multiple in-year revisions (T2026, T2026-1 and T2026-2), supporting a real change-monitoring use case.
- Public procurement pages can accumulate multiple addenda before closing; a current City of Surrey RFP showed four addenda, supporting a narrow monitoring/diff use case.
- Generic spreadsheet-corruption repair is now crowded with browser-local cleaners and damage checkers.
- Generic CSV schema-drift checking also has current CLI/web/Apify substitutes.
- GitHub Actions least-privilege/security is crowded by established security tooling such as Harden-Runner and newer scanners.
- Certificate-of-insurance tracking has current small-business-focused products, reducing novelty.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | DPP API/payload preflight validator | 80 | Advance |
| 2 | Battery DPP field-completeness checker | 79 | Advance |
| 3 | Public tariff-table diff notifier | 78 | Advance |
| 4 | Procurement addendum change detector | 77 | Advance |
| 5 | DPP product-identifier consistency checker | 75 | Advance |
| 6 | DPP revision-diff report generator | 74 | Advance |
| 7 | Product dimensions/weight sanity checker | 72 | Advance cautiously |
| 8 | Variant barcode uniqueness auditor | 71 | Advance cautiously |
| 9 | GTIN bulk validator | 70 | Advance cautiously |
| 10 | Supplier declaration revision monitor | 68 | Hold |
| 11 | SDS revision-date tracker | 68 | Hold |
| 12 | PO vs invoice discrepancy checker | 67 | Hold |
| 13 | Certificate-of-analysis field checker | 67 | Hold |
| 14 | Government CSV schema-change monitor | 64 | Hold; direct substitutes emerging |
| 15 | Spreadsheet identifier-corruption detector | 61 | Drop; crowded |
| 16 | CSV schema-drift checker | 58 | Drop; crowded |
| 17 | Supplier insurance-certificate expiry tracker | 57 | Drop; direct small-business products |
| 18 | Secrets-reference inventory | 56 | Drop/hold; crowded security tooling |
| 19 | GitHub Actions permissions minimizer | 52 | Drop; strong direct substitutes |

## Stage 3 shortlist

1. DPP API/payload preflight validator
2. Battery DPP field-completeness checker
3. Public tariff-table diff notifier
4. Procurement addendum change detector
5. Product dimensions/weight sanity checker

## Current sources

- European Commission DPP timeline and battery guidance
- Regulation (EU) 2023/1542 Article 77
- CBSA Customs Tariff 2026 revision page
- City of Surrey public procurement example with four addenda
- current DPP platform comparisons
- current spreadsheet/schema/GitHub security competitors

## Verification record

- Last verified: 2026-10-19
- Stage 2 status: complete
- Stage 5: out of scope
