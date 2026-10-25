---
title: Revenue Investigation — Wave 28 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest MSP/telecom concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 324
permalink: /projects/notes/revenue-investigation-wave-28-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-28, stage-4, msp, telecom]
---

# Wave 28 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — Vendor SLA-credit evidence / recovery preflight

### Core promise
Help an MSP find likely vendor SLA-credit opportunities and assemble the exact incident/customer evidence needed before vendor claim deadlines expire.

### MVP plan
- Start with a narrow vendor set such as Microsoft 365 plus one telecom/cloud provider.
- Configure SLA thresholds, exclusions, evidence requirements and claim deadlines from official terms.
- Import outage/service-health incident data manually or via export where available.
- Import PSA/support ticket and customer-impact evidence references.
- Flag candidate credit events, missing incident IDs, missing tenant/account/circuit IDs, missing customer-impact proof and approaching deadlines.
- Build a source-linked claim checklist/evidence index.
- Track requested/approved/denied/credited status.
- Never determine entitlement or submit claims automatically.

### Likely stack
- Browser/local workflow with versioned YAML vendor rule packs.
- Python deterministic date/evidence rules.
- CSV/email/ticket export ingestion first; APIs only later if validated.

### Pricing hypothesis
- Free: one incident/vendor check.
- CA$5–15 per claim evidence pack.
- CA$15–35/month recurring MSP plan.

### Semi-automated acquisition pipeline
1. Monitor official vendor SLA/credit-request pages for rule changes.
2. Publish search pages around Microsoft/cloud/carrier SLA credit deadlines and required evidence.
3. Free incident checklist becomes the inbound funnel.
4. Demonstrate with synthetic incident/ticket data.
5. Partner with MSP finance consultants, distributors and fractional operations advisers.
6. Track opt-in vendor demand to decide which rule packs deserve support.
7. Future outreach remains low-volume/manual-approved and secondary to search/partner acquisition.
8. Route multi-client/high-volume credit recovery users to the owner.

### Main risks
- Vendor SLA terms change and contain exclusions.
- Evidence may still be disputed by the vendor.
- APIs/status history may not expose enough detail retrospectively.

### Stage 4 verdict
**Highest-priority Wave 28 candidate.**

---

## Rank 2 — MSP client offboarding residual-access / cost-closure audit

### Core promise
After an MSP client exits, independently verify that privileged access, agents, delegated relationships, licenses, vendor costs and ownership handoffs actually closed cleanly.

### MVP plan
- Import/export client asset/service inventory, vendor subscriptions, agent/device lists and admin/delegated-access records.
- Record client exit date and expected support boundary.
- Flag RMM/EDR/backup agents still active after exit.
- Flag delegated admin/GDAP relationships or technician/service identities still present.
- Flag vendor subscriptions/licenses whose cost continues after client billing ends.
- Flag domain/DNS/vendor-portal/admin ownership handoff without acknowledgement evidence.
- Flag backup/documentation handoff gaps.
- Produce a signed/reviewable exit-closeout evidence pack.
- Never revoke access, cancel licenses or rotate credentials automatically.

### Likely stack
- Export-first browser/local audit utility.
- Python reconciliation rules.
- Saved templates for common RMM, M365/CSP, backup and security exports.

### Pricing hypothesis
- Free: small-client checklist.
- CA$15–30 per client exit audit.
- CA$15–35/month recurring MSP termination/review plan.

### Semi-automated acquisition pipeline
1. Publish search content around MSP client offboarding, lingering access and vendor-cost cleanup.
2. Free offboarding audit template is the inbound funnel.
3. Partner with MSP consultants, M&A transition advisers and IT-service accountants.
4. Demonstrate with synthetic client inventories only.
5. Track opt-in system/export types to prioritize mappings.
6. Future validation should stay export-based first to minimize privileged access/security risk.
7. Any outreach remains partner-led/manual-approved.
8. Route multi-client/MSP-consultant demand to the owner.

### Main risks
- Broad integration surface if live connections are added too early.
- Some residual access is intentional during transition.
- Security sensitivity requires strict minimum-data handling.

### Stage 4 verdict
**Strong security + cost-closure niche with clear audit value.**

---

## Rank 3 — Telecom activation/disconnection vs billing audit

### Core promise
Find telecom charges that began before usable activation, continued after confirmed disconnect/port completion, or overlapped longer than intended during migrations.

### MVP plan
- Import carrier invoices plus service-order/activation/port/disconnect records.
- Normalize account, site, circuit/service ID, dates and recurring charge lines.
- Flag recurring billing before documented activation.
- Flag billing after documented disconnect/port completion.
- Flag duplicate/overlapping old/new services beyond configured transition window.
- Flag installation/one-time charges inconsistent with quote/order where supplied.
- Flag possible installation-SLA credit event for manual review.
- Export source-linked billing exception worksheet.
- Never dispute charges or contact carriers automatically.

### Likely stack
- Browser/local CSV/PDF audit utility.
- Python matching/date rules.
- Saved carrier mapping templates.

### Pricing hypothesis
- CA$15–30 per audit.
- CA$20–50/month recurring small MSP/multi-location plan.

### Semi-automated acquisition pipeline
1. Publish search content around telecom billing after disconnect, early billing and circuit overlap.
2. Free sample audit/template demonstrates recoverable leakage.
3. Partner with MSPs, telecom consultants and fractional IT/finance providers.
4. Start with one or two common invoice/order formats.
5. Track opt-in carriers/service types to prioritize mappings.
6. Future validation should focus on 5–100 circuit/service portfolios that are too small for enterprise TEM.
7. Outreach remains manual/partner-led.
8. Route multi-location/high-volume users to the owner.

### Main risks
- TEM incumbents already cover similar leakage for larger customers.
- Carrier invoice/order formats vary.
- Actual usable activation may be difficult to prove from administrative records alone.

### Stage 4 verdict
**Good financial-recovery utility, but closer to existing TEM competition than ranks 1–2.**

## Wave 28 conclusion

Top three:

1. Vendor SLA-credit evidence / recovery preflight
2. MSP client offboarding residual-access / cost-closure audit
3. Telecom activation/disconnection vs billing audit

Wave 28 confirms that MSP/telecom software is crowded at PSA, RMM, ticketing, SLA monitoring, telecom-expense and license-reconciliation layers, but narrower recovery and lifecycle-closeout gaps remain where vendor contracts, incidents, access, subscriptions and billing cross system boundaries.

## Verification record
- Last verified: 2026-10-25
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
