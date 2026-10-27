---
title: Revenue Investigation — Wave 36 Stage 4 Implementation Plans
summary: Stage 4 implementation and acquisition plans for the strongest Wix App Market concepts. No Stage 5 development is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 356
permalink: /projects/notes/revenue-investigation-wave-36-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-36, wix, stage-4]
---

# Wave 36 Stage 4 — Implementation Plans

Planning only. No development, Wix App Market submission, customer testing, payments or outreach should be executed from this chat.

## Rank 1 — Wix Form / submission collection retirement preflight

### MVP
- Wix dashboard app using Wix Forms/CMS/site APIs where available.
- Inventory live forms and known submission destinations.
- Detect old Wix Form collections and custom CMS-backed forms where inspectable.
- Flag a collection selected for retirement if a live form still points to it.
- Flag live forms whose expected persistence destination is missing/disconnected.
- Include related automation references where available.
- Show recent submission activity as evidence the form is still active.
- Generate a safe-retirement checklist and exportable report.
- Never delete forms, collections or automations.

### Commercial model
- Free one-site summary or one-form check.
- Paid US$5–15/month or US$39–79/year for full audits/history/export.
- Use Wix Billing; developers currently keep 100% of app sales for the first 12 months, then 80%, after transaction fees/tax.

### Acquisition
1. Wix App Market keywords: missing form submissions, Wix Forms migration, form collection cleanup, CMS form audit.
2. Position around a concrete failure: “before deleting a form collection, verify no live form still depends on it.”
3. Demonstrate with a simple red/green dependency report.
4. Target agencies/site maintainers as a secondary organic audience, but keep App Market discovery primary.

### Main risks
- Old/new Wix Forms and custom CMS forms expose different metadata.
- API visibility may not cover every form type.

### Stage 4 verdict
**Best Wave 36 candidate for separate validation/build.**

---

## Rank 2 — Dynamic-page URL/schema change impact preflight

### MVP
- Wix dashboard app focused on CMS dynamic pages.
- Select a dynamic page/collection.
- Read current Page Link values and slug-related fields where exposed.
- Let user model a proposed slug pattern/field change without publishing it.
- Generate candidate before/after URLs for collection items.
- Flag missing required values, duplicate/colliding URLs and Page Link inconsistencies.
- Identify old URLs requiring redirect review based on domain/page-type conditions.
- Export old-to-new URL map for redirect/change control.
- Never modify live page settings or redirects.

### Commercial model
- Free small collection scan.
- Paid US$7–20/month or US$49–99/year for full collections/export/history.

### Acquisition
1. Marketplace keywords: Wix dynamic page URL, CMS 404, slug migration, dynamic page redirect.
2. Position as a **before-change simulator**, not another broken-link scanner.
3. Use exact screenshots showing current URL → proposed URL → conflict/redirect status.

### Main risks
- Site/page APIs may not expose every editor binding.
- Wix may continue improving automatic redirect handling.

### Stage 4 verdict
**Strong platform-native niche with clear pre-change value.**

---

## Rank 3 — CMS field / collection retirement dependency preflight

### MVP
- Wix dashboard app using CMS collection-management/data APIs.
- Collection/field picker.
- Inventory references to/from other collections.
- Detect participation in dynamic-page URLs/Page Link fields where exposed.
- Detect form/automation relationships where APIs expose them.
- Include indexes, permissions, item counts and recent activity.
- Optional conservative Velo/reference scan only if supported without excessive permissions.
- Classify findings as definite / possible / not inspectable.
- Generate retirement checklist.
- No schema mutation.

### Commercial model
- Free one-object scan.
- Paid US$7–20/month or US$49–99/year/site.

### Acquisition
1. App Market search around CMS cleanup, remove field, delete collection, CMS migration.
2. Agency/site-maintenance use is a natural secondary channel.
3. Position against generic web audits: this app inspects the site's internal data model.

### Main risks
- Dynamic Velo code can hide dependencies.
- Full editor dataset bindings may not be available through public APIs.

### Stage 4 verdict
**Good evergreen admin utility, but technically broader than ranks 1–2.**

## Platform economics note

Wix is one of the strongest platforms examined for low-touch app monetization. Wix handles checkout, tax, local currency, subscriptions and payouts. Developers currently receive 100% of app sales revenue for the first 12 months, then 80%, calculated after the 2.5% transaction fee and applicable tax. The App Market also exposes apps to a very large installed user base.

## Wave 36 conclusion

Top three:
1. Wix Form / submission collection retirement preflight
2. Dynamic-page URL/schema change impact preflight
3. CMS field / collection retirement dependency preflight

Wave 36 reinforces the platform-native pattern: the strongest products inspect internal configuration/data relationships that generic external tools cannot see, then monetize a narrow “before you change/delete this” decision through the host marketplace.

## Verification record
- Last verified: 2026-10-26
- Stage 4 status: complete
- Stage 5: explicitly out of scope
