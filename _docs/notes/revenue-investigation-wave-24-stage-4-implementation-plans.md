---
title: Revenue Investigation — Wave 24 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest hospitality/restaurant concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 308
permalink: /projects/notes/revenue-investigation-wave-24-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-24, stage-4, hospitality, restaurants]
---

# Wave 24 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — Hotel front-desk discretionary revenue-leak audit

### Core promise
Show an independent hotel where front-desk exceptions such as early check-in, late checkout, upgrades, comps, no-shows and waivers did not line up with the hotel's own policy or expected approval trail.

### MVP plan
- Import reservation, folio and activity/user-action exports from one PMS at a time.
- User configures property policy: check-in/out times, fee bands, upgrade rules, comp/waiver approval thresholds and no-show/cancellation expectations.
- Flag chargeable event with no posted charge or waiver evidence.
- Flag complimentary room, rate override or upgrade lacking configured approval reference.
- Flag checkout-day ancillary sale present in source data but absent from folio where supported.
- Summarize leakage candidate value and exception frequency by event/staff user.
- Export source-linked review worksheet.
- Never automatically charge guests or accuse staff of wrongdoing.

### Likely stack
- Browser/local CSV processor.
- Python deterministic rules/matching engine.
- Saved PMS mapping templates.

### Pricing hypothesis
- Free: limited sample/month.
- CA$20–40 one-off monthly audit.
- CA$25–60/month recurring property plan.
- Multi-property accountant/consultant tier later.

### Semi-automated acquisition pipeline
1. Publish exact-intent content around late-checkout leakage, comps/upgrades and front-desk revenue controls.
2. Free sample audit/template becomes the inbound funnel.
3. Partner with hotel accountants/controllers and PMS consultants.
4. Demonstrate with synthetic reservation/folio exports.
5. Track opt-in PMS formats and exception categories to prioritize mappings.
6. Future validation should focus on independent/boutique properties with manual or mixed workflows, not tightly integrated enterprise hotels.
7. Any outreach remains low-volume/manual-approved; search/referrals are preferred.
8. Route recurring/multi-property demand to the owner.

### Main risks
- PMS export variability.
- Property-specific policies.
- Modern PMSs can automate many controls natively.

### Stage 4 verdict
**Highest-priority Wave 24 candidate.**

---

## Rank 2 — Restaurant menu-channel drift audit

### Core promise
Give an independent restaurant a cheap read-only check showing where POS/source menu data has drifted from its website and delivery channels, without requiring menu-sync middleware.

### MVP plan
- Upload approved source menu or structured CSV/PDF.
- Add declared menu URLs/exports for website and supported delivery channels.
- Match items conservatively by name/size/category.
- Compare prices against configured channel markup rules.
- Flag missing/extra items, unexpected price differences, modifier/size mismatch, stale descriptions and unpropagated revisions.
- Mark inaccessible/ambiguous entries for manual review rather than guessing.
- Export a correction checklist.
- No write-back or automated publishing.

### Likely stack
- Browser upload/public-page fetcher where permitted.
- Python matching/rules engine.
- Optional manual screenshot/export input for restricted channels.

### Pricing hypothesis
- Free: one limited comparison.
- CA$10–20 per full audit.
- CA$10–25/month scheduled monitoring.

### Semi-automated acquisition pipeline
1. Publish search content around wrong prices, stale menus and delivery-app menu drift.
2. Free one-menu comparison is the inbound funnel.
3. Partner with restaurant web agencies and local marketing consultants.
4. Use synthetic/sample menus for demos.
5. Track opt-in channel combinations to prioritize supported sources.
6. Future validation should target independents using disconnected channels rather than operators already on Deliverect/Otter-style sync middleware.
7. Outreach remains referral/search-led and manually approved.
8. Route multi-location/manual-menu users to the owner.

### Main risks
- Platform access restrictions.
- Intentional channel-specific differences.
- Menu-sync platforms can add monitoring.

### Stage 4 verdict
**Useful low-cost audit utility, but competitive and operationally dependent on channel access.**

---

## Rank 3 — Hotel maintenance-complete / room-still-blocked audit

### Core promise
Find hotel rooms that remained out of order after the linked maintenance job was completed, quantifying avoidable blocked-room nights without replacing either the PMS or maintenance system.

### MVP plan
- Import PMS room-block/status history and maintenance work-order export.
- Map room identifiers and timestamps.
- Match blocked intervals to work orders.
- Flag maintenance-complete events where the room remained blocked beyond a configurable tolerance.
- Flag blocked rooms with no linked work-order evidence.
- Flag rooms returned to service before work completion for manual review.
- Calculate candidate blocked room-nights and optional revenue impact using hotel-supplied ADR/occupancy assumptions.
- Export exception worksheet.
- Never decide whether a room is safe/ready to sell.

### Likely stack
- CSV/XLSX browser/local audit utility.
- Python timestamp/event matching.
- Saved mappings for common PMS/maintenance exports.

### Pricing hypothesis
- CA$20–40 one-off audit.
- CA$20–50/month recurring property check.

### Semi-automated acquisition pipeline
1. Publish search content around out-of-order room leakage and maintenance-to-PMS handoff failures.
2. Free blocked-room audit template demonstrates the concept.
3. Partner with hotel asset managers, controllers and PMS/maintenance consultants.
4. Use synthetic room/work-order data for demos.
5. Focus on properties where PMS and engineering systems are disconnected.
6. Track opt-in mapping formats to prioritize integrations.
7. Future outreach remains manual/partner-led.
8. Route multi-property portfolio users to the owner.

### Main risks
- Modern integrated systems already reduce the problem.
- Matching work orders to room blocks can be messy.
- Revenue impact is estimated, not guaranteed recoverable revenue.

### Stage 4 verdict
**Narrow but measurable cross-system revenue-control opportunity.**

## Wave 24 conclusion

Top three:

1. Hotel front-desk discretionary revenue-leak audit
2. Restaurant menu-channel drift audit
3. Hotel maintenance-complete / room-still-blocked audit

Wave 24 confirms that hospitality software is crowded at the operational-platform level, but smaller read-only audit gaps remain where policy, guest charges, menu copies and room-status handoffs cross system boundaries.

## Verification record
- Last verified: 2026-10-25
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
