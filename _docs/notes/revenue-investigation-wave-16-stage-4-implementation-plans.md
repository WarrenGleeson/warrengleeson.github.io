---
title: Revenue Investigation — Wave 16 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest construction/field-trade concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-20
updated: 2026-10-20
last_verified: 2026-10-20
owner: High Director
order: 276
permalink: /projects/notes/revenue-investigation-wave-16-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-16, stage-4, construction]
---

# Wave 16 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — Contractor rebate-document / invoice preflight

### Core promise
Before an HVAC/electrical contractor hands rebate paperwork to a customer, check whether the invoice and supporting documents contain the fields/evidence required by the selected rebate program.

### MVP plan
- Start with a narrow BC program set rather than national coverage.
- User selects program/project type.
- Upload invoice plus optional supporting PDFs/images.
- Extract only deterministic fields needed for preflight: invoice date/number, contractor identity, paid status, equipment make/model, permit/reference numbers and expected supporting documents.
- Versioned checklist identifies missing items and application deadline.
- Generate a contractor/customer handoff checklist.
- Explicitly distinguish “document complete” from “rebate eligible.”
- No automated rebate submission.

### Likely stack
- Browser upload utility.
- Python document parser/rule engine.
- Versioned YAML rules per rebate/program revision.
- Optional local/manual-entry fallback for fields extraction cannot confidently read.

### Pricing hypothesis
- Free: one simple document check.
- CA$5–10: one completed rebate-pack preflight.
- CA$15–30/month: recurring contractor plan.

### Semi-automated acquisition pipeline
1. Monitor official BC Hydro/Go Electric/Better Homes contractor resource pages and program guides.
2. Diff requirement changes into proposed rules; require human verification before updating checks.
3. Publish exact-intent pages around specific invoice/document requirements.
4. Free single-document checker is the main inbound funnel.
5. Build synthetic sample invoices/docs to demonstrate missing-field detection.
6. Track opt-in missing-field categories to identify which programs cause the most callbacks/resubmissions.
7. Future validation could involve HVAC/electrical associations, bookkeepers and rebate advisors; any direct outreach remains low-volume/manual-approved.
8. Route contractors with repeated monthly usage to the owner as higher-value leads.

### Main risks
- Program rules change often.
- Document OCR/extraction can be noisy.
- Contractors may see paperwork as the homeowner's problem unless the tool clearly reduces callbacks/reputation issues.

### Stage 4 verdict
**Highest-priority Wave 16 candidate.**

---

## Rank 2 — WorkSafeBC subcontractor clearance evidence tracker

### Core promise
Help small BC prime contractors prove they obtained the required subcontractor clearance evidence before/during/after work without replacing WorkSafeBC's official clearance-letter system.

### MVP plan
- One record per subcontractor and project/contract.
- Store legal name, WorkSafeBC account number, project dates and responsible internal owner.
- User uploads or links the official clearance letter.
- Extract/status-check letter date and advance-clearance date where present.
- Flag missing pre-work evidence, coverage gaps and missing post-work closeout clearance.
- Calendar/reminder view for GoldStar/advance-clearance expiry and project closeout.
- Export project clearance evidence index.
- Do not independently declare a subcontractor “in good standing”; official WorkSafeBC evidence remains authoritative.

### Likely stack
- Lightweight browser SaaS.
- PDF metadata/text extraction.
- CSV subcontractor import.
- Scheduled reminders.

### Pricing hypothesis
- Free: up to 5 subcontractors.
- CA$10–20/month: active contractor portfolio.
- One-off project-closeout report option.

### Semi-automated acquisition pipeline
1. Maintain factual search content around WorkSafeBC clearance timing/evidence and prime-contractor liability.
2. Free spreadsheet/import template + 5-subcontractor tier becomes the inbound funnel.
3. Partner channel potential: construction bookkeepers, safety consultants and small GC associations.
4. Track opt-in evidence-gap patterns to refine reminders/workflows.
5. Demonstrate only with synthetic/sample letters.
6. Future validation should focus on small GCs/prime contractors that hire multiple subtrades, not individual owner-operators with no subcontractors.
7. Any direct outreach remains manual and limited; search/partner referrals are the preferred acquisition channel.
8. Route multi-project/accounting-partner interest to the owner.

### Main risks
- BC-only market is narrow.
- Official workflow changes could reduce the need.
- Low monthly price ceiling unless expanded to other provinces' analogous clearance/evidence workflows.

### Stage 4 verdict
**Narrow but concrete recurring administrative niche.**

---

## Rank 3 — Retrospective T&M revenue-leak audit

### Core promise
At month-end, compare approved T&M/extra-work tickets with invoices and rate schedules to find signed work that was never fully billed.

### MVP plan
- Upload approved tickets, rate sheet and invoice export/PDF.
- Match by job/ticket/date/reference with manual confirmation where confidence is low.
- Compare labour hours/rates, equipment, materials, markup and invoice inclusion.
- Flag unbilled approved ticket, partial billing, rate mismatch, duplicate candidate and unsupported invoice line.
- Export a finance review worksheet.
- Do not replace ticket capture, accounting or invoicing software.

### Likely stack
- Browser upload tool.
- Python extraction/matching engine.
- Confidence-scored matching with manual-review queue.

### Pricing hypothesis
- CA$10–25 per audit.
- CA$20–40/month for recurring small subcontractor use.

### Semi-automated acquisition pipeline
1. Publish search pages around unbilled extras, signed T&M ticket reconciliation and month-end construction billing leakage.
2. Offer a synthetic/sample audit as the education funnel.
3. Partner potential: construction bookkeepers/fractional controllers.
4. Focus acquisition on subcontractors that still use PDF/paper tickets rather than users already committed to integrated field-ticket software.
5. Track opt-in mismatch categories to improve supported formats.
6. Future validation should use customer-supplied redacted documents only with explicit handling rules.
7. Keep outreach low-volume/manual-approved; bookkeeping referrals and search are better long-term channels.
8. Route recurring multi-job users to the owner.

### Main risks
- Strong adjacent competitors already reconcile tickets and invoices.
- Document extraction/matching complexity.
- Users may eventually migrate to integrated platforms that eliminate the need.

### Stage 4 verdict
**Viable as a low-commitment audit tool, but materially weaker moat than ranks 1–2.**

## Wave 16 conclusion

Top three:

1. Contractor rebate-document / invoice preflight
2. WorkSafeBC subcontractor clearance evidence tracker
3. Retrospective T&M revenue-leak audit

Wave 16 validates the decision to expand beyond software/platform sectors: construction and field trades contain small administrative problems tied directly to cash flow, customer callbacks and liability, without requiring a full contractor-management platform.

## Verification record

- Last verified: 2026-10-20
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
