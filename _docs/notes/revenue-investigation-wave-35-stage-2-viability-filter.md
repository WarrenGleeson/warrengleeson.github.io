---
title: Revenue Investigation — Wave 35 Stage 2 Viability Filter
summary: Viability filtering for Microsoft Teams / Microsoft 365 AppSource ideas, prioritizing workflow continuity and lifecycle preflights over broad governance categories.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 350
permalink: /projects/notes/revenue-investigation-wave-35-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-35, microsoft-teams, viability]
---

# Wave 35 Stage 2 — Viability Filter

## Evidence that changed scoring

- Microsoft Marketplace supports transactable SaaS offers linked to Teams apps, with Microsoft handling transactions and currently retaining a 3% Marketplace service fee.
- Teams Workflows/webhook replacements are tied to specific owners, and Microsoft explicitly warns that workflows can become orphaned if owners leave unless co-owners are assigned.
- The Office 365 Connector retirement itself is now past its main migration deadline, so a migration-only app is too late; continuity and orphan-detection remain evergreen.
- Private and shared channels have distinct lifecycle/storage/app behavior. Private/shared channels can have their own SharePoint sites and app availability differs by host-team/channel context.
- Broad Microsoft 365 governance, lifecycle management and compliance are mature categories, so narrow change-preflight utilities are preferable.
- Exact AppSource searches did not surface a focused product for Teams Workflows orphan-owner continuity or channel retirement blast-radius analysis.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Teams Workflows orphan-owner / continuity audit | 83 | Advance |
| 2 | Team/channel retirement dependency preflight | 79 | Advance |
| 3 | Shared/private-channel app compatibility audit | 76 | Advance |
| 4 | Teams app uninstall dependency preflight | 72 | Advance cautiously |
| 5 | Team owner departure blast-radius report | 70 | Merge into #1/#2 |
| 6 | Private-channel SharePoint site retirement preflight | 69 | Merge into #2 |
| 7 | Teams webhook replacement residual audit | 58 | Hold; primary migration window passed |
| 8 | Generic team lifecycle governance | 50 | Drop; broad competition |
| 9 | Generic M365 compliance/governance | 45 | Drop; heavily crowded |
| 10 | Generic meeting/AI assistant | 40 | Drop; extremely crowded |

## Stage 3 shortlist
1. Teams Workflows orphan-owner / continuity audit
2. Team/channel retirement dependency preflight
3. Shared/private-channel app compatibility audit

## Verification record
- Last verified: 2026-10-26
- Stage 2 status: complete
- Stage 5: out of scope
