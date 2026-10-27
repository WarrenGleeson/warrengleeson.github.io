---
title: Revenue Investigation — Wave 37 Stage 4 Implementation Plans
summary: Stage 4 implementation and acquisition plans for the strongest monday.com Marketplace concepts. No Stage 5 development is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 360
permalink: /projects/notes/revenue-investigation-wave-37-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-37, monday, stage-4]
---

# Wave 37 Stage 4 — Implementation Plans

Planning only. No development, Marketplace submission, customer testing, payments or outreach should be executed from this chat.

## Rank 1 — Board archive/delete dependency preflight

### MVP
- monday.com Marketplace app with read-only scopes wherever possible.
- Board picker.
- Inventory Connect Boards relationships to/from the selected board.
- Resolve mirror-column dependencies created through those relationships.
- Detect cross-board automations targeting the selected board where APIs expose them.
- Detect dashboards/widgets sourcing the board where available.
- Include portfolio/project relationships, board owners and recent activity.
- Compare archive vs delete consequences.
- Clearly list dependency classes that cannot be inspected.
- Export a retirement checklist/report.
- No archive/delete/write action.

### Commercial model
- Free: one-board scan.
- Paid feature-based plan around US$10–30/month for account-wide scans, history, exports and batch retirement projects.
- Native monday billing. New Marketplace apps must use monday monetization.
- Developer retains all app revenue until US$200,000 lifetime accumulated revenue; after that, 85% developer / 15% monday.com.

### Acquisition
1. Marketplace keywords: archive board, delete board, board cleanup, board migration, board dependency.
2. Position around one concrete question: “What breaks if I archive or delete this board?”
3. Screenshots should show exact downstream board/mirror/automation dependencies.
4. Free single-board scan provides genuine value and drives organic installs.
5. Consultants/admins handling workspace consolidation become a natural secondary channel.

### Main risks
- Automation/dashboard visibility may be partial.
- Large accounts may require careful API-rate handling.

### Stage 4 verdict
**Best Wave 37 candidate for separate validation/build.**

---

## Rank 2 — Column/status retirement dependency preflight

### MVP
- Board/column/status picker.
- Inspect accessible automation references.
- Resolve mirror, Connect Boards, dependency and formula relationships where APIs permit.
- Flag required-column behavior affecting item creation.
- Show current/historical item counts using the selected status label.
- Detect cross-board mapping dependencies where exposed.
- Allow admin to nominate a replacement column/status and produce a migration checklist.
- Classify findings as definite / possible / not inspectable.
- No schema mutation.

### Commercial model
- Free one-object scan.
- Paid US$10–30/month for board/account-wide schema reports and batch cleanup projects.

### Acquisition
1. Marketplace keywords: delete column, status cleanup, board schema migration, automation breakage.
2. Position against native deletion: monday lets you delete the object; this app tells you what depends on it first.
3. Offer a low-friction single-board workflow for admins and consultants.

### Main risks
- Some app-owned/custom dependencies may remain invisible.
- Formula/reference parsing may be incomplete depending on API exposure.

### Stage 4 verdict
**Strong second candidate with broad admin usefulness.**

---

## Rank 3 — Automation ownership / target continuity audit

### MVP
- Account/board-level automation inventory where APIs permit.
- Flag owner departure/inactivity or sole ownership.
- Flag automation targets that no longer exist or are selected for retirement.
- Flag cross-board recipes tied to boards marked for archive/delete.
- Allow admins to mark critical automations and require backup-owner coverage.
- Generate continuity/handoff report.
- No owner transfer or automation modification.

### Commercial model
- Free account summary.
- Paid US$15–40/month based on automation count/reporting depth.

### Acquisition
1. Marketplace keywords: broken monday automation, automation owner, employee departure, automation continuity.
2. Content around monday’s documented behavior when automation targets are deleted.
3. Secondary channel: monday consultants and larger workspace admins.

### Main risks
- Public API coverage of automations may be the deciding feasibility constraint.
- Native automation management may improve over time.

### Stage 4 verdict
**Good operational niche, but feasibility risk is higher than ranks 1–2.**

## Platform economics note

monday.com is one of the most attractive ecosystems in this platform-native series. All new Marketplace apps use monday-native billing; monday handles subscriptions, VAT and currency conversion. Revenue share does not activate until the app reaches US$200,000 in lifetime accumulated revenue. After that threshold, developers receive 85% and monday.com 15%. Feature-based and seat-based plans, monthly/yearly billing, free plans and trials are all supported.

## Wave 37 conclusion

Top three:
1. Board archive/delete dependency preflight
2. Column/status retirement dependency preflight
3. Automation ownership/target continuity audit

The key pattern remains consistent: the best marketplace products are narrow, read-only tools that answer a high-consequence admin question immediately and can be understood from a single Marketplace listing screenshot.

## Verification record
- Last verified: 2026-10-26
- Stage 4 status: complete
- Stage 5: explicitly out of scope
