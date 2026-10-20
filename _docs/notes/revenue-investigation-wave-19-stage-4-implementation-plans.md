---
title: Revenue Investigation — Wave 19 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest agriculture and small-food-production concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-20
updated: 2026-10-20
last_verified: 2026-10-20
owner: High Director
order: 288
permalink: /projects/notes/revenue-investigation-wave-19-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-19, stage-4, food-production]
---

# Wave 19 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — Actual purchases vs approved-supplier / approved-scope audit

### Core promise
Find purchases from suppliers, facilities or material categories that fall outside a small food processor's own approved-supplier register before an auditor finds them.

### MVP plan
- Upload approved-supplier register plus AP/purchase export.
- User maps supplier/material columns once.
- Normalize supplier names conservatively.
- Compare each purchase against approved supplier + material/category scope.
- Flag unapproved supplier, out-of-scope material, site/name mismatch, approval/certificate expiry and temporary-exception evidence gaps.
- Confidence-scored manual-review queue for fuzzy matches.
- Export audit worksheet with exact source rows.
- Never approve/reject suppliers automatically.

### Likely stack
- Browser/local CSV/XLSX utility.
- Python deterministic matching/rules.
- Optional saved mappings for repeat customers.

### Pricing hypothesis
- Free: small sample audit.
- CA$15–30: periodic audit.
- CA$15–35/month: recurring monthly/quarterly check.

### Semi-automated acquisition pipeline
1. Publish search content around approved supplier list audits and purchases outside approved scope.
2. Free CSV template/checker drives inbound discovery.
3. Partner with food-safety consultants, auditors and bookkeepers serving small processors.
4. Demonstrate using synthetic supplier/purchase files.
5. Track opt-in mismatch categories to refine name/material matching.
6. Future validation should target spreadsheet/accounting-based businesses rather than companies already on integrated food ERPs.
7. Any outreach remains low-volume/manual-approved; consultant referrals/search are preferred.
8. Route recurring multi-site/consultant demand to the owner.

### Main risks
- Supplier normalization can produce false positives.
- Integrated QMS/ERP adoption can eliminate the need.
- Procedures vary by business/customer certification standard.

### Stage 4 verdict
**Highest-priority Wave 19 candidate.**

---

## Rank 2 — CFIA traceability-request export readiness preflight

### Core promise
Check whether a processor's existing receiving, production and shipping spreadsheets can actually be assembled into a clean, single-file CFIA traceability response without reconstructing records under pressure.

### MVP plan
- Upload CSV/XLSX exports from existing systems.
- User identifies receiving, production/batch and shipment datasets.
- Map required fields: common name, lot/identifier, supplier/customer, addresses and dates.
- Validate joinability between supplier lots, finished lots and outbound shipments.
- Flag missing fields, orphan identifiers, duplicate/conflicting values and nonstandard formats.
- Produce one normalized reviewable workbook/CSV plus a gap report.
- Preserve source-row references.
- Do not make recall-scope or food-safety decisions.

### Likely stack
- Local/browser file processing where practical.
- Python normalization/join engine.
- Saved schema mappings for recurring users.

### Pricing hypothesis
- Free: one-lot/sample preflight.
- CA$10–25: full export audit.
- CA$10–25/month: recurring readiness checks.

### Semi-automated acquisition pipeline
1. Monitor CFIA traceability guidance for record/export changes.
2. Publish search pages around CFIA one-step-back/one-step-forward record exports and electronic single-file requirements.
3. Free sample/template drives inbound acquisition.
4. Synthetic spreadsheet sets demonstrate gap detection.
5. Consultant/auditor referrals are the preferred secondary channel.
6. Track opt-in schema patterns to support common accounting/production exports.
7. Future direct outreach, if any, remains manual and tightly targeted.
8. Route recurring/co-packer consultant demand to the owner.

### Main risks
- Free mock-recall/CSV tools are close substitutes.
- Differentiation depends on normalization/export-quality workflow.
- Must avoid implying CFIA approval or certification.

### Stage 4 verdict
**Useful if kept focused on arbitrary existing-record export readiness.**

---

## Rank 3 — Received-lot document/evidence matcher

### Core promise
Show whether each received ingredient/packaging lot has the supplier evidence the processor's own procedure expects, without requiring a supplier-management platform migration.

### MVP plan
- Import receiving records.
- Upload or index supplier-document folder.
- User configures expected evidence by ingredient/material category.
- Extract supplier, product/material, lot/reference, document type, date/version and expiry where available.
- Match documents to received lots with confidence score.
- Flag missing evidence, wrong lot/product/supplier, expired/outdated document and orphan document.
- Human-review queue for ambiguous matches.
- Export receiving-evidence index.
- Do not decide whether a COA/certificate is legally sufficient.

### Likely stack
- Python document/text extraction + deterministic matcher.
- Browser upload/local folder index option.
- Lightweight recurring workspace only if demand supports it.

### Pricing hypothesis
- CA$10–25 per monthly/batch review.
- CA$15–35/month recurring receiving QA.

### Semi-automated acquisition pipeline
1. Publish content around matching COAs/certificates to received lots and audit preparation.
2. Offer a synthetic folder + receiving-file demo checker.
3. Food-safety consultants and co-packer advisors are the main partner channel.
4. Focus on operations still using email/shared drives/spreadsheets.
5. Track opt-in document types to prioritize extraction support.
6. Future validation should use redacted/synthetic documents until privacy/security design is established.
7. Outreach remains manual/partner-led.
8. Route recurring high-volume receiving teams to the owner.

### Main risks
- OCR/document extraction variability.
- Supplier-management platforms already solve the workflow for more mature companies.
- Many businesses may not require evidence per individual received lot.

### Stage 4 verdict
**Real paperwork pain, but narrower and technically harder than ranks 1–2.**

## Wave 19 conclusion

Top three:

1. Actual purchases vs approved-supplier / approved-scope audit
2. CFIA traceability-request export readiness preflight
3. Received-lot document/evidence matcher

Wave 19 confirms that agriculture/food has heavy existing software coverage, but a gap remains for small processors that want to keep their spreadsheets/accounting systems while independently checking record quality before audits or traceability requests.

## Verification record

- Last verified: 2026-10-20
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
