---
title: Revenue Investigation — Wave 27 Stage 3 Deep Investigation
summary: Deep investigation of the strongest solar/EV-charging ideas after direct competition checks.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 319
permalink: /projects/notes/revenue-investigation-wave-27-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-27, deep-investigation, solar, ev-charging]
---

# Wave 27 Stage 3 — Deep Investigation

## 1. EV charger final-rebate evidence reconciliation preflight

### Problem
EV-charger incentive programs can require a specific final package: pre-approval reference, paid/itemized hardware and installation invoices, contractor installation form, inspection evidence, charger make/model, networking proof and sometimes photos or utility support. Installers/property managers often assemble these records from separate contractors, portals and email threads after the physical work is complete.

### Product
Upload the final application inputs plus supporting documents and flag:
- missing paid/itemized invoice;
- charger make/model inconsistency across invoice/application/contractor form;
- charger count or location mismatch;
- missing contractor form/signature;
- missing inspection/authorization evidence;
- network-services proof missing where configured;
- pre-approval/reference mismatch;
- total project cost inconsistent across claim documents;
- missing utility-support document for configured high-load projects.

The product does not decide incentive eligibility or submit claims.

### Distribution
Search around EV charger rebate documents, electricians/EV contractors, strata/property managers and incentive consultants.

### Monetization hypothesis
Free one-project checklist; CA$10–25 per final-package audit; CA$15–35/month for recurring contractors/consultants.

### Competition
Current rebate portals and contractors publish checklists, while project-management platforms cover parts of the workflow. The current review did not surface a strong lightweight independent tool focused on **cross-document final-application consistency across multiple EV rebate programs**.

### Risk
Programs change frequently and requirements differ by geography/project type. Rules must be versioned and clearly scoped.

### Verdict
**Advance.** Strongest Wave 27 concept.

---

## 2. Solar/battery approved-design vs installed-system change audit

### Problem
A solar/battery project can be approved for one equipment set, size or layout and then change during procurement/installation. Utilities may require a formal change request because revised equipment or system parameters can affect approval, interconnection and rebate records. The risk is that the physical system, invoice, permit/inspection record and approved application no longer describe the same project.

### Product
Compare approved application/design records against installed-system closeout evidence. Flag:
- inverter/battery/module model changed;
- system size/capacity changed;
- equipment count changed;
- installed equipment absent from approved list where configured;
- site plan/SLD/invoice/inspection document describing inconsistent equipment;
- installation date/startup preceding required approval/change process;
- closeout package still referencing superseded approved configuration.

The tool does not determine engineering acceptability or authorize the change.

### Distribution
Solar contractor search, interconnection consultants, small EPCs and utility-application service providers.

### Monetization hypothesis
CA$10–25 per project audit; CA$20–40/month recurring installer plan.

### Competition
Interconnection/compliance platforms validate project packages and larger installer systems manage change control. The surviving wedge is a simple **approved-vs-installed factual diff** for small contractors using mixed documents/portals.

### Risk
Design formats vary and some changes are immaterial or already approved. Output must remain factual and review-oriented.

### Verdict
**Advance.** Clear cross-document problem with measurable consequences.

---

## 3. Solar interconnection / rebate cross-document consistency audit

### Problem
A residential solar/battery project can involve an interconnection application, site plan, single-line diagram, qualified-product lists, permit/inspection record and paid rebate invoice. Utilities explicitly warn that incomplete or inconsistent information can delay applications. Small installers may have every document, but conflicting addresses, sizes, equipment models or permit references can still create rework.

### Product
Upload the application package and compare deterministic fields across documents:
- customer/site address;
- system size/capacity;
- inverter/battery model and quantity;
- permit number;
- project/application/reference number;
- contractor identity;
- invoice equipment descriptions;
- site-plan/SLD equipment naming;
- inspection declaration project size/address.

Output is a mismatch report with exact source references. It does not generate engineering drawings or certify utility compliance.

### Distribution
BC/Canadian solar contractor search, interconnection consultants and a free small-package checker.

### Monetization hypothesis
Free limited package; CA$10–20 per audit; CA$15–30/month recurring installer plan.

### Competition
Broad solar compliance platforms now include document checks, and interconnection platforms can perform cross-document validation. The differentiation is a narrower, lower-cost **document-consistency audit for small installer workflows**, especially in jurisdictions not well served by larger platforms.

### Risk
Competition is closer here than ranks 1–2. Utility forms and rules change often.

### Verdict
**Advance cautiously.** Useful, but moat depends on jurisdiction-specific rule quality and pricing.

---

## Dropped after deeper review

### Generic solar compliance/warranty checker
Current dedicated platforms already provide broad compliance, warranty, recall and rebate scanning.

### Generic interconnection-package generation
Current products already generate and validate interconnection packages.

### Generic commissioning platform
Current commissioning software already captures equipment, serials, tests, signatures and retests for solar/EV/BMS work.

## Stage 3 ranking

1. EV charger final-rebate evidence reconciliation preflight
2. Solar/battery approved-design vs installed-system change audit
3. Solar interconnection / rebate cross-document consistency audit

## Advance to Stage 4
Advance those three only.

## Verification record
- Last verified: 2026-10-25
- Stage 3 status: complete
- Stage 5: out of scope
