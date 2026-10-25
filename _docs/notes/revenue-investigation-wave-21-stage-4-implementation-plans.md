---
title: Revenue Investigation — Wave 21 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest automotive/fleet/equipment concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-20
updated: 2026-10-20
last_verified: 2026-10-20
owner: High Director
order: 296
permalink: /projects/notes/revenue-investigation-wave-21-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-21, stage-4, automotive]
---

# Wave 21 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — Parts/labor warranty reimbursement evidence preflight

### Core promise
Before an independent repair shop submits a supplier/manufacturer warranty claim, check whether the reimbursement packet contains the evidence that program expects.

### MVP plan
- User selects or creates warranty-program template.
- Upload original supplier invoice, repair order, replacement invoice, photos/testing evidence and RMA/authorization where applicable.
- Extract part number, serial/date code, vehicle/unit reference, dates, labour hours/rate and claim/reference identifiers.
- Flag missing source invoice, mismatched part number, missing failed-part evidence, missing authorization, inconsistent vehicle/job reference, incomplete labour evidence and approaching submission deadline.
- User-confirmed checklist for supplier-specific requirements.
- Export a clean claim-evidence index.
- Never determine warranty entitlement or submit claims automatically.

### Likely stack
- Browser upload utility.
- Python document extraction + deterministic rules.
- Saved supplier/program templates for repeat users.

### Pricing hypothesis
- Free: one simple claim preflight.
- CA$5–15 per completed claim pack.
- CA$15–30/month for recurring repair shops.

### Semi-automated acquisition pipeline
1. Publish search pages around parts warranty claim documentation, labour reimbursement and denied claims.
2. Free claim checklist/preflight drives inbound acquisition.
3. Partner channel: automotive bookkeepers, shop consultants and parts distributors willing to publish their evidence checklist.
4. Use synthetic claim packets for demos.
5. Track opt-in denial/missing-document categories to prioritize supplier templates.
6. Future validation should focus on independent auto, diesel, RV, marine and equipment-repair shops rather than franchise dealers with OEM systems.
7. Any outreach remains low-volume/manual-approved and secondary to search/partner referrals.
8. Route multi-supplier/high-volume warranty users to the owner.

### Main risks
- Supplier warranty requirements vary widely.
- Parts distributors may improve native claim workflows.
- Document extraction must stay confidence-scored.

### Stage 4 verdict
**Highest-priority Wave 21 candidate.**

---

## Rank 2 — Small-fleet downtime / repair-cost reconciliation audit

### Core promise
Help small commercial fleets tie repair, towing and replacement-rental costs back to the same breakdown event and find mismatched or unnecessary charges without adopting a full fleet platform.

### MVP plan
- Import fleet unit list plus repair invoices, tow bills and rental/replacement-vehicle invoices.
- Normalize VIN/unit number/date/odometer references.
- Create breakdown/repair event groups.
- Flag rental days outside downtime period, wrong-unit invoices, duplicate charge candidates, mismatched repair/rental completion dates, missing authorization/reference and possible reimbursement/warranty follow-up.
- Export monthly review worksheet with source references.
- No automated dispute submission.

### Likely stack
- Browser/CSV/PDF audit tool.
- Python matching/reconciliation engine.
- Manual-review queue for ambiguous event matches.

### Pricing hypothesis
- CA$15–30 per monthly audit.
- CA$20–40/month recurring small-fleet plan.

### Semi-automated acquisition pipeline
1. Publish search content around fleet downtime cost, rental replacement charges and outsourced repair reconciliation.
2. Sample synthetic monthly audit serves as the education funnel.
3. Partner channel: fleet bookkeepers, fractional controllers, trades-business accountants and vehicle-leasing brokers.
4. Focus on 5–100 vehicle fleets using external shops and accounting exports.
5. Track opt-in mismatch categories to prioritize supported document formats.
6. Future validation uses customer-supplied redacted files only with explicit handling rules.
7. Keep outreach partner/referral-led and manually approved.
8. Route recurring multi-fleet/bookkeeper demand to the owner.

### Main risks
- Messy source documents and event matching.
- Mature fleet platforms can substitute for larger fleets.
- Value depends on finding enough dollars, not merely admin errors.

### Stage 4 verdict
**Strong financial-audit niche for small outsourced fleets.**

---

## Rank 3 — Serialized replacement-component consistency audit

### Core promise
Give specialty repair shops and small equipment fleets a clean history of which serialized/high-value component was installed on which asset, without forcing adoption of a full MRO system.

### MVP plan
- Import asset/unit register and repair-order/invoice history.
- Extract component part/model/serial where present.
- Link removal/replacement events to asset/unit/date/odometer or meter.
- Flag duplicate serials, component assigned to multiple assets, missing removal history, mismatched part/model, missing warranty-start date and missing calibration/coding evidence where the user's own procedure requires it.
- Export component-history record per asset.
- Avoid regulated aviation/medical-device contexts initially.

### Likely stack
- CSV/PDF import utility.
- Python record-linkage engine.
- Spreadsheet-style review interface.

### Pricing hypothesis
- CA$10–25 per audit.
- CA$15–35/month recurring specialty-shop/fleet plan.

### Semi-automated acquisition pipeline
1. Publish content around serialized engines/transmissions/modules/equipment-component records.
2. Free sample audit/template demonstrates duplicate/missing serial problems.
3. Target marine, RV, commercial equipment and specialty repair consultants via search/referrals.
4. Keep initial imports simple: CSV plus invoice PDFs.
5. Track opt-in component categories to decide which verticals deserve dedicated templates.
6. Future validation should avoid heavily regulated MRO sectors until domain-specific obligations are researched separately.
7. Any outreach remains manual/partner-led.
8. Route recurring asset-history users to the owner.

### Main risks
- Narrow market.
- Serial/model extraction can be unreliable.
- Asset-management/MRO platforms already solve this for larger operators.

### Stage 4 verdict
**Viable specialty-repair utility, but narrower than ranks 1–2.**

## Wave 21 conclusion

Top three:

1. Parts/labor warranty reimbursement evidence preflight
2. Small-fleet downtime / repair-cost reconciliation audit
3. Serialized replacement-component consistency audit

Wave 21 confirms that automotive/rental software is crowded at the shop-management, returns, inspection and service-history layers, but narrower evidence and reconciliation gaps remain around warranty reimbursement and outsourced fleet costs.

## Verification record

- Last verified: 2026-10-20
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
