---
title: Revenue Investigation — Wave 26 Stage 2 Viability Filter
summary: Evidence-based filtering of small manufacturing/fabrication ideas, emphasizing engineering-change impact, supplier requirement flowdown and shipment-document readiness rather than ERP/PLM/QMS replacement.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 314
permalink: /projects/notes/revenue-investigation-wave-26-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-26, viability, manufacturing]
---

# Wave 26 Stage 2 — Viability Filter

## Evidence that changed scoring

- Small-shop BOM/revision-control, quoting and digital-traveler software are now well served, including low-cost/open-source options.
- Quote-vs-customer-PO comparison has an exact current manufacturing product that compares scope, revisions, delivery, payment, warranty and other terms before order release.
- Material-certificate matching is also being automated by current products that read mill certificates, match PO lines and check heat numbers against receipts.
- Drawing-to-inspection-plan extraction has direct tools that balloon drawings and generate inspection characteristics automatically.
- Current manufacturing guidance still identifies engineering changes that fail to propagate to open travelers, purchasing, outside processes and inspection as a recurring operational failure.
- ISO-oriented supplier controls require applicable drawings/specifications/process/acceptance requirements to be communicated to external providers; the practical gap is often whether the released supplier PO actually carries the customer requirement set.
- Shipment/certificate packs remain a recurring quality gate: parts, revision, lots/heats, quantities, CoC/material/process certificates and customer-specific records must line up before release.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Engineering-change open-job impact audit | 82 | Advance |
| 2 | Customer-requirement to supplier/outsource PO flowdown audit | 80 | Advance |
| 3 | Shipment certificate/document-pack readiness preflight | 77 | Advance |
| 4 | Drawing/BOM/traveler revision consistency audit | 75 | Merge into #1 |
| 5 | Supplier substitution/deviation effectivity tracker | 74 | Advance cautiously; merge into #1/#2 |
| 6 | Customer-required cert list vs shipment pack audit | 73 | Merge into #3 |
| 7 | Material cert vs receiving/job traceability audit | 70 | Hold; direct automation competition |
| 8 | Supplier acknowledgment vs PO diff | 68 | Hold |
| 9 | Critical-characteristic inspection coverage audit | 66 | Hold; drawing inspection tools strong |
| 10 | Accepted quote vs customer PO diff | 52 | Drop; exact current competitor |
| 11 | Generic BOM/revision manager | 49 | Drop; mature/low-cost competition |
| 12 | Digital traveler platform | 47 | Drop; crowded |
| 13 | Material certificate matching/filing | 46 | Drop; direct competitor |
| 14 | Drawing-to-inspection-plan generator | 44 | Drop; exact competitor |

## Stage 3 shortlist

1. Engineering-change open-job impact audit
2. Customer-requirement to supplier/outsource PO flowdown audit
3. Shipment certificate/document-pack readiness preflight
4. Supplier substitution/deviation effectivity tracker
5. Supplier acknowledgment vs PO diff

## Verification record
- Last verified: 2026-10-25
- Stage 2 status: complete
- Stage 5: out of scope
