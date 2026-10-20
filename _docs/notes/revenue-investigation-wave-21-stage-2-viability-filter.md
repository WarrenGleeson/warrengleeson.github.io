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

- Full Canadian auto-repair software already connects estimates, customer authorization, repair orders, parts, labor, invoices and payments. Generic workflow products are therefore crowded.
- Ontario repair rules create a deterministic QA niche: shops generally need a compliant written estimate or authorized maximum, authorization records, and a final invoice that does not exceed the estimate by more than 10% without additional authorization.
- Equipment-rental inspection/damage evidence is already served by dedicated products, including timestamped condition reports, signatures and AI damage detection.
- Automotive AP/parts reconciliation is increasingly covered by purpose-built tools, including three-way parts invoice matching and return/credit tracking.
- Fleet warranty recovery is a mature enterprise category, but smaller independent shops may still lack a simple preflight for manufacturer/extended-warranty evidence before a claim is submitted.
- Technician payroll time, flagged/billed labor and job-clock time are distinct datasets; integrated shop systems can report them, but disconnected small shops can still have a reconciliation gap.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Ontario estimate/authorization/final-invoice QA preflight | 82 | Advance |
| 2 | Small-shop warranty claim evidence preflight | 78 | Advance |
| 3 | Technician clocked-time vs billed-labor audit | 76 | Advance |
| 4 | Customer-authorized work vs final invoice consistency checker | 75 | Merge into #1 |
| 5 | Warranty reimbursement vs repair-order reconciliation | 73 | Merge into #2 |
| 6 | Outsourced/sublet invoice vs customer billing audit | 71 | Advance cautiously |
| 7 | Parts/core/credit leakage audit | 68 | Hold; direct competition emerging |
| 8 | Repair-order vs supplier invoice variance checker | 66 | Hold; three-way-match tools exist |
| 9 | Calibration certificate-to-asset matcher | 63 | Hold; mature asset/calibration systems |
| 10 | Rental damage evidence reconciliation | 60 | Drop; direct current competition |
| 11 | Rental off-rent vs billed-through checker | 58 | Drop; dedicated rental audit products exist |
| 12 | Generic digital vehicle inspection | 49 | Drop; crowded |
| 13 | Full repair-shop workflow software | 46 | Drop; mature market |
| 14 | Full rental-management platform | 44 | Drop; mature market |

## Stage 3 shortlist

1. Ontario estimate/authorization/final-invoice QA preflight
2. Small-shop warranty claim evidence preflight
3. Technician clocked-time vs billed-labor audit
4. Outsourced/sublet invoice vs customer billing audit
5. Warranty reimbursement reconciliation

## Verification record

- Last verified: 2026-10-20
- Stage 2 status: complete
- Stage 5: out of scope
