---
title: Revenue Investigation — Wave 25 Stage 3 Deep Investigation
summary: Deep investigation of the strongest HR/recruitment and professional-services ideas after direct competition checks.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 311
permalink: /projects/notes/revenue-investigation-wave-25-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-25, deep-investigation, recruitment, professional-services]
---

# Wave 25 Stage 3 — Deep Investigation

## 1. Professional-services scope-change / unbilled-work audit

### Problem
Consulting, accounting, engineering and other professional-services firms routinely perform small client-requested changes before formal amendments or fee changes are documented. Industry guidance continues to warn that undocumented scope changes create both margin leakage and contractual risk.

### Product
Import the executed SOW/engagement letter, approved amendments/change orders, time-entry/task export and optional client-request log/email summary. Flag:
- tasks/time entries that do not map cleanly to contracted deliverables;
- work performed after a client change request but before an approved amendment;
- fixed-fee burn associated with unapproved scope additions;
- approved change order with no corresponding invoice uplift;
- recurring client requests that exceed configured revision/meeting/site limits;
- deliverables or milestones added without fee/schedule coverage.

The tool surfaces candidate scope leakage for human review; it does not interpret legal rights or automatically bill clients.

### Distribution
Search around consulting scope creep, unbilled work and change-order leakage; accounting/engineering consultants and fractional CFO/ops advisers.

### Monetization hypothesis
CA$15–30 per project audit; CA$20–50/month for recurring multi-project firms.

### Competition
PSA platforms track projects/budgets, and some newer tools explicitly discuss scope creep. The surviving wedge is an independent **contract/SOW-to-time/workstream audit** for firms that do not want to replace their PSA/accounting stack.

### Risk
Mapping time entries/tasks to contract scope can be ambiguous. Output must stay confidence-scored and review-oriented.

### Verdict
**Advance.** Strongest Wave 25 concept.

---

## 2. Staffing placement requirement / evidence reconciliation

### Problem
A staffing agency can have a worker marked generally compliant while a particular client/site/assignment requires an extra credential, orientation, background check or approval. The operational risk is at placement time: does this worker have the evidence required for this exact assignment and is it still valid through the assignment period?

### Product
Import client/job-order requirements plus worker credential/evidence export. Flag:
- required credential missing for the assignment;
- credential expires before assignment end;
- client/site-specific orientation or approval missing;
- evidence present but not tied to the required credential type;
- assignment extension that exceeds document validity;
- placement record lacking required client approval/reference.

The tool does not make hiring decisions; it checks administrative evidence against user-defined assignment requirements.

### Distribution
Staffing compliance search, small agency consultants and ATS implementation partners.

### Monetization hypothesis
Free small placement audit; CA$15–30/month for small agencies; consultant/multi-client tier later.

### Competition
Many staffing ATS platforms already track credentials and can block assignments. The narrower wedge is an independent **cross-system/client-specific placement audit** for agencies whose client requirements live outside the ATS or differ by site.

### Risk
Could be absorbed by modern ATS products. Sensitive worker data requires minimum-data/local-processing design.

### Verdict
**Advance cautiously.** Clear pain but closer to existing staffing software.

---

## 3. Staffing approved-time / bill-rate reconciliation audit

### Problem
Staffing firms often move data across ATS/timekeeping, payroll and accounting/invoicing systems. Leakage occurs when approved hours are not invoiced, bill rates differ from the client rate card, overtime/shift premiums are applied inconsistently or placement extensions use stale rates.

### Product
Import approved timesheets, placement/rate-card data and client invoice export. Flag:
- approved hours not billed;
- billed hours exceeding approved time;
- bill rate inconsistent with placement/client rate card;
- overtime/premium mismatch;
- placement extension still using old rate;
- approved shift with no invoice line;
- duplicate invoice candidate.

It audits commercial records only and does not calculate employee payroll entitlements.

### Distribution
Staffing finance/bookkeeper search, staffing-accounting consultants and fractional controllers.

### Monetization hypothesis
CA$15–30 monthly audit; CA$20–50/month recurring agency plan.

### Competition
Integrated staffing platforms already connect timesheets, payroll and billing. The surviving niche is agencies using disconnected tools or wanting an independent second-pass margin audit.

### Risk
Market narrows as agencies consolidate software. File mapping may be complex.

### Verdict
**Advance.** Strong direct revenue-leak angle.

---

## Dropped after deeper review

### Credential-expiry tracking
Already standard in staffing/compliance platforms, often with assignment blocking.

### Client-document collection
Extremely crowded across accounting, legal and professional-services workflows.

### Generic PSA / practice management
Mature category with project, budget, time and billing controls.

### Temp-to-perm trigger tracker
Useful but commonly handled inside ATS/placement systems; too feature-like as a standalone product.

## Stage 3 ranking

1. Professional-services scope-change / unbilled-work audit
2. Staffing approved-time / bill-rate reconciliation audit
3. Staffing placement requirement / evidence reconciliation

## Advance to Stage 4
Advance those three only.

## Verification record
- Last verified: 2026-10-25
- Stage 3 status: complete
- Stage 5: out of scope
