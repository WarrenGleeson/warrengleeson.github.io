---
title: Revenue Investigation — Wave 9 Stage 2 Viability Filter
summary: Evidence-based filtering of Wave 9 ideas across cloud lifecycle exposure, EU customs PID readiness, Canadian procurement supplier operations and adjacent operational utilities.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 246
permalink: /projects/notes/revenue-investigation-wave-9-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-9, viability]
---

# Wave 9 Stage 2 — Viability Filter

## Evidence that changed scoring

- AWS now publishes a Product Lifecycle page, lifecycle-update feed and machine-readable end-of-support data. AWS also has sample lifecycle-tracker projects. A generic AWS EOL dashboard therefore has little value; the surviving wedge is mapping lifecycle events directly to a customer's Terraform/CloudFormation/code dependencies.
- AWS announced new September 2026 service availability changes, including services entering maintenance and sunset, which confirms recurring change volume.
- EU product identifiers become mandatory for relevant B2C e-commerce customs declarations on 1 November 2026. However, free/paid catalog checkers and shipping platforms are already appearing, including a Shopify-focused PID checker and carriers that can generate/handle identifiers. Generic PID readiness is therefore less differentiated.
- Canada's Buy Canadian policy threshold for strategic federal procurement dropped from $25M to $5M in June 2026, expanding the number of procurements where Canadian supplier/content rules can apply. Canadian Value-Added can represent 25% of offer evaluation and requires line-item attestations/evidence.
- Canada's Vendor Performance Management policy took effect September 18, 2026 and is being phased across departments. Performance is assessed across cost, schedule, quality and management, and results can inform future bid evaluations.
- Generic Canadian RFP screening/compliance-matrix tools are already available (for example BidFit/TenderFit), so another broad tender summarizer is not attractive.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | AWS service-sunset exposure scanner for IaC | 81 | Advance |
| 2 | Canadian Value-Added evidence/calculation workspace | 79 | Advance |
| 3 | Federal VPM supplier scorecard evidence organizer | 77 | Advance |
| 4 | AWS lifecycle watchlist for MSPs | 75 | Advance; merge into #1 later |
| 5 | Buy Canadian solicitation applicability checker | 73 | Advance cautiously |
| 6 | EU PID carrier-export transformation tool | 72 | Advance cautiously |
| 7 | EU PID generic catalog readiness checker | 68 | Hold; direct competitors emerging |
| 8 | AWS resource-to-migration-guide mapper | 68 | Hold; feature of #1 |
| 9 | Canada VPM contract-applicability checker | 67 | Hold; feature of #3 |
| 10 | International shipment missing-customs-data preflight | 66 | Hold; broad logistics competition |
| 11 | Carrier surcharge invoice anomaly checker | 65 | Hold; established audit category |
| 12 | Public downloadable-document revision inventory | 64 | Hold; overlaps Wave 7 |
| 13 | CanadaBuys addendum diff monitor | 63 | Hold; broad tender tools emerging |
| 14 | Bid requirement/evidence matrix generator | 58 | Drop; direct current tools |
| 15 | Generic API changelog-to-code rules engine | 57 | Drop/hold; too broad |
| 16 | AWS generic EOL dashboard | 54 | Drop; official/open-source substitutes |
| 17 | EU €3-duty calculator | 48 | Drop; multiple exact free calculators |
| 18 | Generic PID Shopify checker | 46 | Drop; direct commercial substitute |

## Stage 3 shortlist

1. AWS service-sunset exposure scanner for Terraform/CloudFormation
2. Canadian Value-Added evidence/calculation workspace
3. Federal Vendor Performance Management supplier evidence organizer
4. EU PID carrier-export transformation tool
5. Buy Canadian solicitation applicability checker

## Verification record

- Last verified: 2026-10-19
- Stage 2 status: complete
- Stage 5: out of scope
