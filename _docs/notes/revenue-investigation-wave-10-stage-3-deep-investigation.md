---
title: Revenue Investigation — Wave 10 Stage 3 Deep Investigation
summary: Deep investigation of five Wave 10 finalists, focused on app-store commercial-term modelling, Play reporting correctness and narrow e-invoice reconciliation.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 251
permalink: /projects/notes/revenue-investigation-wave-10-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-10, deep-investigation]
---

# Wave 10 Stage 3 — Deep Investigation

## 1. Apple EU payment-option margin / commitment modeller

### Problem
Apple's unified EU business terms now present materially different commercial paths: Apple IAP, alternative in-app payment, out-of-app offers and alternative distribution. Rates vary by program/subscription status, and payment-option choices must be maintained for 12 months. Alternative-payment choices also shift support/refund/tax responsibilities to the developer.

### Product
A self-serve planning model where a developer enters app economics and user mix, then compares expected commissions, PSP fees, taxes/support assumptions and operational obligations across permitted payment configurations. It tracks the 12-month commitment window and exports an assumption sheet.

### Distribution
Search around Apple EU alternative payments, App Store commission comparison, DMA payment choices and developer finance communities.

### Monetization hypothesis
Free simple calculator; CA$15–30 one-off scenario workbook; CA$10–20/month for saved scenarios, policy-change alerts and team assumptions.

### Competition
Apple publishes official rates and obligations, but current research did not surface a strong current independent tool combining **economics + operational obligations + 12-month commitment tracking** under the October 2026 terms.

### Risks
Rates/policies can change; every result must be explicitly assumption-based and linked to current Apple documentation. It cannot provide tax/legal advice.

### Verdict
**Advance.** Strongest Wave 10 concept.

---

## 2. Google Play external-content-link reporting / fee reconciler

### Problem
US developers using external content links now face multiple service-fee cases, transaction/download reporting, install-age distinctions and deadlines. Finance teams need to reconcile their own external transactions/install events against what should be reportable and fee-bearing.

### Product
Import developer transaction/install exports plus Play report data, classify events according to the current program rules, calculate expected service-fee buckets and flag records needing review before reporting/payment.

### Distribution
Developer/finance search, Google Play communities and a free CSV preflight tool.

### Monetization hypothesis
Free small reconciliation; CA$19–49 one-off monthly reconciliation; CA$15–39/month recurring report checks/history.

### Competition
Google documents the program and fees, but current research did not surface an exact independent reconciliation workflow. The wedge is operational correctness against the developer's own data, not another fee calculator.

### Risks
Program terms are subject to legal/policy change; data required to determine install status may be incomplete. The tool must surface uncertainty instead of guessing.

### Verdict
**Advance.** Good recurring finance-ops niche.

---

## 3. Google Play financial-report schema regression checker

### Problem
Google changed Fee Description values in October 2026 and explicitly warned that workflows using exact matches may need updates. Finance pipelines frequently depend on fixed CSV columns/enums and can silently misclassify new values.

### Product
A local CLI or upload utility that compares a current Play report against a user's declared schema/mapping rules, identifies unseen enum values/columns, tests mapping coverage and produces a regression report before downstream import.

### Distribution
GitHub Marketplace, developer/finance search and reusable CSV schema templates.

### Monetization hypothesis
Free local checker; CA$5–15/month for scheduled monitoring/multiple apps; one-off migration report.

### Competition
Generic CSV/schema tools exist, but the current niche is sharply bounded around Google Play finance reports and official schema changes. It can potentially expand later to Apple/Stripe marketplace payout schemas.

### Risks
May be too narrow as a standalone business unless expanded carefully to multiple marketplace payout/report formats.

### Verdict
**Advance cautiously.** Strong feature/product wedge, possibly smaller business.

---

## 4. PDF invoice vs structured e-invoice reconciliation checker

### Problem
Businesses transitioning to structured e-invoicing may generate a human-readable PDF alongside XML/UBL/XRechnung/ZUGFeRD content. Amounts, tax identifiers, payment terms or line details can diverge between the visible representation and structured payload.

### Product
Upload paired PDF + XML/structured invoice, extract deterministic fields and highlight mismatches with source evidence. It validates consistency between representations rather than certifying legal EN 16931 compliance.

### Distribution
Search around e-invoice PDF/XML mismatch, accounting integrator communities and ERP implementation partners.

### Monetization hypothesis
Free single comparison; CA$10–25 batch validation; CA$20–50/month API/batch monitoring.

### Competition
Generic e-invoice validators and platforms are crowded, but a focused **human-readable vs machine-readable consistency** check is a narrower operational QA problem.

### Risks
PDF extraction quality, multiple invoice formats and localized tax fields raise implementation complexity.

### Verdict
**Hold as fourth-ranked candidate.** Worth preserving, but heavier than the top three.

---

## 5. App Review guideline change impact scanner

### Problem
Apple updates App Review Guidelines and developer terms several times per year. Teams must determine whether new clauses affect their app's declared capabilities/content/payment behavior.

### Finding
A generic rule-to-app scanner would rely heavily on heuristic interpretation and could overstate review risk. Some checks can be deterministic, but many guideline issues require contextual judgment.

### Verdict
**Hold/drop as standalone.** Better as a feature inside narrower app-store readiness tools.

## Stage 3 ranking

1. Apple EU payment-option margin / commitment modeller
2. Google Play external-content-link reporting / fee reconciler
3. Google Play financial-report schema regression checker
4. PDF vs structured e-invoice reconciliation checker

## Advance to Stage 4

Advance the top three only.

## Verification record

- Last verified: 2026-10-19
- Stage 3 status: complete
- Stage 5: out of scope
