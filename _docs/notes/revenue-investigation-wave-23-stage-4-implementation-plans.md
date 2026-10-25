---
title: Revenue Investigation — Wave 23 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest logistics/trucking/wholesale concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 304
permalink: /projects/notes/revenue-investigation-wave-23-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-23, stage-4, logistics, wholesale]
---

# Wave 23 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — Carrier accessorial evidence / revenue recovery preflight

### Core promise
Before a small carrier invoices a load, identify detention/layover/TONU/lumper events that appear billable under the carrier's own terms and show whether the evidence packet is complete enough to submit for review.

### MVP plan
- Upload rate confirmation, BOL/POD, driver timestamps/notes, receipts and invoice draft.
- Extract appointment, arrival, departure, free-time/rate references and receipt amounts where readable.
- User configures customer/broker-specific evidence/deadline rules.
- Flag possible accessorial event not yet billed.
- Flag billed accessorial with missing timestamps, receipt, authorization, notice or source term.
- Track requested/billed/accepted/collected status.
- Export evidence index and missing-item checklist.
- Never decide contractual entitlement or automatically send claims/invoices.

### Likely stack
- Browser upload tool.
- Python document extraction + deterministic rules.
- Saved customer/broker rule templates.
- Optional local processing for sensitive freight documents.

### Pricing hypothesis
- Free: one load/evidence audit.
- CA$5–10 per evidence pack.
- CA$15–30/month small-carrier plan.

### Semi-automated acquisition pipeline
1. Publish search content around detention evidence, accessorial deadlines and unbilled accessorials.
2. Free one-load preflight/checklist is the inbound funnel.
3. Partner with trucking bookkeepers and small-carrier billing services.
4. Demonstrate with synthetic rate confirmations/PODs/receipts.
5. Track opt-in missing-evidence categories to prioritize templates.
6. Future validation should target small carriers that invoice brokers/shippers directly, not large fleets with mature TMS billing modules.
7. Any outreach remains low-volume/manual-approved; search/referrals are preferred.
8. Route recurring multi-load billing users to the owner.

### Main risks
- Contract terms and evidence standards vary by counterparty.
- Document quality can be poor.
- Broker/TMS vendors can add equivalent evidence checks.

### Stage 4 verdict
**Highest-priority Wave 23 candidate.**

---

## Rank 2 — Wholesale case-pack / UOM consistency audit

### Core promise
Find case/inner/each/unit-of-measure errors across a distributor's item master, supplier/PO data and customer orders before they create margin or inventory mistakes.

### MVP plan
- Import item master plus optional supplier price/PO, receiving and customer-order exports.
- User maps base UOM, purchase UOM, sell UOM, pack quantity and identifiers.
- Normalize explicit pack conversion hierarchy.
- Flag supplier pack changes, purchase-vs-master UOM mismatch, receiving-vs-PO mismatch, implausible unit-cost changes and customer quantities outside sell-pack multiples.
- Flag ambiguous packaging descriptions for manual review.
- Export source-row audit report.
- Never write changes back into ERP automatically.

### Likely stack
- Local/browser CSV/XLSX processor.
- Python deterministic normalization/rules.
- Saved ERP column mappings.

### Pricing hypothesis
- Free: small catalog/sample audit.
- CA$15–30 one-off audit.
- CA$15–35/month recurring distributor checks.

### Semi-automated acquisition pipeline
1. Publish search content around case-vs-each errors, pack-size cost errors and UOM reconciliation.
2. Free item-master audit/template is the inbound funnel.
3. Partner with small ERP/accounting consultants and purchasing advisors.
4. Use synthetic distributor datasets for demonstrations.
5. Track opt-in ERP/file schemas and common UOM mismatches.
6. Future validation should focus on spreadsheet-heavy wholesalers with 1,000–50,000 SKUs rather than large distributors with mature PIM/ERP controls.
7. Keep outreach partner-led/manual.
8. Route recurring/multi-supplier users to the owner.

### Main risks
- Complex pack hierarchies.
- ERP schemas vary significantly.
- Supplier-price tools may broaden into cross-system UOM auditing.

### Stage 4 verdict
**Strong wholesale data-control niche with deterministic checks.**

---

## Rank 3 — Customer freight recharge vs carrier-cost reconciliation

### Core promise
Show a wholesaler/distributor where it paid freight or accessorial costs that were not recovered from customers—or charged customer freight inconsistently with its own policy.

### MVP plan
- Import customer orders/invoices, shipment IDs and carrier invoices.
- Import/configure customer-specific freight terms: free-freight thresholds, flat fees, pass-through rules, fuel/accessorial policies.
- Match carrier cost to customer order/invoice.
- Flag unrecovered freight/accessorial, unsupported customer freight charge, duplicate charge, policy inconsistency and freight-margin exception.
- Export monthly leakage/review worksheet.
- Do not set or recommend freight pricing.

### Likely stack
- Browser/CSV audit utility.
- Python matching/rules engine.
- Saved customer freight-policy templates.

### Pricing hypothesis
- CA$15–30 monthly audit.
- CA$20–40/month recurring distributor plan.

### Semi-automated acquisition pipeline
1. Publish search pages around freight recovery leakage and customer freight recharge audits.
2. Synthetic monthly leakage report demonstrates ROI.
3. Partner channel: wholesale bookkeepers, controllers and ERP consultants.
4. Focus on distributors that use external carriers and manually/semimanually recharge freight.
5. Track opt-in freight policy types to prioritize templates.
6. Future validation uses redacted/synthetic files until data-handling design is established.
7. Outreach remains manual/partner-led.
8. Route multi-branch/consultant users to the owner.

### Main risks
- Shipment/order matching can be messy.
- Customer freight policies differ widely.
- ERP/TMS integrations may become necessary at higher volume.

### Stage 4 verdict
**Good revenue-leak audit utility, with slightly higher onboarding complexity than ranks 1–2.**

## Wave 23 conclusion

Top three:

1. Carrier accessorial evidence / revenue recovery preflight
2. Wholesale case-pack / UOM consistency audit
3. Customer freight recharge vs carrier-cost reconciliation

Wave 23 confirms that logistics and wholesale are crowded at the platform level, but narrower revenue/evidence and UOM-control problems remain for small carriers and spreadsheet-heavy distributors.

## Verification record
- Last verified: 2026-10-25
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
