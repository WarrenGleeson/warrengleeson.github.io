---
title: Revenue Investigation — Wave 31 Stage 4 Implementation Plans
summary: Stage 4 implementation and acquisition plans for the strongest Figma and Canva marketplace concepts. No Stage 5 development is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 336
permalink: /projects/notes/revenue-investigation-wave-31-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-31, figma, canva, stage-4]
---

# Wave 31 Stage 4 — Implementation Plans

Planning only. No development, marketplace submission, customer testing, payments or outreach should be executed from this chat.

## Rank 1 — Figma variable retirement / rename dependency preflight

### MVP
- Classic Figma plugin.
- Variable/collection picker.
- Traverse current file for bindings to selected variable.
- Identify aliases and reverse aliases.
- Show mode coverage and missing-mode cases.
- Flag hard-coded values near the selected variable value as migration candidates.
- Build rename/delete impact report and export.
- Clearly state current-file/library scope.
- No write/delete action.

### Commercial model
- Free one-variable scan.
- Paid plugin unlocks collection-wide scans, batch reports and export/history.
- Prefer native Figma Community payments.

### Acquisition
1. Community keywords: Figma variables, tokens, rename variable, delete variable, design system cleanup.
2. Screenshots centered on one destructive question: “Can I safely remove this variable?”
3. Publish narrowly focused documentation around design-token retirement/refactoring.
4. No external sales motion required beyond Community listing/content.

### Main risk
Organization-wide/cross-file certainty is impossible without broader data access. Scope must remain explicit.

### Stage 4 verdict
**Best Wave 31 product for a separate validation/build chat.**

---

## Rank 2 — Figma component-property / variant retirement impact preflight

### MVP
- Classic Figma plugin.
- Component-set/property/variant picker.
- Scan current file for instances using selected property/variant.
- Enumerate override values that may be lost.
- Flag rare/invalid property combinations.
- Allow maintainer to nominate intended replacement and show uncovered instances.
- Export migration checklist.
- No component mutation.

### Commercial model
- Free one component-set scan.
- Paid unlimited scans and report export through Figma Community payments.

### Acquisition
1. Community keywords around component cleanup, variant cleanup, design-system migration and component refactor.
2. Position against usage trackers: not “where is this used?” but “what breaks if I remove/change this?”
3. Target design-system maintainers rather than general designers.

### Main risk
Cross-file visibility remains incomplete.

### Stage 4 verdict
**Strong second Figma micro-plugin; clear paid-user persona.**

---

## Rank 3 — Canva external-printer custom bleed / safe-zone overlay generator

### MVP
- Canva Apps SDK app.
- User enters finished size and external-printer bleed/safe-zone dimensions, or selects a saved preset.
- Generate visual guide layers for trim, bleed, safe area and optional fold/gutter/cut/quiet zones.
- Allow presets for labels, cards, packaging, signs and common printer templates.
- Include a removable job-spec label.
- Keep the generated overlay easy to hide/delete before final export if Canva cannot mark it non-printing.

### Commercial model
- Free basic custom overlay.
- Premium saved profiles/preset packs if accepted into Canva Premium Apps Program.
- External paid plan is fallback, but scores lower because it adds billing friction.

### Acquisition
1. Canva Apps Marketplace keywords: bleed, safe zone, print template, packaging, label, printer.
2. Preset landing pages for common print products.
3. Printer/print-shop referral potential without requiring cold sales.
4. Emphasize that Canva's native bleed is fixed and external printer specs can differ.

### Main risk
Premium Apps monetization is approval-based and billable-action fit must be confirmed before build. Canva may later add configurable guides natively.

### Stage 4 verdict
**Good product gap; monetization uncertainty keeps it below the Figma concepts.**

## Platform conclusion

Figma is the stronger platform for this research objective because paid classic plugins can be sold directly through Community and Canada is supported for creator payouts. Canva offers strong distribution but native monetization is conditional on acceptance to the Premium Apps Program; external payment links remain possible but add friction.

## Wave 31 conclusion

Top three:
1. Figma variable retirement / rename dependency preflight
2. Figma component-property / variant retirement impact preflight
3. Canva external-printer custom bleed / safe-zone overlay generator

## Verification record
- Last verified: 2026-10-25
- Stage 4 status: complete
- Stage 5: explicitly out of scope
