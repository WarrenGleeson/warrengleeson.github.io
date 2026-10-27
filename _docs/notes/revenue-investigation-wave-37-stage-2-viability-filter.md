---
title: Revenue Investigation — Wave 37 Stage 2 Viability Filter
summary: Viability filtering for monday.com Marketplace ideas, prioritizing board/column/automation lifecycle preflights over generic productivity apps.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 358
permalink: /projects/notes/revenue-investigation-wave-37-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-37, monday, viability]
---

# Wave 37 Stage 2 — Viability Filter

## Evidence that changed scoring

- New monday Marketplace apps must use monday-native monetization. monday handles subscriptions, billing, VAT and currency conversion.
- Revenue share is unusually favorable at low scale: the app keeps all revenue until US$200,000 lifetime accumulated revenue, after which the developer receives 85% and monday.com 15%.
- monday documents that deleting a board removes Connect Boards connections; archiving boards temporarily severs mirrored/dashboard linkages.
- monday documents that deleting a target board, column, group, workspace or subitem dependency can deactivate automations.
- Required-column changes can also break item-creation automations/integrations.
- Broad automation builders, dashboards, CRM/time tracking and generic workflow tools are mature, so narrow lifecycle-risk products score higher.
- Exact Marketplace searches did not surface dedicated apps whose core purpose is board/column retirement blast-radius analysis.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Board archive/delete dependency preflight | 85 | Advance |
| 2 | Column/status retirement dependency preflight | 82 | Advance |
| 3 | Automation ownership/target continuity audit | 79 | Advance |
| 4 | Required-column rollout impact simulator | 76 | Advance cautiously |
| 5 | Connect Boards column retirement preflight | 74 | Merge into #1/#2 |
| 6 | Dashboard source retirement preflight | 72 | Merge into #1 |
| 7 | Marketplace app uninstall dependency preflight | 67 | Hold; visibility risk |
| 8 | Generic automation map | 53 | Drop; crowded |
| 9 | Generic board health | 48 | Drop; broad/native overlap |
| 10 | Generic project dashboard | 42 | Drop; crowded |

## Stage 3 shortlist
1. Board archive/delete dependency preflight
2. Column/status retirement dependency preflight
3. Automation ownership/target continuity audit

## Verification record
- Last verified: 2026-10-26
- Stage 2 status: complete
- Stage 5: out of scope
