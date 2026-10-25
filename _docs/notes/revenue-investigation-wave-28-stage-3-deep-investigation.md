---
title: Revenue Investigation — Wave 28 Stage 3 Deep Investigation
summary: Deep investigation of the strongest MSP and telecom business-operation ideas after direct competition checks.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 323
permalink: /projects/notes/revenue-investigation-wave-28-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-28, deep-investigation, msp, telecom]
---

# Wave 28 Stage 3 — Deep Investigation

## 1. Vendor SLA-credit evidence / recovery preflight

### Problem
MSPs buy Microsoft 365, cloud, backup, security, telecom and other recurring services on behalf of customers. Many vendors offer service credits when availability or response commitments are missed, but credits are not automatic: claims often require incident IDs, customer-impact evidence, ticket references, dates/times and submission within a short deadline. Small MSPs can miss recoverable credits because this evidence sits across vendor status pages, PSA tickets, customer emails and invoices.

### Product
Import or enter vendor SLA terms plus outage/support-event evidence. Flag:
- incident appears to meet the configured credit threshold;
- customer-impact evidence missing;
- vendor incident/outage ID missing;
- ticket/reference evidence missing;
- claim deadline approaching or expired;
- affected subscription/account/circuit identifiers missing;
- credit received but not linked to the underlying incident/customer;
- optional downstream customer-credit obligation requiring review.

The tool does not determine legal entitlement or submit claims automatically.

### Distribution
Search around Microsoft SLA credits, carrier SLA credits, MSP vendor credits and outage reimbursement; MSP finance consultants and cloud distributors.

### Monetization hypothesis
Free one incident check; CA$5–15 per credit pack; CA$15–35/month recurring MSP plan.

### Competition
PSA/helpdesk tools track SLA performance for the MSP's own customer service, but the current review did not identify a strong lightweight product focused on **recovering credits from upstream SaaS/cloud/telecom vendors across multiple providers**.

### Risk
Vendor SLA wording and exclusions vary widely. The product must be rules/configuration driven and label findings as candidate credits, not guaranteed claims.

### Verdict
**Advance.** Strongest Wave 28 concept.

---

## 2. MSP client offboarding residual-access / cost-closure audit

### Problem
When an MSP client leaves, the operational task is broader than removing a user account. RMM/EDR/backup agents, delegated administration, service accounts/API integrations, vendor licenses, recurring supplier costs, domains/DNS/vendor portals and documentation handoff all need to be reconciled. A missed item can leave a security exposure or continuing supplier cost after client revenue stops.

### Product
Import/export the client's asset/service inventory plus PSA/vendor/admin records and check:
- RMM/EDR/backup agents still present after exit date;
- GDAP/delegated admin relationship still active;
- technician/service/API identities or integrations still present;
- supplier subscriptions/licenses still active after client billing stopped;
- domain/DNS/vendor-portal ownership not transferred/confirmed;
- backup/documentation/admin handoff not acknowledged;
- final invoice/vendor-cost period mismatch;
- offboarding evidence missing for a required control.

The tool never revokes access or deletes anything automatically.

### Distribution
MSP offboarding search, MSP consultants, acquisition/merger transition specialists and free exit checklist/audit.

### Monetization hypothesis
Free small-client checklist; CA$15–30 per client exit audit; CA$15–35/month for MSPs wanting recurring termination checks.

### Competition
Offboarding checklists and PSA workflows are common, but the wedge is a **post-offboarding reconciliation audit across access, agents, licenses and supplier costs**, not another checklist/workflow engine.

### Risk
Integration breadth can become large quickly. Start with export-based audits rather than live privileged connections.

### Verdict
**Advance.** Strong security + cost-closure angle.

---

## 3. Telecom activation/disconnection vs billing audit

### Problem
Businesses and MSPs can have circuits, voice lines or managed telecom services where carrier billing dates do not line up cleanly with actual activation, port completion or disconnect evidence. New service may be invoiced before usable activation, old service may continue billing after migration/disconnect, or temporary overlap can persist longer than intended.

### Product
Upload carrier invoices plus service-order/port/activation/disconnect records and flag:
- recurring charge starting before documented service activation;
- charge continuing after confirmed disconnect/port completion;
- overlapping old/new service beyond configured transition window;
- installation charge inconsistent with order/quote;
- circuit/location/account mismatch;
- service-level installation miss with possible credit review;
- duplicate recurring service candidate.

The tool does not dispute charges automatically.

### Distribution
MSPs with telecom resale/management, multi-site small businesses, telecom consultants and fractional IT/finance providers.

### Monetization hypothesis
CA$15–30 per audit; CA$20–50/month recurring multi-location/MSP plan; contingency pricing could be tested later in a separate Stage 5 chat.

### Competition
TEM platforms already audit telecom spend broadly. The narrower wedge is a low-touch **service-order milestone vs invoice-period reconciliation** for small portfolios that do not justify a full TEM implementation.

### Risk
Carrier document formats vary and TEM incumbents can cover the same cases. Target only small/mid-size portfolios with clear service-order evidence.

### Verdict
**Advance cautiously.** Strong ROI angle but closer to mature TEM competition.

---

## Dropped after deeper review

### Microsoft 365 seat/license reconciliation
Current MSP products directly compare distributor seats, tenant assignments and PSA/customer billing, including NCE/proration handling.

### Generic vendor subscription vs PSA billing reconciliation
Existing MSP billing tools already reconcile recurring vendor quantities/costs against PSA contracts.

### Generic SLA monitoring
PSA/helpdesk and dedicated SLA-monitoring tools already cover response/resolution tracking.

### Generic telecom expense management
Mature market with many SMB-capable products.

## Stage 3 ranking

1. Vendor SLA-credit evidence / recovery preflight
2. MSP client offboarding residual-access / cost-closure audit
3. Telecom activation/disconnection vs billing audit

## Advance to Stage 4
Advance those three only.

## Verification record
- Last verified: 2026-10-25
- Stage 3 status: complete
- Stage 5: out of scope
