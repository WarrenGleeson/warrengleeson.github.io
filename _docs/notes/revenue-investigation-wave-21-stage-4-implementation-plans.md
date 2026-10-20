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
- Check non-written authorization records for name/contact/date/time where present.
- Flag missing required invoice statements/fields against a versioned Ontario ruleset.
- Produce a review-only evidence checklist with exact source references.
- Never provide legal advice or claim the documents are legally compliant.

### Likely stack
- Browser upload utility.
- Python/PDF extraction and deterministic rule engine.
- Manual-entry fallback for low-confidence fields.
- Versioned Ontario repair-rule pack.

### Pricing hypothesis
- Free: one sample/simple preflight.
- CA$5–10: per repair-document preflight.
- CA$15–30/month: recurring independent-shop plan.

### Semi-automated acquisition pipeline
1. Monitor Ontario's official repair-business guidance and regulations.
2. Publish exact-intent pages around estimate, authorization and invoice requirements.
3. Free checklist/sample checker drives inbound traffic.
4. Demonstrate with synthetic repair documents only.
5. Partner channel: automotive bookkeepers, shop consultants and independent-shop associations.
6. Track opt-in recurring missing-field/error categories to improve deterministic rules.
7. Any future outreach remains low-volume/manual-approved; search/referrals are preferred.
8. Route multi-location/consultant demand to the owner.

### Main risks
- Legal sensitivity and rule maintenance.
- Modern shop platforms already connect these records well.
- Document extraction variability.

### Stage 4 verdict
**Highest-priority Wave 21 candidate.**

---

## Rank 2 — Technician clocked-time vs billed-labor audit

### Core promise
At month-end, reconcile actual technician time with job-clock and customer-billed labor so an independent shop can see where labor recovery is leaking across disconnected systems.

### MVP plan
- Import payroll/time-clock export.
- Import repair-order/invoice labor export.
- Optional job-clock export.
- Map technicians/jobs/dates.
- Report paid hours, job hours and billed hours side by side.
- Flag missing technician attribution, unusually low labor recovery, billed-without-job-time candidates and high overtime/low-recovery periods.
- Allow user-defined non-billable categories.
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
**Useful financial-control utility with moderate durability.**

---

## Rank 3 — Outsourced / sublet invoice vs customer billing audit

### Core promise
Show whether outsourced repair work was fully and correctly passed through from vendor invoice to customer billing without losing authorized margin.

### MVP plan
- Import vendor/sublet invoices.
- Import repair-order/customer invoice export.
- Optional authorization/estimate export.
- Match by RO/job/date/vendor with manual confirmation for low-confidence links.
- Flag vendor cost not billed to customer, customer charge with no vendor cost, configured markup variance, changed vendor cost after estimate, duplicate vendor charge and unclear authorization linkage.
- Export a month-end sublet reconciliation worksheet.
- Do not determine lawful markup or contract terms.

### Likely stack
- Browser/local CSV/PDF utility.
- Python extraction and matching engine.
- Configurable markup/reference rules.
- Saved vendor/job mappings for repeat use.

### Pricing hypothesis
- CA$10–25 per audit.
- CA$15–35/month recurring shop plan.

### Semi-automated acquisition pipeline
1. Publish search content around sublet repair markup leakage and outsourced-work reconciliation.
2. Offer a synthetic sample audit as the acquisition funnel.
3. Partner channel: automotive/body-shop bookkeepers and fractional controllers.
4. Focus on shops using disconnected accounting/shop/vendor workflows.
5. Track opt-in matching problems to prioritize supported export formats.
6. Future validation uses customer-supplied redacted documents only with explicit handling rules.
7. Outreach remains low-volume/manual-approved; bookkeeping referrals/search are preferred.
8. Route recurring multi-shop/controller demand to the owner.

### Main risks
- Document matching complexity.
- Integrated shop systems can reduce the problem.
- Pricing power may be limited unless audits consistently recover measurable margin.

### Stage 4 verdict
**Narrow but financially legible opportunity; best positioned as a month-end audit utility.**

## Wave 21 conclusion

Top three:

1. Ontario estimate / authorization / final-invoice QA preflight
2. Technician clocked-time vs billed-labor audit
3. Outsourced / sublet invoice vs customer billing audit

Wave 21 confirms that automotive and equipment-rental operations are heavily software-served. The surviving opportunities are independent compliance/evidence and financial-reconciliation layers that work beside existing shop systems rather than replacing them.

## Verification record

- Last verified: 2026-10-20
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
