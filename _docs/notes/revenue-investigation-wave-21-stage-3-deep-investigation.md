---
title: Revenue Investigation — Wave 21 Stage 3 Deep Investigation
summary: Deep investigation of the strongest automotive, fleet and equipment-repair ideas after direct competition checks.
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

## 1. Parts/labor warranty reimbursement evidence preflight

### Problem
Independent repair shops regularly perform work involving supplier, aftermarket or third-party warranties. Reimbursement often depends on tying the failed part, original purchase, vehicle/job, replacement work, photos/testing and authorization/RMA together cleanly. Missing evidence creates denied or delayed reimbursement.

### Product
A lightweight preflight that checks a shop's warranty packet before submission:
- original supplier invoice/purchase reference;
- vehicle/unit and repair-order link;
- failed/replacement part numbers;
- serial/date code where relevant;
- photos/testing evidence where the shop's program expects it;
- RMA/authorization/reference;
- labour hours/rate evidence;
- customer-pay vs warranty line separation;
- submission deadline/status.

The user configures the supplier/program requirements. The tool does not decide warranty eligibility.

### Distribution
Search around automotive parts warranty reimbursement, repair-shop warranty claims, supplier return/warranty workflows and bookkeeping/shop-consultant referrals.

### Monetization hypothesis
Free one packet; CA$5–15 per warranty preflight; CA$15–30/month for recurring shops.

### Competition
Parts-return/core-credit products exist, but current research did not surface a strong low-cost independent-shop tool centered on **reimbursement packet completeness across multiple suppliers/warranty programs**.

### Risk
Warranty requirements vary by supplier. The tool must be user-configurable rather than pretending one rule set applies everywhere.

### Verdict
**Advance.** Strongest Wave 21 concept.

---

## 2. Serialized replacement-component consistency audit

### Problem
Some repair businesses replace serialized/high-value components—engines, transmissions, control modules, batteries, pumps, compressors, attachments or machinery components—but the serial/model history can end up split across repair orders, invoices and equipment records. That makes later warranty, resale or repeat-repair investigation harder.

### Product
Upload repair-order/invoice exports plus an asset/unit register and flag:
- installed serial/model not linked to the expected vehicle/equipment unit;
- replacement component without prior removal/history record;
- duplicate serial assigned to multiple assets;
- warranty start date missing;
- repair invoice naming a different part/model than the asset register;
- calibration/coding evidence missing where the user's own procedure requires it.

### Distribution
Equipment repair, commercial vehicle, marine/RV and specialty repair search; service consultants and bookkeepers.

### Monetization hypothesis
CA$10–25 per audit; CA$15–35/month for recurring shops/fleets.

### Competition
Large MRO/asset-management systems already support serial-level component history. The surviving wedge is a lightweight consistency auditor for smaller repair operations that do not want a full serialized-asset platform.

### Risk
Narrow target market and inconsistent source documents. Avoid regulated aviation/medical-device contexts initially.

### Verdict
**Advance cautiously.** Distinct enough in smaller specialty repair niches.

---

## 3. Small-fleet downtime / repair-cost reconciliation audit

### Problem
Small commercial fleets often outsource repairs. A breakdown can create repair invoices, tow bills, rental/replacement-vehicle charges and lost-use/downtime records in different systems. Managers need to know which costs belong to the same event and whether replacement-rental days or vendor turnaround align with actual downtime.

### Product
Upload/import repair invoices, tow bills and replacement-rental records, then map them to fleet units and breakdown events. Flag:
- rental days outside documented downtime window;
- repair invoice attached to wrong unit/VIN/odometer;
- duplicate tow/rental/repair charge candidate;
- repair completion date inconsistent with rental return;
- missing authorization/reference;
- warranty/third-party reimbursement candidate requiring review.

### Distribution
Small fleets, trades businesses, delivery operators, fleet bookkeepers and fractional controllers.

### Monetization hypothesis
CA$15–30 per monthly audit; CA$20–40/month for recurring small fleets.

### Competition
Full fleet-management systems manage downtime and maintenance, but smaller operators often retain accounting + spreadsheets + external repair vendors. The wedge is **retrospective reconciliation without replacing fleet software**.

### Risk
Document matching can be messy. ROI must be shown in recovered/avoided costs, not just cleaner records.

### Verdict
**Advance.** Strong operational/financial angle.

---

## Dropped after deeper review

### Core-return / vendor-credit tracking
Multiple dedicated products now target exactly this problem, including small repair shops.

### Consumer vehicle service-history / resale packs
Current apps already scan receipts, maintain service history and generate resale reports.

### Rental damage/condition workflows
Inspection and damage capture are standard features in current rental-management products.

### Collision estimate scrubbing
The BC Automotive Retailers Association already offers EstimateScrubber with ICBC-aware estimate analysis.

## Stage 3 ranking

1. Parts/labor warranty reimbursement evidence preflight
2. Small-fleet downtime / repair-cost reconciliation audit
3. Serialized replacement-component consistency audit

## Advance to Stage 4

Advance those three only.

## Verification record

- Last verified: 2026-10-20
- Stage 3 status: complete
- Stage 5: out of scope
