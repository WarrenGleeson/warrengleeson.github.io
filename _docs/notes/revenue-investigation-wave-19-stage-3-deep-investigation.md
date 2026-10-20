---
title: Revenue Investigation — Wave 19 Stage 3 Deep Investigation
summary: Deep investigation of the strongest agriculture and small-food-production ideas after direct competition checks.
section: notes
doc_type: note
status: active
created: 2026-10-20
updated: 2026-10-20
last_verified: 2026-10-20
owner: High Director
order: 287
permalink: /projects/notes/revenue-investigation-wave-19-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-19, deep-investigation, food-production]
---

# Wave 19 Stage 3 — Deep Investigation

## 1. Actual purchases vs approved-supplier / approved-scope audit

### Problem
Small processors may maintain an approved supplier list in one spreadsheet while purchasing happens through accounting software, email, cards or ad-hoc POs. The practical failure is not that the list is missing—it is that a real purchase can come from a supplier, facility or material outside the approved scope without anyone noticing until an audit.

### Product
Upload an approved-supplier register plus purchase/AP export for a selected period. Normalize supplier names and material descriptions, then flag:
- supplier not on approved list;
- approved supplier used for an unapproved material/category;
- supplier/site name mismatch requiring review;
- purchase after approval/certificate expiry where dates are present;
- temporary-exception purchase without linked evidence;
- approved suppliers never used / stale records.

The tool does not approve suppliers or assess food safety.

### Distribution
Search around approved supplier audits, SQF/BRCGS supplier lists and spreadsheet-based QA; partnerships with food-safety consultants/bookkeepers.

### Monetization hypothesis
Free sample/small audit; CA$15–30 per periodic audit; CA$15–35/month for recurring small-processor checks.

### Competition
Food QMS/ERP products already prevent or flag purchases inside their own systems, and supplier-management platforms are mature. The surviving wedge is an **independent cross-check for processors that are not ready to migrate purchasing into a food QMS**.

### Risk
Supplier-name/material matching can be messy and needs confidence-based review. This is a bridge product and may disappear when customers adopt integrated systems.

### Verdict
**Advance.** Strongest Wave 19 concept.

---

## 2. CFIA traceability-request export readiness preflight

### Problem
CFIA requires covered businesses to keep traceability records that identify the food/lot plus one-step-back and one-step-forward information. Electronic records must be accessible in Canada and, when requested, provided in a single file in a format easily opened with standard commercial software. Small processors may have the necessary facts spread across receiving, batch and shipping spreadsheets but not know whether they can assemble a clean request-ready export quickly.

### Product
A local/browser preflight that accepts the business's own CSV/XLSX exports and checks whether the selected period/lot can produce a regulator-ready evidence file:
- required supplier/customer/date/lot/common-name fields;
- missing or orphan lot links;
- inconsistent column formats;
- duplicate/conflicting identifiers;
- rows that cannot be joined deterministically;
- output into one reviewable CSV/XLSX package with a gap report.

The tool describes record completeness only; it does not make recall decisions.

### Distribution
Search around CFIA traceability records/export requests, small-processor consultants and downloadable spreadsheet templates.

### Monetization hypothesis
Free one-lot/sample preflight; CA$10–25 per full export audit; CA$10–25/month recurring readiness checks.

### Competition
TraceBench already performs free mock-recall tracing from CSVs, while full QMS/ERP platforms export traceability records. The surviving distinction is **request-format/readiness QA across arbitrary existing records**, not mock recall or ongoing traceability capture.

### Risk
The differentiation from free trace tools is narrow. It must materially improve file normalization/gap evidence and not overclaim CFIA acceptance.

### Verdict
**Advance cautiously.** Useful but differentiation must stay crisp.

---

## 3. Received-lot document/evidence matcher

### Problem
A small food processor can receive an ingredient or packaging lot with several related records—purchase/invoice, receiving entry, supplier lot code, COA/specification/certificate, and perhaps an exception or corrective action. The records often live in separate folders/email/spreadsheets. During an audit, staff need to prove that the lot they actually received connects to the expected supplier evidence.

### Product
Upload/import receiving rows and a folder/index of supplier documents. The tool creates a review queue showing:
- received lot with no linked supplier evidence where the user's procedure expects it;
- document referring to a different lot/product/supplier;
- document date/version outside the configured validity window;
- duplicate/unmatched COA or certificate;
- missing receiving-record link to the approved supplier/material record.

User-configured procedures define which document types are expected; the tool does not decide what testing/certificate is legally required.

### Distribution
Search around COA matching, receiving QA and audit preparation; food-safety consultant referrals.

### Monetization hypothesis
CA$10–25 per batch/monthly review; CA$15–35/month for recurring receiving evidence QA.

### Competition
Supplier-management systems already store certificates/COAs and integrated food ERPs link receiving to supplier records. The wedge is a lightweight independent matcher for processors still using shared folders/accounting/spreadsheets.

### Risk
Document extraction and lot/product matching may be noisy. The market may prefer migrating directly to a QMS if volume grows.

### Verdict
**Advance cautiously.** Clear administrative pain, moderate implementation complexity.

---

## Dropped after deeper review

### Batch record vs finished-label lot-code consistency checker
Current batch systems such as BatchDash and Crown already bind/generated finished-good lot codes into batch and label workflows, weakening a standalone checker.

### Generic approved-supplier spreadsheet audit
A current free tool already audits approved-supplier spreadsheets for missing/expired evidence.

### Generic mock recall / traceability graph
Free CSV-based trace tools and multiple low-cost food traceability platforms already cover this directly.

### Formula/specification-to-label management
Mature specification-management suites already connect formulations, allergens, nutrition and packaging/labels.

### Cold-storage / harvest traceability
Produce-specific systems already handle field, harvest, storage, packing and shipment movements.

## Stage 3 ranking

1. Actual purchases vs approved-supplier / approved-scope audit
2. CFIA traceability-request export readiness preflight
3. Received-lot document/evidence matcher

## Advance to Stage 4

Advance those three only.

## Verification record

- Last verified: 2026-10-20
- Stage 3 status: complete
- Stage 5: out of scope
