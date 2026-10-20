---
title: Revenue Investigation — Wave 18 Stage 3 Deep Investigation
summary: Deep investigation of the strongest non-clinical healthcare administration ideas after competition checks.
section: notes
doc_type: note
status: active
created: 2026-10-20
updated: 2026-10-20
last_verified: 2026-10-20
owner: High Director
order: 283
permalink: /projects/notes/revenue-investigation-wave-18-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-18, deep-investigation, healthcare-admin]
---

# Wave 18 Stage 3 — Deep Investigation

## 1. Allied-health insurer / claim document readiness workspace

### Problem
Physiotherapy, chiropractic and similar clinics often work across private benefits, ICBC and WorkSafeBC. Each payer can require different claim numbers, reports, extension requests, forms and submission timing. The clinical work may be complete while the administrative record is still missing one item needed for billing or continuation.

### Product
A non-clinical payer-readiness workspace:
- payer/program selection;
- claim/reference number presence;
- required administrative forms/reports;
- report due dates;
- extension-request status;
- submission method/status;
- missing-document queue;
- payment-status follow-up reference.

The tool does not evaluate treatment appropriateness or recommend care.

### Distribution
Search around ICBC/WorkSafe physiotherapy forms, clinic admin communities, billing consultants and a free payer checklist.

### Monetization hypothesis
Free small caseload; CA$10–25/month per clinic/admin team; optional one-off cleanup/report.

### Competition
Practice-management platforms cover scheduling/notes/billing broadly, but current official payer workflows remain fragmented across different portals/forms. The wedge is a lightweight payer-document readiness layer rather than replacing the clinic PMS.

### Risk
Patient information is sensitive. Any future product would need strong privacy/security design, minimum-data handling and ideally integration or local processing rather than duplicating full records.

### Verdict
**Advance.** Strongest Wave 18 concept.

---

## 2. MSP / ICBC billing-evidence QA preflight

### Problem
BC practitioners remain accountable for correct claim coding and audit support. Current MSP guidance includes referral-dependent specialist billing and MVA-specific claim identification, while service-verification audits can examine whether billed services were actually provided.

### Product
A pre-submission QA utility that checks a claim export or manually entered claim batch for deterministic administrative issues:
- required referral reference/evidence flag where configured;
- MVA indicator and ICBC claim-number presence where supplied;
- duplicate claim candidates;
- missing provider/payee identifiers;
- missing supporting-document reference in the clinic's own checklist;
- submission-deadline warnings.

It does not recommend billing codes or determine clinical eligibility for a fee item.

### Distribution
BC physician billing search, billing agents/consultants, small specialist offices and a free batch preflight.

### Monetization hypothesis
Free small batch; CA$15–30 per monthly audit or CA$15–40/month recurring clinic plan.

### Competition
BC medical billing platforms already submit claims and manage rejections. The surviving wedge is an independent **evidence/readiness QA pass before submission or audit**, especially for clinics using existing billing services but wanting a second check.

### Risk
Rules are high consequence and must remain narrow. Avoid automated code selection or medical-record interpretation.

### Verdict
**Advance cautiously.** Useful but closer to mature billing software.

---

## 3. Rejected-claim reason normalizer + resubmission checklist

### Problem
Small clinics can receive rejected claims from multiple payers with different wording and administrative next steps. Staff repeatedly translate those messages into the same internal actions: missing identifier, stale authorization, incorrect submission path, missing report or duplicate submission.

### Product
Paste/import rejection messages and map them to a normalized internal category plus a deterministic resubmission checklist. The tool tracks resolution status and recurring rejection categories by payer.

### Distribution
Allied-health/medical billing search, clinic admin communities and billing-consultant partnerships.

### Monetization hypothesis
Free low-volume use; CA$10–20/month for recurring clinic use.

### Competition
Many billing platforms already provide payer-specific rejection handling. The niche is strongest when a clinic deals with several disconnected payer systems and wants one admin queue.

### Risk
Low price ceiling and close adjacency to existing billing systems.

### Verdict
**Advance cautiously.** Better as a focused admin tool or feature than a large standalone company.

---

## Dropped after deeper review

### Generic referral completeness / tracking
BC's DRO/Ocean/Pathways ecosystem is explicitly targeting digital referral completeness, tracking and missing-information follow-up.

### Generic MSP billing platform
Dedicated BC billing products already cover Teleplan submission, rejection handling and reporting.

### Pharmacy transfer-record administration
Highly integrated/regulated pharmacy systems make a standalone workflow tool unattractive.

### New-patient intake completeness
Crowded by digital intake/form products and practice-management platforms.

## Stage 3 ranking

1. Allied-health insurer / claim document readiness workspace
2. MSP / ICBC billing-evidence QA preflight
3. Rejected-claim reason normalizer + resubmission checklist

## Advance to Stage 4

Advance those three only.

## Verification record

- Last verified: 2026-10-20
- Stage 3 status: complete
- Stage 5: out of scope
