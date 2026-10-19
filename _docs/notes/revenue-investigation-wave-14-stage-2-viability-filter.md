---
title: Revenue Investigation — Wave 14 Stage 2 Viability Filter
summary: Evidence-based filtering of Wave 14 ideas across Android developer verification, EU packaging operations, marketplace trader identity, and seller administration.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 266
permalink: /projects/notes/revenue-investigation-wave-14-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-14, viability]
---

# Wave 14 Stage 2 — Viability Filter

## Evidence that changed scoring

- Android developer verification is now live in selected regions and expands globally in 2027. Google provides package-status and developer-console APIs for registration automation.
- Free single-app verification checkers already exist, so another package-name checker is not differentiated.
- The stronger Android opportunity is portfolio-level administration: multiple apps, signing keys, off-Play channels, registration state, duplicate-package cases and rollout exposure.
- PPWR has been applicable since 12 August 2026 and a large ecosystem of compliance platforms, DoC generators and packaging-data systems already exists. Generic PPWR compliance software is crowded.
- Packaging artwork/specification consistency remains narrower: structured packaging specifications, declarations and actual artwork can drift independently.
- Apple already manages DSA trader verification directly, but organizations distributing through several marketplaces can still face duplicated identity/contact evidence and inconsistent public details.
- Generic seller-verification dashboards overlap with marketplace-native tooling and vendor-risk products; cross-marketplace consistency is the more defensible wedge.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Android verification portfolio / registration inventory | 81 | Advance |
| 2 | Packaging artwork vs material/spec consistency checker | 79 | Advance |
| 3 | Cross-marketplace trader/contact consistency checker | 76 | Advance |
| 4 | Android signing-key/package consistency audit | 75 | Advance; merge into #1 |
| 5 | Packaging revision-to-DoC consistency monitor | 74 | Advance; merge into #2 |
| 6 | Android rollout exposure checker | 73 | Merge into #1 |
| 7 | Packaging supplier-material data gap report | 72 | Advance cautiously |
| 8 | Multi-store compliance-contact workflow | 70 | Merge into #3 |
| 9 | Marketplace business-name/address consistency audit | 69 | Merge into #3 |
| 10 | Packaging BOM-to-artwork consistency report | 69 | Merge into #2 |
| 11 | Android batch-registration preflight | 68 | Feature of #1 |
| 12 | DSA trader information inventory | 66 | Feature of #3 |
| 13 | Packaging label-readiness inventory | 64 | Hold; broader PPWR competition |
| 14 | Trader evidence expiry tracker | 63 | Hold |
| 15 | Packaging DoC evidence index | 61 | Hold; crowded PPWR suites |
| 16 | Generic marketplace verification dashboard | 57 | Drop; native tooling strong |
| 17 | Single-app Android verification checker | 50 | Drop; exact free competitors |
| 18 | Generic PPWR compliance dashboard | 45 | Drop; crowded |

## Stage 3 shortlist

1. Android verification portfolio / registration inventory
2. Packaging artwork vs material/spec consistency checker
3. Cross-marketplace trader/contact consistency checker
4. Packaging supplier-material data gap report
5. Trader evidence expiry tracker

## Verification record

- Last verified: 2026-10-19
- Stage 2 status: complete
- Stage 5: out of scope
