---
title: Revenue Investigation — Wave 37 Stage 3 Deep Investigation
summary: Deep investigation of the strongest monday.com Marketplace opportunities after direct competitor checks.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 359
permalink: /projects/notes/revenue-investigation-wave-37-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-37, monday, marketplace]
---

# Wave 37 Stage 3 — Deep Investigation

## 1. Board archive/delete dependency preflight

### Problem
monday.com boards can be connected through Connect Boards columns, mirror columns, dashboards, cross-board automations and portfolio/reporting structures. monday documents that deleting a board removes Connect Boards relationships, while archiving a board temporarily severs mirrored/dashboard linkages. Admins therefore need a practical blast-radius report before retirement.

### Product
Select a board and report accessible dependencies:
- Connect Boards columns pointing to/from the board;
- Mirror columns relying on those connections;
- cross-board automations targeting the board;
- dashboards/widgets sourcing the board where exposed;
- portfolio/project relationships;
- recent item/activity volume;
- owner continuity and board type;
- archive vs delete consequences;
- unsupported dependency classes explicitly identified.

No board is archived or deleted automatically.

### Distribution
monday Marketplace search around archive board, delete board, board cleanup, workspace migration and board consolidation.

### Monetization hypothesis
Free one-board scan; paid account-wide scans/history/export using feature-based pricing around US$10–30/month for small accounts, scaling upward for larger estates.

### Competition
Broad governance and cleanup tools exist, but exact Marketplace searches did not surface a focused app whose main job is “what breaks if I archive/delete this board?”

### Verdict
**Advance.** Strongest Wave 37 concept.

---

## 2. Column/status retirement dependency preflight

### Problem
Columns and status labels become embedded in automations, formulas, mirrors, dependencies, dashboards and operating procedures. monday explicitly documents that deleting a column targeted by an automation can deactivate that automation; required-column changes can also break item-creation automations/integrations.

### Product
Select a column or status label and report:
- automations that reference the column/label where APIs expose them;
- formula/mirror/dependency relationships;
- required-column behavior and item-creation impact;
- dashboard/view dependencies where exposed;
- cross-board mappings involving the column;
- historical/current item counts using the status label;
- proposed replacement mapping and retirement checklist;
- definite vs possible vs uninspectable references.

No column/status is changed automatically.

### Distribution
Marketplace search around delete column, status cleanup, board refactor, schema migration and automation breakage.

### Monetization hypothesis
Free one-object scan; paid board/account-wide schema dependency reporting around US$10–30/month.

### Competition
Generic automation and board-management tools are common, but current review did not identify a narrow retirement-blast-radius app for columns/statuses.

### Risk
Not every app-owned or formula-level dependency may be inspectable through public APIs.

### Verdict
**Advance.** Strong deterministic admin niche.

---

## 3. Automation ownership / target continuity audit

### Problem
monday automations have owners and target specific boards, columns, groups or workspaces. monday documents that deleted targets can deactivate automations and supports manual ownership transfer. That creates an evergreen continuity problem when owners leave, boards are reorganized or critical automations depend on fragile targets.

### Product
Inventory accessible automations and flag:
- automation owner inactive/departed or sole owner;
- target board/column/group/workspace missing or scheduled for retirement;
- disabled automation still marked business-critical;
- cross-board automation pointing to a board slated for archive/delete;
- ownership mismatch between board owner and automation owner;
- no backup owner for critical recipes;
- continuity checklist and handoff evidence pack.

No automation ownership or configuration is changed automatically.

### Distribution
Marketplace search around automation ownership, broken automation, employee departure and monday admin continuity.

### Monetization hypothesis
Free account summary; paid recurring audit around US$15–40/month depending on automation count.

### Competition
monday has native automation management and ownership transfer, but current research did not surface a lightweight Marketplace app focused on **continuity risk across automation owners and targets**.

### Risk
Automation API visibility may constrain full coverage.

### Verdict
**Advance cautiously.** Strong problem, but API visibility is the gating factor.

## Stage 3 ranking
1. Board archive/delete dependency preflight
2. Column/status retirement dependency preflight
3. Automation ownership/target continuity audit

## Verification record
- Last verified: 2026-10-26
- Stage 3 status: complete
- Stage 5: out of scope
