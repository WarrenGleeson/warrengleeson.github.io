---
title: Revenue Investigation — Wave 22 Stage 3 Deep Investigation
summary: Deep investigation of the strongest education/training and childcare administration ideas after direct competition checks.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 299
permalink: /projects/notes/revenue-investigation-wave-22-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-22, deep-investigation, education, childcare]
---

# Wave 22 Stage 3 — Deep Investigation

## 1. Alberta PCC attendance-to-withdrawal rule audit

### Problem
Alberta private career colleges must monitor attendance continuously. Student Aid rules create deterministic withdrawal triggers, including five consecutive unexcused class days and prolonged excused absences. A missed effective date can affect funding, refunds and student records.

### Product
Import an attendance/status export and run a rules-first audit that flags:
- five consecutive class days absent without documented contact/reason;
- prolonged excused absence approaching/exceeding the configured threshold;
- student marked active despite a potential withdrawal trigger;
- withdrawal effective date inconsistent with attendance history;
- missing contact/reason evidence for an absence sequence;
- amended-registration follow-up missing.

The tool does not decide academic standing or student eligibility. It surfaces deterministic administrative exceptions for staff review.

### Distribution
Search around Alberta PCC withdrawal rules, Student Aid attendance, compliance consultants and independent college administrators.

### Monetization hypothesis
Free small cohort audit; CA$15–30 per monthly audit; CA$20–40/month recurring college plan.

### Competition
Full Alberta PCC SIS/audit-readiness products exist, but current research did not identify a focused independent **attendance-to-withdrawal exception audit** that can sit beside an existing SIS or spreadsheet workflow.

### Risk
Rules are high consequence and must be versioned precisely. Attendance calendar definitions and documented excuses require user confirmation.

### Verdict
**Advance.** Strongest Wave 22 concept.

---

## 2. Alberta childcare funding backup-evidence reconciliation audit

### Problem
Alberta childcare monthly funding claims can be reviewed/audited and providers must retain backup evidence such as attendance, child registration, ECE timesheets and payroll. The provincial Auditor General found material claim discrepancies across sampled operators. Some childcare platforms now automate claim preparation, but many operators still need an independent QA pass over the records supporting the submitted numbers.

### Product
Upload claim/export data plus supporting attendance, registration, timesheet and payroll exports. Flag:
- claimed child attendance inconsistent with registration/start/end dates;
- subsidy/claim hours inconsistent with recorded attendance;
- wage-top-up hours without matching staff timesheet/payroll evidence;
- claim advance vs actual claim variance requiring review;
- missing backup records for a claimed line/category;
- prior-period adjustment without linked evidence.

It does not decide subsidy eligibility or submit claims.

### Distribution
Alberta childcare operator search, childcare accountants/bookkeepers, consultants and a free monthly audit template.

### Monetization hypothesis
Free sample month; CA$15–30 per monthly audit; CA$20–40/month recurring operator plan.

### Competition
Canadian childcare platforms increasingly provide claim generation and provincial funding workflows. The surviving wedge is an **independent reconciliation/audit layer** for operators using mixed systems or wanting a second check before/after submission.

### Risk
Sensitive child/staff data and privacy requirements. File formats vary by childcare/payroll system.

### Verdict
**Advance.** Strong financial/compliance angle if privacy and onboarding stay lightweight.

---

## 3. Alberta PCC enrolment-contract amendment consistency preflight

### Problem
Alberta private career colleges use a prescribed Student Enrolment Contract. Changes after signing must be agreed to in writing and initialled by both parties; start/end-date changes are specifically included. Colleges can accumulate amended contracts, email confirmations and SIS dates that no longer agree.

### Product
Upload signed contract plus amendment(s) and optionally a structured student/program record. The checker flags:
- changed program dates not reflected consistently across documents;
- amendment lacking expected signatures/initials;
- conflicting tuition/fee/start/end-date values;
- contract version/template mismatch requiring review;
- program details inconsistent with the user's licensed-program master record;
- amendment with no linked student-file evidence.

The tool does not determine contract validity or provide legal advice.

### Distribution
Alberta PCC compliance search, college administrators, compliance consultants and document-review partners.

### Monetization hypothesis
CA$5–10 per contract/amendment preflight; CA$15–30/month for recurring cohort use.

### Competition
Full SIS products store contracts and student files, but the current review did not identify a focused independent document-consistency checker for prescribed PCC contracts/amendments.

### Risk
Document extraction and legal sensitivity. Must stay confined to factual consistency and missing-evidence checks.

### Verdict
**Advance cautiously.** Clear narrow problem; smaller addressable market than ranks 1–2.

---

## Dropped after deeper review

### Generic PCC audit-readiness SIS
A current Alberta-focused product already markets exactly this outcome, including attendance, grades, admissions and instructor credentials.

### Generic childcare funding claim generator
Canadian childcare-management vendors now generate provincial claim fields and reconcile subsidy hours.

### Generic CE certificate/credit tracker
LMS, association-management and credential platforms already cover attendance, certificates and renewal records.

### PCC student-file completeness platform
Useful but too close to the existing audit-ready SIS category unless narrowed to a specific exception workflow.

## Stage 3 ranking

1. Alberta PCC attendance-to-withdrawal rule audit
2. Alberta childcare funding backup-evidence reconciliation audit
3. Alberta PCC enrolment-contract amendment consistency preflight

## Advance to Stage 4

Advance those three only.

## Verification record

- Last verified: 2026-10-25
- Stage 3 status: complete
- Stage 5: out of scope
