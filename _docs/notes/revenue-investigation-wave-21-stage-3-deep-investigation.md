---
title: Revenue Investigation — Wave 21 Stage 3 Deep Investigation
summary: Deep investigation of the strongest automotive and equipment-repair ideas after direct competition checks.
section: notes
doc_type: note
status: active
created: 2026-10-20
updated: 2026-10-20
last_verified: 2026-10-20
owner: High Director
order: 295
permalink: /projects/notes/revenue-investigation-wave-21-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-21, deep-investigation, automotive]
---

# Wave 21 Stage 3 — Deep Investigation

## 1. Ontario estimate / authorization / final-invoice QA preflight

### Problem
Ontario repair shops have deterministic consumer-protection obligations around estimates, customer authorization and final invoices. The shop generally needs a written estimate or an authorized maximum, must preserve authorization evidence, and cannot exceed a written estimate by more than 10% without appropriate authorization. Final invoices also require specific information.

### Product
A preflight/audit utility for shops that already create estimates and invoices elsewhere:
- upload estimate, authorization evidence and final invoice;
- check required administrative fields;
- compare estimate/max-authorized amount against final invoice;
- identify invoice lines not clearly present in the authorized work set;
- check recorded phone/non-written authorization fields;
- flag missing odometer/vehicle/business information;
- produce a review-only compliance checklist with source references.

The tool does not give legal advice or determine whether a customer dispute will succeed.

### Distribution
Ontario repair-shop search, bookkeeping/shop consultants, independent garages and body shops that use generic invoicing/accounting or older shop systems.

### Monetization hypothesis
Free sample/single-document check; CA$5–10 per completed preflight; CA$15–30/month for recurring small-shop usage.

### Competition
Current shop-management platforms connect estimates, authorization, repair orders and invoices, but the current review did not identify a focused independent Ontario-specific checker for shops that want to audit existing documents without replacing their workflow.

### Risk
Legal sensitivity and document variability. The product must use official rule references and conservative deterministic checks only.

### Verdict
**Advance.** Strongest Wave 21 concept.

---

## 2. Small-shop warranty claim evidence preflight

### Problem
Warranty recovery is mature in fleets/dealers, but small independent shops can still lose recoverable money because a failed part, purchase date, mileage, serial/part number, labor record, supplier invoice or return/core evidence is missing when the warranty claim is prepared.

### Product
A supplier/manufacturer-neutral evidence preflight:
- repair order/work order;
- supplier invoice/part purchase date;
- failed-part number/serial where applicable;
- vehicle/equipment VIN/serial and mileage/hours;
- removal/replacement date;
- labor evidence;
- photos/test result where user's warranty process expects them;
- return/core/reference number;
- reimbursement/status tracking.

The user configures the expected evidence for each supplier/warranty program; the tool does not decide eligibility.

### Distribution
Independent repair shops, heavy-equipment service companies, parts distributors and shop bookkeepers.

### Monetization hypothesis
CA$5–15 per claim preflight or CA$15–35/month recurring small-shop plan.

### Competition
Enterprise fleet warranty products automate full recovery, but they target integrated maintenance fleets. The surviving wedge is a lightweight evidence-readiness layer for smaller repair operations that do not have enterprise warranty software.

### Risk
Manufacturer/supplier rules vary widely, which limits automation unless users maintain their own program checklists.

### Verdict
**Advance cautiously.** Clear money-recovery pain with moderate rule-maintenance burden.

---

## 3. Technician clocked-time vs billed-labor audit

### Problem
A technician's payroll clock time, job-clock time and customer-billed/flat-rate hours are different concepts. Shops using separate time-clock, shop-management and accounting systems can struggle to see where labor profitability or payroll anomalies are coming from.

### Product
Upload technician time-clock export plus repair-order/invoice labor export. Normalize by technician/date/job and report:
- paid/clocked hours with unusually low billed hours;
- billed hours with no matching job-time record where one is expected;
- overtime-heavy periods with weak billed-hour recovery;
- job-clock vs customer-billed variance;
- missing technician attribution;
- recurring non-billable gap categories supplied by the user.

The product does not calculate legal payroll entitlement or recommend wage changes.

### Distribution
Independent repair shops, automotive bookkeepers/controllers and search around technician efficiency/productivity reconciliation.

### Monetization hypothesis
CA$15–30 per month-end audit or CA$20–40/month recurring shop plan.

### Competition
Modern shop systems can already separate clocked, assigned and billed hours internally. The niche is an independent reconciliation layer for shops with disconnected systems or outsourced payroll/accounting.

### Risk
Small market once shops consolidate onto modern integrated systems. Labor/payroll interpretation must stay out of scope.

### Verdict
**Advance cautiously.** Useful financial-control tool, but transitional rather than durable.

---

## Dropped after deeper review

### Parts/core/credit leakage audit
Purpose-built auto-body parts-return tools and automotive AP products already track returns, credits and vendor invoice mismatches.

### Repair-order vs supplier-invoice parts variance
Current collision/shop systems increasingly provide three-way matching of PO, receipt and vendor invoice.

### Rental damage/condition reconciliation
Current rental platforms and standalone condition-report products already capture timestamped photos, customer signatures and return damage.

### Calibration certificate / serialized equipment tracking
Current NDT/equipment platforms already manage calibration certificates, serial numbers, status and dispatch conflicts.

## Stage 3 ranking

1. Ontario estimate / authorization / final-invoice QA preflight
2. Small-shop warranty claim evidence preflight
3. Technician clocked-time vs billed-labor audit

## Advance to Stage 4

Advance those three only.

## Verification record

- Last verified: 2026-10-20
- Stage 3 status: complete
- Stage 5: out of scope
