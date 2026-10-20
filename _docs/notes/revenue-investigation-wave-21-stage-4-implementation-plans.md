---
title: Revenue Investigation — Wave 21 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest automotive/equipment-repair concepts. No Stage 5 development or testing is authorized here.
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

## Rank 1 — Ontario estimate / authorization / final-invoice QA preflight

### Core promise
Before a repair invoice goes to the customer, check whether the shop's estimate, authorization evidence and final invoice are internally consistent with Ontario's administrative repair requirements.

### MVP plan
- Upload estimate/work authorization/final invoice PDFs or structured exports.
- Extract customer, shop, vehicle, VIN/licence, odometer, estimate amount, line items, authorization data and final total.
- Check required estimate/invoice fields.
- Compare final amount with written estimate or authorized maximum.
- Flag charges/work not visibly linked to the authorized work set.
- Check non-written authorization record for name/contact/date/time where present.
- Flag missing required statement/invoice fields based on a versioned Ontario ruleset.
- Produce a review-only evidence checklist with exact source references.
- Never provide legal advice or claim the documents are legally compliant.

### Likely stack
- Browser upload utility.
- Python/PDF extraction and deterministic rule engine.
- Local/manual-entry fallback for low-confidence fields.
- Versioned Ontario Consumer Protection Act / regulation rule pack.

### Pricing hypothesis
- Free: one sample/simple preflight.
- CA$5–10: per repair-document preflight.
- CA$15–30/month: recurring independent-shop plan.

### Semi-automated acquisition pipeline
1. Monitor Ontario's official repair-business guidance and regulations for changes.
2. Publish exact-intent pages around estimate, authorization and invoice requirements.
3. Free checklist/sample checker drives inbound traffic.
4. Demonstrate with synthetic repair documents only.
5. Partner channel: automotive bookkeepers, shop consultants and independent-shop associations.
6. Track opt-in recurring missing-field/error categories to improve rules.
7. Any future outreach remains low-volume/manual-approved; search/referrals are preferred.
8. Route multi-location/consultant demand to the owner.

### Main risks
- Legal sensitivity and rule maintenance.
- Modern shop platforms already connect these records well.
- Document extraction variability.

### Stage 4 verdict
**Highest-priority Wave 21 candidate.**

---

## Rank 2 — Small-shop warranty claim evidence preflight

### Core promise
Help independent automotive/heavy-equipment repair shops catch missing warranty evidence before submitting a supplier/manufacturer claim.

### MVP plan
- User creates/configures warranty-program checklist.
- Upload repair order, supplier invoice and supporting documents.
- Record failed/replacement part numbers and serials where applicable.
- Record VIN/equipment serial, mileage/hours, purchase/install/remove dates and labor evidence.
- Track core/failed-part return requirements/reference numbers.
- Flag missing documents, date/serial mismatches and incomplete return evidence.
- Record reimbursement/status after submission.
- No warranty-eligibility determination.

### Likely stack
- Browser/file utility.
- Configurable checklist/rules engine.
- PDF/image metadata extraction.
- Simple recurring claim workspace.

### Pricing hypothesis
- CA$5–15 per claim preflight.
- CA$15–35/month recurring shop plan.

### Semi-automated acquisition pipeline
1. Publish practical content around failed warranty claims and missing evidence.
2. Free generic claim checklist is the inbound funnel.
3. Focus initial validation on parts distributors/repair shops with repeat supplier warranties rather than OEM dealer warranty departments.
4. Demonstrate using synthetic claim packs.
5. Partner channel: automotive/heavy-equipment bookkeepers and parts distributors.
6. Track opt-in missing-evidence categories to determine which warranty programs justify templates.
7. Any direct outreach remains manual and secondary to search/partner referrals.
8. Route recurring/multi-program users to the owner.

### Main risks
- Warranty requirements vary by supplier/manufacturer.
- Enterprise/fleet tools already automate recovery.
- Users must maintain program-specific checklists.

### Stage 4 verdict
**Good money-recovery niche if targeted at smaller disconnected shops.**

---

## Rank 3 — Technician clocked-time vs billed-labor audit

### Core promise
At month-end, reconcile actual technician time with job-clock and customer-billed labor so an independent shop can see where labor recovery is leaking across disconnected systems.

### MVP plan
- Import payroll/time-clock export.
- Import repair-order/invoice labor export.
- Optional job-clock export.
- Map technicians/jobs/dates.
- Report paid hours, job hours and billed hours side by side.
- Flag missing technician attribution, unusually low labor recovery, billed-without-job-time candidates and high overtime/low-recovery periods.
- Export a controller/bookkeeper review worksheet.
- Do not calculate payroll compliance or recommend compensation plans.

### Likely stack
- Local/browser CSV/XLSX utility.
- Deterministic matching and variance rules.
- Saved mappings for repeat monthly audits.

### Pricing hypothesis
- CA$15–30 per month-end audit.
- CA$20–40/month recurring plan.

### Semi-automated acquisition pipeline
1. Publish content around clocked vs flagged vs billed technician hours.
2. Free sample reconciliation template/checker drives inbound discovery.
3. Partner with automotive bookkeepers/fractional controllers.
4. Target shops running separate payroll/time-clock and shop systems.
5. Demonstrate with synthetic time and repair-order exports.
6. Track opt-in mismatch categories to improve mappings.
7. Keep future outreach manual and partner-led.
8. Route multi-shop/controller demand to the owner.

### Main risks
- Modern integrated shop systems already report these metrics.
- Payroll/labor-law boundaries require explicit scope limits.
- Transitional opportunity as shops consolidate systems.

### Stage 4 verdict
**Useful financial-control utility, but less durable than ranks 1–2.**

## Wave 21 conclusion

Top three:

1. Ontario estimate / authorization / final-invoice QA preflight
2. Small-shop warranty claim evidence preflight
3. Technician clocked-time vs billed-labor audit

Wave 21 confirms that automotive/rental operations are heavily software-served, but smaller opportunities remain in independent compliance/evidence and financial-reconciliation layers that work alongside existing shop systems.

## Verification record

- Last verified: 2026-10-20
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
