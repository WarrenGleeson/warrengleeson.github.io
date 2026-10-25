---
title: Revenue Investigation — Wave 26 Stage 3 Deep Investigation
summary: Deep investigation of the strongest small manufacturing/fabrication ideas after direct competition checks.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 315
permalink: /projects/notes/revenue-investigation-wave-26-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-26, deep-investigation, manufacturing]
---

# Wave 26 Stage 3 — Deep Investigation

## 1. Engineering-change open-job impact audit

### Problem
A drawing/spec/BOM revision can be released while open jobs, printed travelers, supplier orders, inspection plans or material allocations still reference the prior state. Current PLM/ERP/MES products can govern this when everything is integrated, but smaller shops frequently have the relevant evidence split across folders, spreadsheets, ERP exports and paper travelers.

### Product
Upload/export the newly released change plus open-job/traveler/purchasing/inspection data. The audit identifies candidate affected records and flags:
- open job/traveler on superseded drawing/BOM revision;
- purchase/outsource PO still referencing old specification/revision;
- inspection plan/report tied to previous revision;
- material or supplier deviation approval whose effectivity does not cover the changed job;
- production start before/after change-effectivity ambiguity;
- superseded document still present in the release package.

The tool does not decide whether work must stop; it builds a source-linked impact-review queue.

### Distribution
Search around engineering change impact, wrong-revision manufacturing, ISO 9001 change control, job-shop quality consultants and ERP/QMS implementers.

### Monetization hypothesis
Free small change audit; CA$15–30 per change/release audit; CA$20–50/month recurring small-shop plan.

### Competition
PLM/ERP/MES systems and newer manufacturing platforms manage controlled change when adopted end-to-end. The surviving wedge is an independent **read-only impact audit across disconnected exports and documents** for shops that are not ready to migrate systems.

### Risk
Effectivity can be complex and shop-specific. The audit must present candidates/uncertainty, not automatically disposition WIP.

### Verdict
**Advance.** Strongest Wave 26 concept.

---

## 2. Customer-requirement to supplier/outsource PO flowdown audit

### Problem
A job shop remains responsible for outsourced processing/material even when work leaves the building. Customer drawings/specifications may require a specific revision, finish/coating process, approved source, material grade, traceability, certificate, inspection evidence or packaging rule. Those requirements can disappear when purchasing creates a short supplier PO from memory or an old template.

### Product
Compare the released customer/job requirement package against the supplier/outsource PO and attached instructions. Flag:
- required drawing/spec revision missing or outdated;
- material grade/process/finish requirement absent;
- required certificate/inspection/traceability evidence not requested;
- approved-source or no-substitution requirement not flowed down;
- quantity/part/revision mismatch;
- customer-specific packaging/marking/document requirement omitted;
- supplier acknowledgment that conflicts with the issued requirement.

The tool checks factual flowdown only; it does not approve suppliers or interpret standards.

### Distribution
ISO 9001 supplier-control search, machine/fab shop quality consultants, purchasing consultants and a free PO-flowdown checklist.

### Monetization hypothesis
Free one PO/package check; CA$5–15 per outsource PO preflight; CA$15–35/month recurring shop plan.

### Competition
ERP/QMS platforms can encode purchasing controls, but current research did not surface a strong lightweight standalone product specifically auditing **released customer requirements against the actual external-provider PO/instructions** for small shops.

### Risk
Customer requirement documents vary widely. Extraction must remain conservative and source-linked.

### Verdict
**Advance.** Strong deterministic admin/quality wedge.

---

## 3. Shipment certificate/document-pack readiness preflight

### Problem
Many customers require shipment evidence beyond a packing slip: CoC, material certs, process certs, inspection reports, lot/heat traceability, revision and quantity references. Small shops often assemble this pack from shared folders/email just before shipment, creating rejection/delay risk when a cert covers the wrong lot, revision or quantity—or is simply missing.

### Product
Upload shipment/order data plus the job's configured customer document requirements and evidence folder. Flag:
- required document type missing;
- CoC/inspection cert references wrong part/revision/PO/quantity;
- material/process cert lot or heat does not match job/shipment traceability;
- evidence is present but associated with another batch/job;
- required deviation/waiver not included;
- packing slip/CoC/inspection quantity mismatch;
- customer-specific final-data requirement incomplete.

The tool does not certify conformity; it checks pack completeness/internal consistency before release.

### Distribution
Search around certificate-of-conformance shipment rejection, quality-document packs, machine-shop shipping QA and ISO/AS quality consultants.

### Monetization hypothesis
Free one small shipment pack; CA$5–15 per shipment preflight; CA$15–35/month recurring shop plan.

### Competition
QMS/ERP and certificate-management products cover pieces of this flow; current products also automate material-cert matching. The narrower surviving wedge is **whole shipment-pack completeness and cross-document consistency** for small shops using mixed systems.

### Risk
Document extraction variability and regulated-sector complexity. Initial target should be general industrial/job-shop work, not aerospace/medical/defense compliance claims.

### Verdict
**Advance cautiously.** Clear operational pain with moderate extraction complexity.

---

## Dropped after deeper review

### Accepted quote vs customer PO comparison
A current manufacturing product already performs whole-package quote-to-PO comparison, including technical revisions and commercial commitments.

### Material-certificate matching
Current tools already read mill certificates, match them to PO lines and cross-check heat numbers against goods receipt.

### Drawing-to-inspection-plan extraction
Direct tools now extract drawing characteristics, balloon drawings and generate inspection plans.

### Generic BOM/revision control and digital travelers
Well served by PLM, BOM and job-shop systems, including products aimed at small manufacturers.

## Stage 3 ranking

1. Engineering-change open-job impact audit
2. Customer-requirement to supplier/outsource PO flowdown audit
3. Shipment certificate/document-pack readiness preflight

## Advance to Stage 4
Advance those three only.

## Verification record
- Last verified: 2026-10-25
- Stage 3 status: complete
- Stage 5: out of scope
