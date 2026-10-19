---
title: Revenue Investigation — Wave 10 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest Wave 10 concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 252
permalink: /projects/notes/revenue-investigation-wave-10-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-10, stage-4, acquisition]
---

# Wave 10 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — Apple EU payment-option margin / commitment modeller

### Core promise
Help an EU-distributed app developer compare Apple IAP, alternative in-app payment, out-of-app offers and alternative distribution using their own revenue mix and operational assumptions.

### MVP plan
- Inputs for annual EU digital-goods revenue, subscription/non-subscription mix, program eligibility, payment method mix and PSP cost assumptions.
- Model current Apple commission paths and reduced-rate cases from official documentation.
- Include non-commission operational assumptions: payment processing, refunds/support, taxes, purchase-history/subscription-management burden.
- Record selected payment configuration and 12-month commitment window.
- Export scenario comparison with every rule/source version and user-entered assumption.
- Never present outputs as tax/legal advice or guaranteed savings.

### Likely stack
- Browser-first deterministic calculator.
- Versioned YAML/JSON commercial-term rules.
- Optional saved scenarios/history later.

### Pricing hypothesis
- Free: simple scenario comparison.
- CA$15–30: detailed downloadable scenario workbook/report.
- CA$10–20/month: saved scenarios, policy-change alerts, team assumptions and periodic recalculation.

### Semi-automated acquisition pipeline
1. Monitor official Apple EU payment/business-term pages and Developer Program License Agreement update notices.
2. Diff rate/eligibility/obligation changes and require human verification before updating rules.
3. Generate factual search pages for common questions such as alternative payment vs IAP, link-out commission and 12-month commitment implications.
4. Free calculator acts as the primary inbound acquisition surface.
5. Track anonymized/opt-in scenario categories to identify high-value developer segments without collecting confidential app financials by default.
6. For future validation, identify public app/developer communities discussing EU payment choices and prepare factual example scenarios using synthetic numbers.
7. Any outreach in a future chat must be low-volume, manually approved and compliant; the intended model is search/product-led acquisition.
8. Route qualified team/finance-advisor interest to the owner.

### Main risks
- Apple terms may change due to regulatory/legal developments.
- Financial modelling depends on user assumptions and transaction mix.
- Free spreadsheets/calculators could appear quickly.

### Stage 4 verdict
**Highest-priority Wave 10 candidate.**

---

## Rank 2 — Google Play external-content-link reporting / fee reconciler

### Core promise
Help developers using US external content links reconcile their external transaction/download records against current Google Play reporting and service-fee rules before submission/payment.

### MVP plan
- Import CSV exports from the developer's payment/analytics systems and Play financial/reporting data.
- User maps required event fields once.
- Classify subscriptions, other digital transactions and app-download events.
- Track new-vs-existing install information only when supplied by the user/source; never infer unsupported status.
- Calculate expected fee buckets using current published rates.
- Flag missing, ambiguous and unmatched records for review.
- Produce monthly reconciliation/export with source-rule version.

### Likely stack
- Browser/local CSV processing for small datasets.
- Python rule engine for batch processing.
- Saved schema mappings for recurring customers.

### Pricing hypothesis
- Free: small/sample reconciliation.
- CA$19–49: one monthly reconciliation/export.
- CA$15–39/month: recurring reconciliations, mapping history and change alerts.

### Semi-automated acquisition pipeline
1. Monitor official Google Play external-content-link policy, fee and reporting pages.
2. Diff fee/event/reporting changes into rule proposals with human approval before release.
3. Publish narrow search pages around reporting deadlines, external-link fee categories and reconciliation errors.
4. Free CSV preflight/reconciliation sample acts as the primary acquisition path.
5. Monitor public developer discussions for recurring reporting confusion and use those patterns to prioritize new deterministic checks.
6. Create synthetic worked examples for common fee cases rather than using or scraping developer transaction data.
7. Any future outreach should be limited to voluntarily public developer/business contacts, manually approved and legally compliant.
8. Alert the owner only for qualified recurring/monthly reconciliation interest.

### Main risks
- Policy may change quickly due to ongoing litigation/regulatory action.
- Developer exports may not contain all fields required for definitive classification.
- Incorrect fee calculations would be high-impact, so uncertainty must be explicit.

### Stage 4 verdict
**Strong recurring finance-operations concept.**

---

## Rank 3 — Google Play financial-report schema regression checker

### Core promise
Catch new columns, enum values and mapping gaps in Google Play financial reports before they silently break accounting/data pipelines.

### MVP plan
- Local CLI/web upload for current Play CSV reports.
- User supplies or selects a known schema/mapping profile.
- Detect unknown columns, changed types, unseen enum values and unmapped fee-description values.
- Test exact-match mapping coverage.
- Generate machine-readable and human-readable regression reports.
- Maintain versioned known-value templates tied to official Play report documentation.
- No automatic modifications to downstream accounting mappings.

### Likely stack
- Python CLI + optional GitHub Action.
- YAML schema/mapping definitions.
- Optional scheduled watcher for teams pulling reports automatically.

### Pricing hypothesis
- Free: local one-file/schema check.
- CA$5–15/month: scheduled checks, multiple apps/profiles and change history.
- Team plan if expanded later to Apple/Stripe/marketplace payout formats.

### Semi-automated acquisition pipeline
1. Monitor official Play Console reporting documentation for column/value changes.
2. Maintain test fixtures and versioned schema profiles after human verification.
3. Publish search pages around specific new report values and breaking finance-pipeline changes.
4. Free CLI/checker is the product-led acquisition channel.
5. Analyze opt-in error categories to prioritize additional report formats and mappings.
6. For validation, use synthetic/current documented CSV fixtures rather than private developer reports.
7. GitHub Marketplace/distribution can target teams maintaining automated finance pipelines.
8. Route requests for multi-app or multi-marketplace support to the owner as qualified expansion signals.

### Main risks
- Narrow standalone market.
- Generic data-quality tools can reproduce the mechanics.
- Best long-term value may require expansion into multiple app-store/payment report formats.

### Stage 4 verdict
**Good small developer-finance utility; potentially a feature seed for a broader reporting-regression product.**

## Wave 10 conclusion

Top three:

1. Apple EU payment-option margin / commitment modeller
2. Google Play external-content-link reporting / fee reconciler
3. Google Play financial-report schema regression checker

Wave 10 adds a distinct opportunity class to the pool: operational tools around rapidly changing app-store economics, payment options and finance-reporting obligations.

## Verification record

- Last verified: 2026-10-19
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
