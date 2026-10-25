---
title: Revenue Investigation — Wave 25 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest HR/recruitment and professional-services concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 312
permalink: /projects/notes/revenue-investigation-wave-25-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-25, stage-4, recruitment, professional-services]
---

# Wave 25 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — Professional-services scope-change / unbilled-work audit

### Core promise
Show a consulting, accounting, engineering or advisory firm where work performed no longer matches the executed engagement/SOW and where approved changes were not fully reflected in fees or invoices.

### MVP plan
- Upload SOW/engagement letter plus approved amendments/change orders.
- Import project/task/time-entry and invoice exports.
- Extract contracted deliverables, revision limits, milestones, fees/rates and approved changes.
- Map time/task descriptions to contracted scope with confidence scores.
- Flag work with no clear scope coverage, work performed before change approval, approved change without invoice uplift, and fixed-fee burn tied to extra work.
- Allow user to confirm/override ambiguous matches.
- Export source-linked leakage/review worksheet.
- Never determine legal entitlement or automatically invoice clients.

### Likely stack
- Browser/local file-processing utility.
- Python document extraction + deterministic matching.
- Optional language-model assistance for candidate scope mapping, always source-linked and reviewable.

### Pricing hypothesis
- Free: one small project/sample audit.
- CA$15–30 per project audit.
- CA$20–50/month recurring multi-project plan.

### Semi-automated acquisition pipeline
1. Publish search content around scope creep, unbilled consulting work and change-order leakage.
2. Free sample SOW-vs-time audit becomes the inbound funnel.
3. Partner channel: fractional CFOs, accounting/engineering practice consultants and PSA implementers.
4. Demonstrate with synthetic projects only.
5. Track opt-in scope-leak categories to refine mapping patterns.
6. Future validation should target 5–100 person professional-services firms with fixed-fee or mixed-fee projects.
7. Any outreach remains low-volume/manual-approved; partner/search acquisition is preferred.
8. Route recurring multi-project demand to the owner.

### Main risks
- Scope interpretation is inherently ambiguous.
- PSA vendors can add similar controls.
- Sensitive client/project documents require careful data handling.

### Stage 4 verdict
**Highest-priority Wave 25 candidate.**

---

## Rank 2 — Staffing approved-time / bill-rate reconciliation audit

### Core promise
Find approved staffing hours that were never billed, billed at the wrong client rate or invoiced inconsistently with the placement/rate card across disconnected systems.

### MVP plan
- Import approved timesheets, placement/rate-card export and client invoice export.
- Normalize worker, client, assignment, date and rate identifiers.
- Flag approved-but-unbilled hours, billed-without-approval hours, stale/incorrect bill rates, overtime/premium mismatches and duplicate invoice candidates.
- Track placement extensions/rate changes.
- Export monthly margin-leak review worksheet with source references.
- Do not calculate employee payroll entitlement or alter invoices automatically.

### Likely stack
- Browser/local CSV/XLSX audit utility.
- Python reconciliation engine.
- Saved ATS/timekeeping/accounting mappings.

### Pricing hypothesis
- CA$15–30 monthly audit.
- CA$20–50/month recurring small-agency plan.

### Semi-automated acquisition pipeline
1. Publish search content around unbilled staffing hours, rate-card leakage and staffing invoice audits.
2. Synthetic monthly audit demonstrates recoverable leakage.
3. Partner with staffing bookkeepers, controllers and ATS/accounting consultants.
4. Focus on agencies using separate ATS/timekeeping/payroll/accounting tools.
5. Track opt-in file schemas to prioritize mappings.
6. Future validation uses redacted/synthetic exports until data handling is established.
7. Any outreach remains partner-led/manual-approved.
8. Route recurring multi-client or consultant use to the owner.

### Main risks
- Integrated staffing systems can reduce the need.
- File mapping complexity.
- Rate rules can include client-specific overtime/premium logic.

### Stage 4 verdict
**Strong direct revenue-leak utility for agencies with fragmented systems.**

---

## Rank 3 — Staffing placement requirement / evidence reconciliation

### Core promise
Before a worker starts or extends an assignment, check whether the evidence on file satisfies the client/site-specific requirements for that exact placement through the planned end date.

### MVP plan
- Import client/job-order requirements and worker credential/evidence records.
- Map required credential/orientation/background-check types.
- Compare validity dates against assignment dates.
- Flag missing requirement, expiring-before-end evidence, site-specific orientation gap and missing client approval/reference.
- Support manual exception/waiver evidence.
- Export placement-readiness checklist.
- Never make hiring or suitability decisions.

### Likely stack
- Local/browser CSV processor.
- Deterministic requirement/evidence matching.
- Minimal worker identifiers and no unnecessary sensitive data.

### Pricing hypothesis
- Free: small placement batch.
- CA$15–30/month small-agency plan.
- Consultant/multi-agency tier later.

### Semi-automated acquisition pipeline
1. Publish content around client-specific staffing compliance and assignment-start readiness.
2. Free placement-readiness template/checker is the inbound funnel.
3. Partner with ATS implementation consultants and staffing compliance advisers.
4. Demonstrate with synthetic worker/assignment records.
5. Track opt-in requirement types to prioritize templates.
6. Future validation should target agencies whose client requirements are maintained outside their ATS.
7. Any outreach remains manual/partner-led.
8. Route multi-client/high-placement-volume users to the owner.

### Main risks
- Modern ATS products increasingly cover assignment-level compliance.
- Sensitive worker data requires strong privacy design.
- Client requirement taxonomies vary.

### Stage 4 verdict
**Useful cross-system compliance QA, but more vulnerable to ATS feature expansion than ranks 1–2.**

## Wave 25 conclusion

Top three:

1. Professional-services scope-change / unbilled-work audit
2. Staffing approved-time / bill-rate reconciliation audit
3. Staffing placement requirement / evidence reconciliation

Wave 25 confirms that HR/recruitment and professional-services software is crowded at the platform level, but smaller margin/evidence gaps remain where contract scope, approved work, placements and billing cross system boundaries.

## Verification record
- Last verified: 2026-10-25
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
