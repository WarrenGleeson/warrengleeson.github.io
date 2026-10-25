---
title: Revenue Investigation — Wave 22 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest education/training and childcare administration concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 300
permalink: /projects/notes/revenue-investigation-wave-22-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-22, stage-4, education, childcare]
---

# Wave 22 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — Alberta PCC attendance-to-withdrawal rule audit

### Core promise
Give an Alberta private career college a fast independent audit of attendance data to find students whose attendance history may require withdrawal/status review before funding or compliance problems compound.

### MVP plan
- Import CSV/XLSX attendance and student-status data.
- Configure instructional calendar and attendance codes.
- Apply versioned deterministic rules for consecutive unexcused absences and prolonged excused absences.
- Flag active students with potential withdrawal triggers.
- Calculate candidate effective date from attendance history for staff review.
- Flag missing contact/reason evidence where the college records those fields.
- Export an exception queue with exact source rows and rule references.
- Never automatically withdraw a student or change Student Aid records.

### Likely stack
- Local/browser file-processing utility.
- Python rules engine with versioned Alberta rule pack.
- Saved column mappings for repeat users.

### Pricing hypothesis
- Free: small cohort/sample audit.
- CA$15–30: monthly cohort audit.
- CA$20–40/month: recurring college plan.

### Semi-automated acquisition pipeline
1. Monitor Alberta Student Aid/PCC withdrawal guidance for rule changes.
2. Publish exact-intent content around five-day absence rules, withdrawal dates and attendance audit preparation.
3. Free sample/CSV checker is the main inbound funnel.
4. Demonstrate using synthetic attendance records only.
5. Partner channel: PCC compliance consultants, bookkeepers and SIS implementers.
6. Track opt-in exception categories to refine calendar/attendance-code mappings.
7. Future outreach remains low-volume/manual-approved and targets administrators/compliance consultants rather than students.
8. Route recurring/multi-program college demand to the owner.

### Main risks
- High-consequence rules require precise maintenance.
- Existing SIS vendors can add equivalent exception checks.
- Attendance-code mapping and class calendars vary.

### Stage 4 verdict
**Highest-priority Wave 22 candidate.**

---

## Rank 2 — Alberta childcare funding backup-evidence reconciliation audit

### Core promise
Before or after an Alberta childcare monthly funding claim, independently reconcile claimed child/staff hours against the attendance, registration, timesheet and payroll evidence the operator must retain.

### MVP plan
- Import claim/export file, child registration list, attendance export, staff timesheets and payroll summary.
- Map child/staff identifiers with manual review for ambiguous matches.
- Flag claimed attendance outside registration period.
- Flag claimed/subsidy hours inconsistent with attendance records.
- Flag wage-top-up hours without corresponding timesheet/payroll support.
- Compare claim advance with actual claim and identify unexplained variance.
- Link adjustments to supporting evidence.
- Produce a monthly audit worksheet with source references.
- Never decide funding eligibility or submit/adjust claims automatically.

### Likely stack
- Local/browser CSV/XLSX processor to minimize sensitive-data exposure.
- Python reconciliation engine.
- Saved mappings for common childcare/payroll exports.

### Pricing hypothesis
- Free: synthetic/sample month or limited rows.
- CA$15–30 per monthly audit.
- CA$20–40/month recurring operator plan.

### Semi-automated acquisition pipeline
1. Monitor Alberta childcare claim/financial reporting guidance.
2. Publish search content around funding claim audits, backup records and wage-top-up reconciliation.
3. Free monthly audit template/sample checker drives inbound acquisition.
4. Partner with childcare bookkeepers/accountants and funding consultants.
5. Demonstrate with synthetic records only.
6. Track opt-in file formats to prioritize integrations/mappings.
7. Future validation should use redacted/sample exports with explicit privacy handling.
8. Route multi-centre/bookkeeper demand to the owner.

### Main risks
- Sensitive child/staff information.
- Childcare-management vendors already automate much of the claim workflow.
- Provincial rules and funding programs change.

### Stage 4 verdict
**Strong financial/compliance QA niche for operators using mixed systems or wanting a second check.**

---

## Rank 3 — Alberta PCC enrolment-contract amendment consistency preflight

### Core promise
Check whether a signed Alberta Student Enrolment Contract, later amendments and the college's own student/program record still agree on the factual details staff will need during a compliance review.

### MVP plan
- Upload original signed contract plus amendment(s).
- Optional CSV/student-record import.
- Extract program name, dates, tuition/fees and signature/initial fields where readable.
- Compare before/after values and structured record.
- Flag unreflected date changes, conflicting tuition/program details, missing signatures/initials and unmatched amendments.
- Version/reference the contract template used.
- Export a factual consistency report with source-page links.
- Do not determine contract validity or legal enforceability.

### Likely stack
- Browser/local PDF utility.
- Text extraction plus deterministic field comparison.
- Human-review queue for low-confidence extraction.

### Pricing hypothesis
- CA$5–10 per contract/amendment pack.
- CA$15–30/month for recurring cohort reviews.

### Semi-automated acquisition pipeline
1. Monitor Alberta PCC contract guidance/template changes.
2. Publish narrowly targeted pages around contract amendments, date changes and desk-audit preparation.
3. Synthetic contract comparison demonstrates the tool.
4. Partner channel: PCC compliance consultants and administrators.
5. Track opt-in mismatch categories to improve extraction templates.
6. Future validation uses synthetic/redacted contracts only until privacy design is finalized.
7. Any outreach remains partner-led/manual.
8. Route high-volume college/compliance-consultant use to the owner.

### Main risks
- Small market.
- Document extraction variability.
- Legal sensitivity requires conservative wording.

### Stage 4 verdict
**Useful narrow document QA utility, but smaller market than ranks 1–2.**

## Wave 22 conclusion

Top three:

1. Alberta PCC attendance-to-withdrawal rule audit
2. Alberta childcare funding backup-evidence reconciliation audit
3. Alberta PCC enrolment-contract amendment consistency preflight

Wave 22 confirms that education/childcare software is crowded at the LMS, SIS and childcare-management layers, but narrower independent audit/reconciliation tools remain plausible where operators must preserve evidence across multiple systems.

## Verification record

- Last verified: 2026-10-25
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
