---
title: Revenue Investigation — Wave 31 Stage 2 Viability Filter
summary: Viability filtering for Figma plugins and Canva apps, prioritizing directly monetizable design-system change tools and narrow production helpers.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 334
permalink: /projects/notes/revenue-investigation-wave-31-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-31, figma, canva, viability]
---

# Wave 31 Stage 2 — Viability Filter

## Evidence that changed scoring

- Figma supports native paid classic plugins in Community, making small single-purpose utilities directly monetizable.
- Broad component-usage tracking is already served by multiple plugins.
- Pseudo-localization, text-expansion and RTL stress testing are also served by current plugins/products.
- Figma's Plugin API supports variables and component metadata, making local-file change-impact utilities feasible even where organization-wide visibility is limited.
- Figma itself recommends testing component/library changes before publishing because a single shared-library change can affect many files.
- Canva's built-in print margins/bleed are fixed; Canva explicitly says custom margins cannot currently be automated and outside printers may require different bleed specifications. This creates a narrow app niche for generating custom production overlays.
- Canva native Premium Apps monetization is approval-based, so Canva candidates score lower than comparable Figma paid-plugin ideas unless they also work with external payment links.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Figma variable retirement / rename dependency preflight | 82 | Advance |
| 2 | Figma component-property / variant retirement impact preflight | 80 | Advance |
| 3 | Canva external-printer custom bleed/safe-zone overlay generator | 77 | Advance |
| 4 | Figma library publish-change impact checker | 74 | Advance cautiously |
| 5 | Figma ready-for-dev contradiction checker | 71 | Hold |
| 6 | Canva packaging dieline safe-zone overlay importer | 70 | Merge into #3 |
| 7 | Figma theme-mode coverage audit | 68 | Hold |
| 8 | Figma component usage tracker | 55 | Drop; direct current competitors |
| 9 | Figma pseudo-localization/overflow checker | 48 | Drop; crowded/direct competitors |
| 10 | Canva generic print preflight | 47 | Drop; native Template Assistant/print proofing |
| 11 | Canva QR tools | 40 | Drop; native/current apps |

## Stage 3 shortlist

1. Figma variable retirement / rename dependency preflight
2. Figma component-property / variant retirement impact preflight
3. Canva external-printer custom bleed/safe-zone overlay generator

## Verification record
- Last verified: 2026-10-25
- Stage 2 status: complete
- Stage 5: out of scope
