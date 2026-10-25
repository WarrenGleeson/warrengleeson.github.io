---
title: Revenue Investigation — Wave 24 Stage 3 Deep Investigation
summary: Deep investigation of the strongest hospitality and restaurant ideas after direct competition checks.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 307
permalink: /projects/notes/revenue-investigation-wave-24-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-24, deep-investigation, hospitality, restaurants]
---

# Wave 24 Stage 3 — Deep Investigation

## 1. Hotel front-desk discretionary revenue-leak audit

### Problem
Independent hotels routinely make front-desk decisions that affect revenue: early check-in, late checkout, room upgrade, complimentary room, no-show/cancellation charge and fee waiver. Some PMSs enforce these policies tightly, but others still depend on manual posting or staff judgement. The leakage appears when a charge was due under the hotel's own policy but never posted, or when a waiver/upgrade/comp lacks the approval evidence the hotel expects.

### Product
Import PMS reservation/folio/activity exports plus the hotel's own policy/approval matrix. Flag:
- early check-in or late checkout with no corresponding charge or documented waiver;
- paid upgrade/room-type change with no expected differential;
- complimentary room or rate override without configured approval evidence;
- no-show/cancellation event with no charge/waiver disposition;
- checkout-day ancillary sale not reflected on the folio where source data shows it;
- repeated staff/user exception patterns.

The tool audits existing policy; it does not set pricing or decide whether a guest should be charged.

### Distribution
Hotel owner/controller search, independent-hotel accountants, PMS consultants and a free month-end sample audit.

### Monetization hypothesis
CA$20–40 monthly audit; CA$25–60/month recurring property plan; multi-property accountant/consultant tier later.

### Competition
Some PMSs now automate early/late charges and approval trails, while hotel-finance tools cover broader revenue reconciliation. The surviving wedge is an independent, cross-PMS **discretionary front-desk exception audit** for smaller properties using mixed or legacy systems.

### Risk
PMS export formats vary and policy details are property-specific. The tool must distinguish expected exceptions from definite errors.

### Verdict
**Advance.** Strongest Wave 24 concept.

---

## 2. Restaurant menu-channel drift audit

### Problem
Independent restaurants commonly maintain menu data in a POS, website, direct-ordering page and multiple delivery marketplaces. Full menu-sync middleware exists, but smaller operators may not want another integration platform. Price, modifier, availability and description changes can drift between copies and create refunds, margin loss or guest complaints.

### Product
Use one approved menu/source file as the reference and compare supplied/public menu pages or exports for:
- item missing/extra;
- unexpected price difference outside configured channel markup policy;
- modifier/size mismatch;
- stale sold-out/availability status where data is supplied;
- description/name mismatch;
- outdated promotional/catering-menu copy;
- menu revision not published to all declared surfaces.

Output is an exceptions report; the product does not push updates.

### Distribution
Independent restaurant search, restaurant web agencies/consultants and a free one-menu audit.

### Monetization hypothesis
Free limited audit; CA$10–20 per full audit; CA$10–25/month scheduled multi-channel monitoring.

### Competition
Menu-sync middleware and restaurant marketing audits are current and growing. The surviving wedge is a cheap **read-only drift detector** for restaurants that deliberately do not want to centralize/push menus through another platform.

### Risk
Delivery platforms can restrict automated access, channel-specific price differences may be intentional, and middleware vendors can add equivalent monitoring.

### Verdict
**Advance cautiously.** Clear pain, but competitive.

---

## 3. Hotel maintenance-complete / room-still-blocked audit

### Problem
An out-of-order room removes sellable inventory and can materially affect revenue. PMS dashboards can show blocked rooms and maintenance systems can show completed jobs, but the cross-system failure is narrower: maintenance is complete, yet the room remains blocked/out of order longer than necessary because the status handoff was missed.

### Product
Import PMS room-block/status history and maintenance/work-order export. Match room and work event, then flag:
- maintenance job completed while room remained out of order beyond configured tolerance;
- room returned to inventory before linked work was completed;
- blocked room with no maintenance/work-order reference;
- repeated rooms with long post-completion unblock delays;
- estimated lost sellable room-nights using actual occupancy/rate inputs supplied by the hotel.

The tool audits status handoff only; it does not direct engineering or decide whether a room is safe to sell.

### Distribution
Independent hotel owners/controllers, hotel accountants, PMS/maintenance consultants and a free blocked-room audit template.

### Monetization hypothesis
CA$20–40 one-off audit; CA$20–50/month recurring property monitoring.

### Competition
Modern PMSs such as Mews already provide blocked-room BI, while hotel maintenance products track work orders. The differentiation is the **cross-system closed-work-order to PMS-unblock reconciliation**, especially for properties with disconnected systems.

### Risk
Integration/export mapping complexity. Modern integrated PMS/maintenance stacks may already eliminate much of the problem.

### Verdict
**Advance cautiously.** Good measurable revenue angle but narrower target market.

---

## Dropped after deeper review

### Hotel room-damage charge evidence preflight
A current dedicated hotel product already builds before/after evidence, prices damage from an asset register and exports claim packs.

### Catering BEO/final-invoice audit
A current product directly reconciles BEOs, agreements, guarantees, changes and final supplier invoices.

### OTA commission/VCC reconciliation
Multiple current specialists automate this and often price on recovered revenue.

### Delivery marketplace payout reconciliation
Current restaurant platforms already reconcile POS, marketplace fees/refunds, payouts and bank deposits.

### Generic hotel housekeeping/maintenance software
Mature category with many current products.

## Stage 3 ranking

1. Hotel front-desk discretionary revenue-leak audit
2. Restaurant menu-channel drift audit
3. Hotel maintenance-complete / room-still-blocked audit

## Advance to Stage 4
Advance those three only.

## Verification record
- Last verified: 2026-10-25
- Stage 3 status: complete
- Stage 5: out of scope
