---
title: Revenue Investigation — Wave 18 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest non-clinical healthcare administration concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-20
updated: 2026-10-20
last_verified: 2026-10-20
owner: High Director
order: 284
permalink: /projects/notes/revenue-investigation-wave-18-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-18, stage-4, healthcare-admin]
---

# Wave 18 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — Allied-health insurer / claim document readiness workspace

### Core promise
Help physiotherapy/chiropractic/allied-health clinics see which payer-admin documents, claim references and report deadlines are still missing before billing or continuation requests become delayed.

### MVP plan
- Start with a narrow BC payer set: ICBC, WorkSafeBC and private-benefit administrative checklists.
- One record per administrative claim/case, using the minimum necessary patient identifier.
- Track claim/reference number, payer, provider, report/form requirements, due dates and submission channel.
- Missing-document queue and deadline reminders.
- Extension-request status where applicable.
- Payment/follow-up reference field.
- Export a payer-readiness checklist.
- Avoid treatment recommendations, coverage decisions or clinical content interpretation.

### Likely stack
- Browser-first lightweight workspace.
- Versioned payer-rule/checklist definitions.
- Local/minimal-data architecture preferred.
- Optional CSV import from existing PMS exports rather than replacing the PMS.

### Pricing hypothesis
- Free: small caseload or one payer checklist.
- CA$10–25/month: small clinic/admin team.
- One-off cleanup/readiness report option.

### Semi-automated acquisition pipeline
1. Monitor official ICBC and WorkSafeBC provider pages/forms for administrative changes.
2. Publish search pages around current report/form/submission requirements.
3. Free payer checklist becomes the primary inbound funnel.
4. Use synthetic case examples only; do not collect real patient records for demonstrations.
5. Track opt-in missing-document categories to prioritize payer workflows.
6. Partner channel: clinic billing consultants, bookkeepers and practice-management implementers.
7. Any future direct outreach remains low-volume/manual-approved and privacy-conscious.
8. Route multi-provider/clinic-admin interest to the owner.

### Main risks
- Sensitive patient information requires strong privacy/security design.
- PMS vendors could add equivalent payer checklists.
- Payer processes change and require ongoing maintenance.

### Stage 4 verdict
**Highest-priority Wave 18 candidate.**

---

## Rank 2 — MSP / ICBC billing-evidence QA preflight

### Core promise
Give BC physician/specialist offices a narrow administrative QA pass before claim submission or audit, checking for missing evidence references and deterministic claim metadata issues without recommending fee codes.

### MVP plan
- Import claim CSV/export or structured batch.
- Check configured administrative rules only: provider/payee IDs, MVA flag/claim reference, referral reference where required by clinic workflow, duplicate claim candidates and deadline warnings.
- Allow clinic to define required supporting-document references per internal policy.
- Produce a review queue and evidence checklist.
- No code recommendation, no diagnosis interpretation, no clinical eligibility determination.

### Likely stack
- Local/browser CSV checker.
- Versioned BC administrative rule pack.
- Optional scheduled batch check later.

### Pricing hypothesis
- Free: small batch.
- CA$15–30: monthly audit.
- CA$15–40/month: recurring small-specialist-office plan.

### Semi-automated acquisition pipeline
1. Monitor official MSP payment schedule/preamble and ICBC administrative billing guidance.
2. Publish narrow search content around administrative claim QA and evidence retention.
3. Free small-batch checker drives inbound acquisition.
4. Use synthetic claims only for demonstrations.
5. Partner with independent billing agents/consultants rather than compete with them.
6. Track opt-in recurring error categories to refine deterministic checks.
7. Future outreach should target billing consultants/office managers manually, not clinicians at scale.
8. Route recurring batch users to the owner.

### Main risks
- High-consequence billing rules.
- Mature billing software market.
- Easy for incumbents to copy narrow checks.

### Stage 4 verdict
**Useful independent QA layer, but weaker moat than rank 1.**

---

## Rank 3 — Rejected-claim reason normalizer + resubmission checklist

### Core promise
Turn inconsistent payer rejection messages into one standardized clinic-admin queue with clear non-clinical follow-up steps.

### MVP plan
- Paste/import rejection text or CSV.
- Map to normalized administrative categories: missing identifier, duplicate, expired/missing authorization, missing report, wrong submission path, payer mismatch, deadline issue, unknown/manual review.
- Generate deterministic checklist based on configured payer rules.
- Track resolved/resubmitted/closed status.
- Report recurring rejection categories by payer.
- No automated resubmission or clinical-code selection.

### Likely stack
- Lightweight web/desktop utility.
- Rules-first normalization with optional language-model assistance only for classification where uncertainty is surfaced.
- CSV export/import.

### Pricing hypothesis
- Free: low-volume use.
- CA$10–20/month: multi-payer clinic queue.

### Semi-automated acquisition pipeline
1. Publish payer-specific administrative rejection guides.
2. Free rejection-normalizer sample is the acquisition funnel.
3. Collect opt-in anonymized category frequencies rather than raw patient data.
4. Partner with billing consultants and small PMS vendors.
5. Demonstrate using synthetic rejection messages.
6. Future direct outreach remains controlled/manual-approved.
7. Route multi-payer recurring users to the owner.

### Main risks
- Low standalone pricing power.
- Existing billing platforms may already classify many rejection reasons.
- Payer wording/rules change over time.

### Stage 4 verdict
**Better as a small utility or feature than a large standalone business.**

## Wave 18 conclusion

Top three:

1. Allied-health insurer / claim document readiness workspace
2. MSP / ICBC billing-evidence QA preflight
3. Rejected-claim reason normalizer + resubmission checklist

Wave 18 confirms that the better healthcare opportunities are in non-clinical administrative fragmentation between clinics and payers, not generic booking/intake/referral platforms or medical decision support.

## Verification record

- Last verified: 2026-10-20
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
