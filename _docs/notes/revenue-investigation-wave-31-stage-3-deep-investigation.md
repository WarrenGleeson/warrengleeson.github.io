---
title: Revenue Investigation — Wave 31 Stage 3 Deep Investigation
summary: Deep investigation of the strongest Figma and Canva marketplace opportunities after direct competitor checks.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 335
permalink: /projects/notes/revenue-investigation-wave-31-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-31, figma, canva, marketplace]
---

# Wave 31 Stage 3 — Deep Investigation

## 1. Figma variable retirement / rename dependency preflight

### Problem
Design-system teams increasingly use Figma variables for color, spacing, typography-adjacent values and modes. Renaming, deleting or migrating a variable can leave hard-to-find bindings in components and frames. Figma exposes variables through the Plugin API, but current research did not surface a focused paid plugin whose core job is answering: "what in this file depends on this variable before I change or remove it?"

### Product
Select a variable or collection and generate a dependency/impact report:
- nodes/properties bound to the selected variable;
- aliases that depend on it;
- modes in which it is missing or diverges;
- variables that alias through the selected variable;
- hard-coded replacement candidates after migration;
- rename/delete checklist;
- clear notice that organization-wide usage outside the current file/library cannot be guaranteed unless exposed through available APIs.

The plugin never deletes or renames variables automatically.

### Distribution
Figma Community search around variables, design tokens, design-system cleanup, migration and refactoring.

### Monetization hypothesis
Free single-variable scan; paid unlimited scans, collection-wide reports and export/history. Native Figma paid-plugin sale is preferred.

### Competition
Token-management plugins are common, but this narrower **retirement/change blast-radius** job appears less directly served than generic variable export/import or token management.

### Risk
Cross-file visibility is limited. The plugin must sell file/library-level certainty, not organization-wide guarantees.

### Verdict
**Advance.** Strongest Wave 31 candidate.

---

## 2. Figma component-property / variant retirement impact preflight

### Problem
Component libraries evolve: variants are removed, property names change, defaults shift and component sets are reorganized. Existing usage trackers show where components are used, but designers still need to know whether a proposed property/variant change will break overrides or make current instances impossible to reproduce.

### Product
Run inside a library/design file and flag:
- instances using the variant/property targeted for retirement;
- override values that would be lost after a property rename/removal;
- invalid or rare property combinations still present in instances;
- replacement target coverage;
- instances detached from the intended replacement path;
- current-file/library migration checklist.

No component or instance is modified automatically.

### Distribution
Figma Community search around component cleanup, design-system migration, variant cleanup and library refactoring.

### Monetization hypothesis
Free one component-set scan; paid unlimited component/library scans and exports.

### Competition
Component usage/adoption trackers exist, but the surviving wedge is **change-impact before variant/property retirement**, not general adoption analytics.

### Risk
Some cross-file dependencies cannot be inspected by a local plugin. Scope must be explicit.

### Verdict
**Advance.** Good paid utility for design-system maintainers.

---

## 3. Canva external-printer custom bleed / safe-zone overlay generator

### Problem
Canva's built-in bleed and margins are designed around Canva Print and are fixed. Canva explicitly advises users printing elsewhere to check the external printer's specifications, but users cannot configure custom margins/bleed automatically. This creates recurring friction for print shops, label printers, sign companies and packaging vendors that give customers their own trim/safe/bleed specifications.

### Product
Inside Canva, user enters or chooses a printer/product specification and the app generates a non-printing or removable guide overlay containing:
- trim boundary;
- custom bleed distance;
- safe zone;
- fold/gutter/cut lines where configured;
- optional quiet zones for labels/barcodes;
- printer/job-spec label.

Preset templates could cover common vendor/product specifications, with custom dimensions supported.

### Distribution
Canva Apps Marketplace search around print bleed, labels, packaging, business cards, signs and printer templates. Partner distribution through print shops is also plausible.

### Monetization hypothesis
Free basic overlay; premium preset libraries/custom saved printer profiles through Canva Premium Apps if accepted, or external paid plan if not.

### Competition
Canva provides fixed margins/bleed and native print proofing, but not customizable external-printer production guides. The current review did not surface an exact Marketplace app centered on custom print-production overlays.

### Risk
Native monetization depends on Canva approval, and a generated-guide action must fit Canva's billable-action model for Premium Apps. External payments add friction.

### Verdict
**Advance cautiously.** Strong utility gap, weaker monetization certainty than Figma.

---

## Dropped after deeper review

- Figma pseudo-localization/text expansion: multiple active plugins/products already cover it.
- Generic Figma component usage tracking: several existing plugins.
- Generic Canva print preflight: Canva Template Assistant and native proofing cover much of it.
- QR/barcode generators: Canva has native and third-party offerings.

## Stage 3 ranking

1. Figma variable retirement / rename dependency preflight
2. Figma component-property / variant retirement impact preflight
3. Canva external-printer custom bleed / safe-zone overlay generator

## Verification record
- Last verified: 2026-10-25
- Stage 3 status: complete
- Stage 5: out of scope
