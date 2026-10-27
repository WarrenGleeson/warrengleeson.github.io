---
title: Revenue Investigation — Wave 36 Stage 3 Deep Investigation
summary: Deep investigation of the strongest Wix App Market opportunities after direct competitor checks.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 355
permalink: /projects/notes/revenue-investigation-wave-36-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-36, wix, app-market]
---

# Wave 36 Stage 3 — Deep Investigation

## 1. Wix Form / submission collection retirement preflight

### Problem
Wix documents that deleting an old Wix Form collection can disconnect the form from its storage while the form can remain live and continue accepting submissions that are no longer saved. Sites can also mix old Wix Forms, new Wix Forms and custom CMS-backed forms, making cleanup deceptively risky.

### Product
A read-only Wix app that inventories site forms and submission destinations, then flags:
- live form whose expected submission collection is missing or disconnected;
- collection proposed for deletion that still has a live form dependency;
- old-vs-new Wix Forms collection ambiguity;
- form-to-CMS destination mismatch for custom forms;
- form-related automations whose trigger/source would be affected;
- recent submissions proving the form is still active;
- retirement checklist and exportable evidence pack.

No collection, form or automation is deleted automatically.

### Distribution
Wix App Market search around form submissions missing, Wix form migration, form cleanup, CMS collection cleanup and site handoff.

### Monetization hypothesis
Free one-form/site summary; US$5–15/month or US$39–79/year for full site audit/history. Wix native billing is preferred.

### Competition
Wix Forms itself manages form creation/submissions, while generic site-audit apps focus on SEO/links. Current review did not surface a focused App Market product centered on **form-storage dependency and safe retirement**.

### Risk
Wix Forms generations and custom CMS forms have different APIs/structures. The first version should explicitly support only dependency classes that can be inspected reliably.

### Verdict
**Advance.** Strongest Wave 36 concept.

---

## 2. Dynamic-page URL/schema change impact preflight

### Problem
Wix dynamic pages generate URLs from CMS fields and slug structures. Wix documentation warns that changing URL structures can invalidate previous URLs, require redirect handling, and create Page Link mismatches or 404/500 errors if collection values/connections are inconsistent. Generic broken-link scanners only see the published aftermath; the merchant needs a pre-change report.

### Product
Select a dynamic page and model a proposed slug/schema change. Report:
- current generated Page Link values;
- candidate new URLs using the proposed structure;
- collisions/duplicate URL candidates;
- items missing values required by the proposed slug;
- old URLs that need redirect coverage under the site's domain/page type behavior;
- dataset/Page Link mismatches already present;
- collection fields being retired that participate in the URL;
- before/after URL map export.

No URL structure or redirect is changed automatically.

### Distribution
Wix App Market search around dynamic pages, CMS URL changes, 404s, migration and site restructuring.

### Monetization hypothesis
Free limited scan; US$7–20/month or US$49–99/year for full collection/page reports and exports.

### Competition
Wix has native redirect management and troubleshooting, and generic SEO apps catch broken URLs after publication. Current research did not surface a focused **before/after dynamic URL simulation** using CMS Page Link structures.

### Risk
Editor/page configuration APIs may not expose every relationship needed for full certainty. Product scope may need to start with URL/data consistency rather than visual dataset bindings.

### Verdict
**Advance.** Strong platform-native change-preflight niche.

---

## 3. CMS field / collection retirement dependency preflight

### Problem
Wix CMS fields can drive dynamic pages, reference relationships, custom forms, code, automations and app-connected experiences. Removing or changing a field/collection may therefore break site behavior far beyond the collection table itself.

### Product
Select a custom CMS field or collection and report accessible dependencies:
- reference fields from/to other collections;
- dynamic-page URL/Page Link involvement;
- automations triggered by or acting on the collection/field where exposed;
- form submission/storage relationships;
- indexes and permission configuration;
- app/custom code references where detectable through supported APIs or configured scans;
- item counts and recent activity;
- definite vs possible vs uninspectable dependencies;
- retirement/migration checklist.

No field or collection is modified automatically.

### Distribution
App Market search around Wix CMS cleanup, remove field, delete collection, schema migration and site maintenance.

### Monetization hypothesis
US$7–20/month or US$49–99/year/site, with free one-object scan.

### Competition
Generic site-health/SEO tools cannot inspect CMS schema relationships. Current exact App Market review did not surface a dedicated CMS retirement blast-radius tool.

### Risk
Custom Velo code can reference schema dynamically, limiting complete dependency detection. Coverage must be explicitly confidence-scored.

### Verdict
**Advance.** Good evergreen Wix-admin utility.

## Stage 3 ranking
1. Wix Form / submission collection retirement preflight
2. Dynamic-page URL/schema change impact preflight
3. CMS field / collection retirement dependency preflight

## Verification record
- Last verified: 2026-10-26
- Stage 3 status: complete
- Stage 5: out of scope
