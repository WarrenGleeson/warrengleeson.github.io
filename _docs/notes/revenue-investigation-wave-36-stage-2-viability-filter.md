---
title: Revenue Investigation — Wave 36 Stage 2 Viability Filter
summary: Viability filtering for Wix App Market ideas, prioritizing CMS/form/dynamic-page lifecycle safety over crowded generic site-audit categories.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 354
permalink: /projects/notes/revenue-investigation-wave-36-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-36, wix, viability]
---

# Wave 36 Stage 2 — Viability Filter

## Evidence that changed scoring

- Wix App Market has over 800 apps and generic SEO/site-health categories are already crowded, including Wix-native Site Inspection and newer third-party read-only audit apps.
- Wix App Market monetization is attractive: developers keep 100% of app sales for the first year, then 80%, with Wix handling billing, tax and local currency.
- Wix APIs expose CMS/data, business solutions, CRM, automations and site configuration, creating a platform-specific moat for structural checks that generic web crawlers cannot perform.
- Wix documentation warns that deleting an old Wix Form collection can leave the form live while submissions stop being saved, creating a concrete lifecycle failure mode.
- Wix documentation also warns that dynamic-page URL structure changes can break old URLs, page links and connections; some redirect behavior depends on connected domains and page type.
- Generic redirect/broken-link scanning is crowded, so dynamic-page candidates must focus on Wix CMS structure and Page Link consistency rather than generic SEO.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Wix Form / submission collection retirement preflight | 84 | Advance |
| 2 | Dynamic-page URL/schema change impact preflight | 82 | Advance |
| 3 | CMS field/collection retirement dependency preflight | 79 | Advance |
| 4 | Automation trigger/input-field retirement scanner | 74 | Advance cautiously |
| 5 | Wix Bookings service retirement dependency preflight | 71 | Hold |
| 6 | External collection disconnect preflight | 70 | Hold |
| 7 | Generic redirect audit | 52 | Drop; native/current competition |
| 8 | Generic broken-link/site-health scan | 47 | Drop; crowded |
| 9 | Generic forms app | 43 | Drop; native/crowded |
| 10 | Generic SEO audit | 40 | Drop; heavily crowded |

## Stage 3 shortlist
1. Wix Form / submission collection retirement preflight
2. Dynamic-page URL/schema change impact preflight
3. CMS field/collection retirement dependency preflight

## Verification record
- Last verified: 2026-10-26
- Stage 2 status: complete
- Stage 5: out of scope
