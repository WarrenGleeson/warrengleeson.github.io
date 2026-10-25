---
title: Revenue Investigation — Wave 23 Stage 3 Deep Investigation
summary: Deep investigation of the strongest logistics, trucking and wholesale ideas after direct competition checks.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 303
permalink: /projects/notes/revenue-investigation-wave-23-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-23, deep-investigation, logistics, wholesale]
---

# Wave 23 Stage 3 — Deep Investigation

## 1. Carrier accessorial evidence / revenue recovery preflight

### Problem
Small carriers lose detention, layover, TONU, lumper and similar accessorial revenue because the event happened but the evidence packet is incomplete by billing time. Common failure points are missing in/out times, missing notice to the broker/customer, missing receipt, unclear free-time term or missed submission deadline.

### Product
A carrier-side pre-billing utility that takes rate confirmation, BOL/POD, driver timestamps/notes, receipts and invoice draft, then flags:
- possible accessorial event with no invoice line;
- invoice line with incomplete supporting evidence;
- missing appointment/in-out timestamps;
- missing receipt/authorization/reference;
- unclear free-time/rate term requiring human review;
- approaching customer/broker submission deadline;
- billed/requested/accepted/collected status gaps.

It does not decide contractual entitlement or send claims automatically.

### Distribution
Carrier billing/search traffic, trucking bookkeepers, small-fleet billing services and downloadable detention evidence checklist.

### Monetization hypothesis
Free one-load audit; CA$5–10 per evidence pack; CA$15–30/month for small carriers.

### Competition
Freight invoice auditing and broker-side accessorial software are mature, but the current research suggests a narrower carrier-side wedge around **finding billable accessorial events and evidence gaps before invoicing** rather than auditing carrier invoices after receipt.

### Risk
Contract terms vary. Driver evidence may be incomplete. The tool must stop at “evidence ready / review needed,” not promise payment.

### Verdict
**Advance.** Strongest Wave 23 concept.

---

## 2. Wholesale case-pack / UOM consistency audit

### Problem
Distributors commonly buy, stock and sell the same SKU at different packaging levels: each, inner pack, case, pallet. Errors arise when a supplier price or PO is per case but ERP cost is stored per each, or when customer order quantities do not respect sell-pack multiples. These mistakes can quietly distort margin and inventory.

### Product
Upload item master, supplier price/PO export and optional customer-order/invoice export. Normalize packaging hierarchy and flag:
- purchase UOM inconsistent with configured pack conversion;
- supplier pack-size change not reflected in item master;
- unit cost implying case-vs-each mismatch;
- customer quantity not aligned with sell-pack multiple;
- same barcode/SKU mapped to incompatible packaging levels;
- receiving quantity inconsistent with PO UOM;
- ambiguous descriptions such as box/case/pack without explicit conversion.

### Distribution
Wholesale/distributor operations search, ERP consultants, purchasing consultants and free CSV audit.

### Monetization hypothesis
Free small item-master audit; CA$15–30 one-off audit; CA$15–35/month recurring catalog/purchasing checks.

### Competition
Supplier-price diff products now normalize pack sizes, but the surviving wedge is broader **cross-system UOM consistency across item master, PO/receiving and customer orders**, not merely comparing two supplier price lists.

### Risk
ERP schemas vary, and pack hierarchies can be complex. The product must be confidence-scored and never silently alter master data.

### Verdict
**Advance.** Strong wholesale-control opportunity.

---

## 3. Customer freight recharge vs carrier-cost reconciliation

### Problem
Wholesalers/distributors often pay a carrier and separately recharge freight to the customer under customer-specific terms. Leakage occurs when carrier accessorials are never recharged, customer freight is charged after a waived-freight threshold, fuel/accessorial policies are inconsistently applied, or the customer-facing freight amount has no clear relationship to actual shipment cost.

### Product
Import shipment/order/invoice records plus carrier invoices and customer freight terms. Flag:
- carrier freight cost with no customer recharge where policy expects one;
- customer freight charge with no carrier/shipment basis;
- accessorial paid but not passed through;
- waived/free-freight rule applied inconsistently;
- fuel/freight surcharge mismatch;
- duplicate recharge candidate;
- margin on freight outside user-configured tolerance.

It does not recommend pricing policy; it audits the policy the distributor already uses.

### Distribution
Wholesale finance/search, distributor bookkeepers/controllers and ERP/accounting consultants.

### Monetization hypothesis
CA$15–30 monthly audit or CA$20–40/month recurring distributor plan.

### Competition
Freight audit products focus mainly on carrier-side invoice correctness. Pricing/margin platforms cover broader customer pricing. The narrower cross-check between **actual freight expense and customer freight recovery** appears less directly served for small distributors.

### Risk
Customer freight policies vary substantially. Accurate matching requires shipment/order/invoice identifiers.

### Verdict
**Advance.** Strong finance/revenue-leak angle.

---

## Dropped after deeper review

### Generic freight invoice audit
Crowded with enterprise, SMB and contingency products.

### Supplier price-list comparison
Several exact current tools already compare supplier files, including pack-size and unit-cost normalization.

### Distributor rebate/SPA recovery
Current specialists already audit and recover manufacturer rebate/SPA leakage.

### Generic POD capture
Mature ePOD and freight-document platforms already cover this.

## Stage 3 ranking

1. Carrier accessorial evidence / revenue recovery preflight
2. Wholesale case-pack / UOM consistency audit
3. Customer freight recharge vs carrier-cost reconciliation

## Advance to Stage 4
Advance those three only.

## Verification record
- Last verified: 2026-10-25
- Stage 3 status: complete
- Stage 5: out of scope
