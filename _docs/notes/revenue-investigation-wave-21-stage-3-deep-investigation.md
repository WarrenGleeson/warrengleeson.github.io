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
Ontario repair shops have deterministic consumer-protection obligations around estimates, customer authorization and final invoices. Shops generally need a written estimate or an authorized maximum, must preserve authorization evidence, and cannot exceed a written estimate by more than 10% without appropriate authorization. Final invoices also require specific information.

### Product
A preflight/audit utility for shops that already create estimates and invoices elsewhere:
- upload estimate, authorization evidence and final invoice;
- check required administrative fields;
- compare estimate/max-authorized amount against final invoice;
- identify invoice lines not clearly present in the authorized work set;
- check recorded phone/non-written authorization fields;
- flag missing odometer/vehicle/business information;
- produce a review-only checklist with source references.

The tool does not give legal advice or determine whether a customer dispute will succeed.

### Distribution
Ontario repair-shop search, automotive bookkeepers/shop consultants, independent garages and body shops using generic invoicing/accounting or older shop systems.

### Monetization hypothesis
Free sample/single-document check; CA$5–10 per preflight; CA$15–30/month recurring small-shop usage.

### Competition
Current shop-management platforms connect estimates, authorizations and invoices, but the current review did not identify a focused independent Ontario-specific checker for shops that want to audit existing documents without replacing their workflow.

### Risk
Legal sensitivity and document variability. Only deterministic checks against official requirements should be presented as definite findings.

### Verdict
**Advance.** Strongest Wave 21 concept.

---

## 2. Technician clocked-time vs billed-labor audit

### Problem
Payroll clock time, job-clock time and customer-billed/flat-rate hours are different datasets. Shops using separate time-clock, shop-management and accounting systems can struggle to explain weak labor recovery, overtime, missing technician attribution or jobs with unusual billed-vs-worked variance.

### Product
Upload technician time-clock export plus repair-order/invoice labor export, optionally job-clock data. Normalize by technician/date/job and report:
- paid/clocked hours with unusually low billed hours;
- billed hours with no matching job-time record where expected;
- overtime-heavy periods with weak billed-hour recovery;
- job-clock vs customer-billed variance;
- missing technician attribution;
- user-defined non-billable categories.

The product does not calculate legal payroll entitlement or recommend compensation changes.

### Distribution
Independent repair shops, automotive bookkeepers/controllers and search around flagged vs clocked vs billed technician hours.

### Monetization hypothesis
CA$15–30 per month-end audit or CA$20–40/month recurring shop plan.

### Competition
Modern shop systems report these metrics internally, but the niche remains for disconnected shops and outsourced bookkeeping/accounting workflows.

### Risk
Transitional market as more shops move to integrated systems; payroll/labor-law interpretation must remain out of scope.

### Verdict
**Advance cautiously.** Clear financial-control pain, moderate durability.

---

## 3. Outsourced / sublet invoice vs customer billing audit

### Problem
Independent repair shops frequently outsource specialist work such as machining, alignment, glass, towing, programming, sublet body/mechanical work or mobile diagnostics. The vendor invoice, customer authorization, markup policy and final customer invoice may live in different systems. Margin can leak when the vendor cost is not passed through, markup is wrong, or a sublet charge appears without matching authorization.

### Product
Upload sublet/vendor invoices plus repair-order/customer invoice exports and optionally authorization evidence. The checker links by RO/job/date/vendor and flags:
- vendor invoice not billed to customer;
- billed sublet line with no vendor cost;
- cost/markup outside configured policy;
- vendor amount changed after estimate;
- duplicate vendor charge;
- customer sublet line not clearly linked to authorized work.

It does not determine whether a markup is legally permissible or commercially appropriate.

### Distribution
Independent automotive/body/heavy-equipment shops, shop bookkeepers and fractional controllers.

### Monetization hypothesis
CA$10–25 per monthly audit or CA$15–35/month recurring small-shop plan.

### Competition
Shop-management systems can record sublet work, but the current review did not surface a strong independent upload-and-audit product specifically for reconciling outside-work cost, authorization and customer billing across disconnected systems.

### Risk
Matching vendor invoices to repair-order lines can be messy. The opportunity shrinks for shops already operating a tightly integrated management/accounting stack.

### Verdict
**Advance cautiously.** Narrow but directly tied to gross-margin leakage.

---

## Dropped after deeper review

### Small-shop warranty claim evidence preflight
Canadian mechanic-shop software now exists with warranty-claim submission as a core workflow, while fleet warranty-recovery services independently identify historical reimbursement opportunities. The gap is no longer clean enough for the top three.

### Parts/core/credit leakage audit
Current purpose-built tools already track open cores, return windows, vendor credits and missing money trails.

### Rental damage/condition reconciliation
Current rental platforms and standalone condition-report products already capture before/after evidence, signatures and damage charges.

### Calibration certificate / serialized equipment tracking
Current equipment-maintenance and calibration systems already cover asset serials, certificates, maintenance status and dispatch conflicts.

## Stage 3 ranking

1. Ontario estimate / authorization / final-invoice QA preflight
2. Technician clocked-time vs billed-labor audit
3. Outsourced / sublet invoice vs customer billing audit

## Advance to Stage 4

Advance those three only.

## Verification record

- Last verified: 2026-10-20
- Stage 3 status: complete
- Stage 5: out of scope
