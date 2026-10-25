---
title: Revenue Investigation — Wave 30 Stage 4 Implementation Plans
summary: Stage 4 implementation and acquisition plans for the strongest Shopify App Store micro-app concepts. No Stage 5 development is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 332
permalink: /projects/notes/revenue-investigation-wave-30-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-30, shopify, stage-4]
---

# Wave 30 Stage 4 — Implementation Plans

Planning only. No development, App Store submission, customer testing, payments or outreach should be executed from this chat.

## Rank 1 — Checkout metafield `owner_type` 2027 readiness scanner

### MVP
- Embedded Shopify app or lightweight developer/admin utility.
- Accept extension configuration/project export or inspect supported app configuration where available.
- Detect checkout metafield declarations missing `owner_type`.
- Infer likely owner type only as a suggestion, never silently modify config.
- Flag conflicting namespace/key declarations across targets.
- Detect API-version pinning that approaches the 2027-01 requirement.
- Generate copy-ready remediation snippets plus exact source references.
- No deployment/write action.

### Commercial model
- Free one-extension scan.
- US$5–15 one-time migration report for single stores/apps.
- Agency tier for multiple stores/apps if demand supports it.

### Acquisition
1. Exact App Store/search keywords around Shopify 2027-01, checkout metafields, `owner_type`, API upgrade and extension migration.
2. Publish concise migration pages whenever Shopify updates the requirement or examples.
3. Free scanner gives immediate value and creates natural upgrade path.
4. Partner/referral opportunity with Shopify agencies and extension developers.
5. Keep support narrow by handling one announced breaking change extremely well.

### Main risk
Time-bounded demand. Best long-term shape is a reusable Shopify platform-change readiness engine with this rule as the first module.

### Stage 4 verdict
**Best first Shopify micro-app to validate in a separate chat.**

---

## Rank 2 — Location / fulfillment-service retirement dependency preflight

### MVP
- Merchant selects a location or fulfillment service.
- Read inventory levels/items tied to it.
- Identify variants stocked exclusively or materially dependent on it.
- Identify open/unfulfilled orders associated with it where APIs allow.
- Show recent fulfillment activity and fulfillment-service associations.
- Show exposed pickup/delivery/routing dependencies.
- Explicitly list uninspectable dependencies.
- Export retirement checklist.
- Never deactivate/remove the location/service.

### Commercial model
- Free one-location scan.
- US$9–19/month for unlimited scans/history/export.
- Agency/multi-store plan later.

### Acquisition
- Shopify App Store keywords around remove location, close warehouse, 3PL migration, fulfillment service migration and store consolidation.
- Evergreen content around safe warehouse/location retirement.
- Useful to agencies during merchant migrations and 3PL changes.

### Main risk
API coverage may not expose every routing dependency.

### Stage 4 verdict
**Best evergreen Wave 30 candidate.**

---

## Rank 3 — Shopify app/function uninstall dependency preflight

### MVP
- Merchant selects an installed app.
- Inventory visible functions/extensions and theme extension presence.
- Inspect visible Flow/app relationships where possible.
- List visible metafield definitions/namespaces associated with the app where permissions allow.
- Show billing/renewal state and recent visible usage indicators.
- Produce a before-you-uninstall checklist.
- Clearly distinguish inspected vs inaccessible/private dependencies.
- Never uninstall or modify another app.

### Commercial model
- Free one-app scan.
- US$9–19/month for unlimited scans and pre/post uninstall reports.
- Agency tier for stores with large app stacks.

### Acquisition
- Search/App Store discovery around uninstall Shopify app, app cleanup, app replacement and migration.
- Agency channel is especially relevant because agencies inherit stores with unknown app dependencies.

### Main risk
Shopify's cross-app isolation may limit visibility enough that the report feels incomplete. API feasibility must be tested first in a separate chat before any build decision.

### Stage 4 verdict
**Potentially valuable, but feasibility risk is materially higher than ranks 1–2.**

## Platform economics note

Shopify's current App Store revenue-share program is attractive for small developers: eligible developers keep 100% of the first US$1M in lifetime gross app revenue earned on or after January 1, 2025, then 85% above that threshold. App billing is subject to a 2.9% processing fee, and App Store registration has a one-time US$19 fee.

## Wave 30 conclusion

Top three:
1. Checkout metafield `owner_type` 2027 readiness scanner
2. Location / fulfillment-service retirement dependency preflight
3. Shopify app/function uninstall dependency preflight

The key lesson is that Shopify's generic micro-tool categories are extremely competitive, but short-lived platform-change niches and narrow lifecycle dependency checks can still offer strong built-in distribution with little sales effort.

## Verification record
- Last verified: 2026-10-25
- Stage 4 status: complete
- Stage 5: explicitly out of scope
