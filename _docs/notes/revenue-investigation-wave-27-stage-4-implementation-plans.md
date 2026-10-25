---
title: Revenue Investigation — Wave 27 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest solar/EV-charging concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 320
permalink: /projects/notes/revenue-investigation-wave-27-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-27, stage-4, solar, ev-charging]
---

# Wave 27 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — EV charger final-rebate evidence reconciliation preflight

### Core promise
Before a contractor/property manager submits the final EV-charger incentive claim, verify that the invoices, contractor forms, inspection evidence, charger details and pre-approval references all describe the same completed project.

### MVP plan
- Start with one or two Canadian rebate programs rather than national coverage.
- User selects program/project type.
- Upload pre-approval/reference, hardware invoice, installation invoice, contractor form, inspection/authorization evidence and optional network-services proof/photos.
- Extract charger make/model/count, contractor, dates, amounts, site address and application/reference numbers.
- Flag missing documents and cross-document mismatches.
- Flag unpaid/non-zero-balance invoice evidence where the program expects paid evidence.
- Flag charger model/count inconsistent with application or contractor form.
- Generate a source-linked final-submission checklist.
- Never determine incentive eligibility or submit claims automatically.

### Likely stack
- Browser/local PDF/image/CSV upload utility.
- Python extraction + deterministic rules.
- Versioned YAML rule packs per program revision.
- Human-review queue for low-confidence fields.

### Pricing hypothesis
- Free: one simple project checklist.
- CA$10–25 per final-package audit.
- CA$15–35/month recurring contractor/consultant plan.

### Semi-automated acquisition pipeline
1. Monitor official EV rebate program pages/forms for requirement changes.
2. Convert changes into proposed rule updates with human verification.
3. Publish exact-intent pages around final application documents and rejected/missing evidence.
4. Free one-project checklist is the inbound funnel.
5. Demonstrate with synthetic project packs only.
6. Partner channel: EV electricians, strata/condo consultants and rebate advisors.
7. Future outreach remains low-volume/manual-approved and secondary to search/partner acquisition.
8. Route multi-project contractor/consultant demand to the owner.

### Main risks
- Program churn and geographic fragmentation.
- Sensitive invoices/project documents.
- Some portals may improve their own validation.

### Stage 4 verdict
**Highest-priority Wave 27 candidate.**

---

## Rank 2 — Solar/battery approved-design vs installed-system change audit

### Core promise
Show a solar/battery installer where the installed equipment or system configuration no longer matches the utility-approved/application design before final interconnection/rebate closeout.

### MVP plan
- Upload approved application/design package plus final installed-system records.
- Extract inverter/battery/module model, quantity, system size/capacity, site address and reference IDs.
- Compare approved vs installed values.
- Flag equipment/model/quantity/system-size changes.
- Flag invoice, inspection declaration or final drawing still referencing superseded equipment.
- Flag installed equipment not represented in the approved project record.
- Generate a factual change-review checklist.
- Never decide whether a utility change request is required or whether a change is technically acceptable.

### Likely stack
- Browser/local file audit utility.
- Python field extraction/matching.
- Optional equipment-list lookup from official qualified-product lists where relevant.

### Pricing hypothesis
- CA$10–25 per project audit.
- CA$20–40/month recurring installer plan.

### Semi-automated acquisition pipeline
1. Publish search content around solar equipment substitutions and interconnection change requests.
2. Free approved-vs-installed checklist is the inbound funnel.
3. Partner with small EPCs and interconnection consultants.
4. Demonstrate using synthetic design/closeout records.
5. Track opt-in change types to prioritize document templates.
6. Future validation should focus on small installers using mixed document/portal workflows, not integrated national EPCs.
7. Outreach remains manual/partner-led.
8. Route recurring installer demand to the owner.

### Main risks
- Design formats vary.
- Some changes are immaterial or already approved.
- Broader solar-compliance platforms can copy this feature.

### Stage 4 verdict
**Strong factual change-control niche for small installers.**

---

## Rank 3 — Solar interconnection / rebate cross-document consistency audit

### Core promise
Before submitting or closing out a solar/battery application, catch mismatched addresses, system sizes, equipment models, permit references and invoice details across the application, drawings, inspection record and rebate documents.

### MVP plan
- Start with a narrow jurisdiction/program such as BC Hydro residential solar/battery workflows.
- Upload application export/form, site plan, single-line diagram, invoice and inspection/contractor declaration.
- Extract deterministic project fields.
- Compare address, system size, equipment model/quantity, permit number, contractor and application/reference numbers.
- Flag inconsistent or missing values with exact document/page references.
- Optional approved-product-list check where an official list exists.
- Export submission-readiness report.
- Do not generate drawings or certify electrical/interconnection compliance.

### Likely stack
- Browser/local document checker.
- Python extraction/rules.
- Versioned jurisdiction/program templates.

### Pricing hypothesis
- Free limited package check.
- CA$10–20 per audit.
- CA$15–30/month recurring installer plan.

### Semi-automated acquisition pipeline
1. Monitor utility contractor-resource pages and sample-document requirements.
2. Publish search content around incomplete/interconnection application delays and rebate invoice requirements.
3. Free small-package checker drives inbound acquisition.
4. Demonstrate with synthetic site plans/SLDs/invoices.
5. Partner with interconnection/application consultants.
6. Future validation focuses on jurisdictions where installer workflows remain document-heavy.
7. Outreach remains manual/partner-led.
8. Route recurring multi-project use to the owner.

### Main risks
- Competition from broad solar-compliance/interconnection platforms.
- Frequent jurisdiction-specific maintenance.
- Document extraction complexity.

### Stage 4 verdict
**Useful, but more exposed to existing solar-compliance platforms than ranks 1–2.**

## Wave 27 conclusion

Top three:

1. EV charger final-rebate evidence reconciliation preflight
2. Solar/battery approved-design vs installed-system change audit
3. Solar interconnection / rebate cross-document consistency audit

Wave 27 confirms that solar/EV software is crowded at CRM, design, interconnection-generation and commissioning layers, but narrow final-application and cross-document QA gaps remain for smaller contractors working across utility portals, rebate programs and disconnected project files.

## Verification record
- Last verified: 2026-10-25
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
