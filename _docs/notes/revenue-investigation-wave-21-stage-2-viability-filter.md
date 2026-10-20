---
title: Revenue Investigation — Wave 21 Stage 2 Viability Filter
summary: Evidence-based filtering of automotive and equipment repair/rental ideas, emphasizing independent audit/reconciliation workflows rather than full shop or rental platforms.
section: notes
doc_type: note
status: active
created: 2026-10-20
updated: 2026-10-20
last_verified: 2026-10-20
owner: High Director
order: 294
permalink: /projects/notes/revenue-investigation-wave-21-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-21, viability, automotive]
---

# Wave 21 Stage 2 — Viability Filter

## Evidence that changed scoring

- Full Canadian auto-repair software already connects estimates, authorization, repair orders, parts, labor, invoices and payments. Generic shop workflow products are crowded.
- Ontario repair rules create a deterministic QA niche: shops generally need a compliant written estimate or authorized maximum, authorization records, and a final invoice that does not exceed the estimate by more than 10% without appropriate authorization.
- Equipment-rental condition/damage evidence is already served by dedicated standalone and platform-integrated products.
- Core-charge/parts-credit tracking now has exact lightweight products, while automotive AP tools increasingly reconcile repair orders, vendor invoices, statements and credits.
- Small-shop warranty claims are no longer a clean gap: current Canadian repair software already supports warranty-claim submission, and fleet warranty-recovery services independently audit historical repairs.
- Technician payroll time, job-clock time and customer-billed labor remain distinct datasets; disconnected shops can still have a month-end reconciliation gap.
- Outsourced/sublet work creates another narrow reconciliation problem: the shop receives a vendor invoice, passes work through to the customer, and can lose margin when cost, markup, authorization or invoice lines do not reconcile.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Ontario estimate/authorization/final-invoice QA preflight | 82 | Advance |
| 2 | Technician clocked-time vs billed-labor audit | 77 | Advance |
| 3 | Outsourced/sublet invoice vs customer billing audit | 75 | Advance |
| 4 | Customer-authorized work vs final invoice consistency checker | 74 | Merge into #1 |
| 5 | Unbilled diagnostic/inspection line inventory | 70 | Hold |
| 6 | Repair-order vs supplier invoice parts-cost variance | 68 | Hold; current AP tools overlap |
| 7 | Small-shop warranty claim evidence preflight | 65 | Drop/hold; direct current competition |
| 8 | Parts/core/credit leakage audit | 63 | Drop; exact current products |
| 9 | Calibration certificate-to-asset matcher | 61 | Hold; mature asset/calibration systems |
| 10 | Loaner fuel/mileage return audit | 60 | Hold |
| 11 | Rental damage evidence reconciliation | 55 | Drop; direct current competition |
| 12 | Rental off-rent vs billed-through checker | 54 | Drop; rental platforms cover it |
| 13 | Generic digital vehicle inspection | 48 | Drop; crowded |
| 14 | Full repair-shop workflow software | 45 | Drop; mature market |

## Stage 3 shortlist

1. Ontario estimate/authorization/final-invoice QA preflight
2. Technician clocked-time vs billed-labor audit
3. Outsourced/sublet invoice vs customer billing audit
4. Unbilled diagnostic/inspection line inventory
5. Loaner fuel/mileage return audit

## Verification record

- Last verified: 2026-10-20
- Stage 2 status: complete
- Stage 5: out of scope
