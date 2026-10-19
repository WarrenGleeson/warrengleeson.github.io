---
title: Revenue Investigation — Wave 11 Stage 2 Viability Filter
summary: Evidence-based filtering of Wave 11 ideas across CRA operations, AI-model lifecycle, Microsoft Graph/Entra migrations and dependency-support tooling.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 254
permalink: /projects/notes/revenue-investigation-wave-11-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-11, viability]
---

# Wave 11 Stage 2 — Viability Filter

## Evidence that changed scoring

- CRA Article 14 reporting obligations are already live, with ENISA operating the Single Reporting Platform and commercial CRA platforms now offering reporting, SBOM and evidence workflows. Generic CRA reporting dashboards are therefore crowded.
- The CRA still creates narrower operational needs around support periods, product/dependency lifecycle evidence and published support-end dates that full compliance platforms may not solve simply for smaller manufacturers.
- OpenAI has multiple model families/snapshots scheduled for retirement between October 2026 and April 2027. GitHub/Copilot and other AI platforms also retire models, confirming that model lifecycle churn is recurring rather than one-off.
- Microsoft retired the legacy Graph security alerts API on October 15, 2026 and continues to maintain Graph deprecation/version policies. A one-off alerts-v1 scanner is now late, but a broader Microsoft Graph/Entra deprecated-endpoint source scanner remains plausible.
- Microsoft Entra also retired service-principal-less authentication in March 2026, showing that identity-related breaking changes can require tenant/code review.
- Generic SBOM generation and CRA compliance management are already crowded with current products.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Multi-provider AI model sunset source scanner | 82 | Advance |
| 2 | Microsoft Graph/Entra deprecated endpoint/auth source scanner | 79 | Advance |
| 3 | CRA product support-period vs dependency-support checker | 78 | Advance |
| 4 | OpenAI model hard-code detector | 76 | Advance; merge into #1 |
| 5 | AI model migration regression-test pack | 75 | Advance cautiously |
| 6 | AI fine-tuned base-model deprecation tracker | 74 | Advance cautiously; feature of #1 |
| 7 | CRA support-end-date disclosure checker | 72 | Advance cautiously |
| 8 | Microsoft Graph SDK support checker | 70 | Feature of #2 |
| 9 | CRA vulnerability reporting timeline workspace | 66 | Hold; commercial platforms emerging |
| 10 | CRA top-level SBOM completeness checker | 65 | Hold; crowded SBOM tooling |
| 11 | CRA Annex II completeness checker | 64 | Hold |
| 12 | CRA vulnerability disclosure-policy preflight | 63 | Hold |
| 13 | Legacy Graph alerts v1 scanner | 60 | Drop; retirement already passed |
| 14 | Entra service-principal-less auth checker | 58 | Drop as standalone; retirement already passed |
| 15 | Generic SBOM format converter | 52 | Drop; commodity |
| 16 | Generic runtime/framework EOL scanner | 51 | Drop; broad established tooling |
| 17 | Generic API sunset scanner | 50 | Drop; insufficient wedge |
| 18 | CRA all-in-one compliance dashboard | 45 | Drop; direct current competition |

## Stage 3 shortlist

1. Multi-provider AI model sunset source scanner
2. Microsoft Graph/Entra deprecated endpoint/auth source scanner
3. CRA product support-period vs dependency-support checker
4. AI model migration regression-test pack
5. CRA support-end-date disclosure checker

## Verification record

- Last verified: 2026-10-19
- Stage 2 status: complete
- Stage 5: out of scope
