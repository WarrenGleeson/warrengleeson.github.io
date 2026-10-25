---
title: Revenue Investigation — Wave 30 Stage 3 Deep Investigation
summary: Deep investigation of the strongest Shopify App Store micro-app opportunities after direct competitor checks.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 331
permalink: /projects/notes/revenue-investigation-wave-30-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-30, shopify, app-store]
---

# Wave 30 Stage 3 — Deep Investigation

## 1. Checkout metafield `owner_type` 2027 readiness scanner

### Problem
Shopify checkout extensions can declare metafields in extension configuration. In API version 2026-10, `owner_type` is optional, but Shopify documents that it becomes required in 2027-01. App developers/merchants with older extension configurations need to identify affected extensions before upgrading API versions.

### Product
A narrow readiness utility that scans app/extension configuration supplied by the merchant/developer and flags:
- checkout metafield declarations missing `owner_type`;
- ambiguous owner inference requiring manual review;
- multiple targets referencing the same namespace/key inconsistently;
- config files pinned to older API versions;
- exact remediation guidance with generated config snippets for review.

The tool does not deploy changes automatically.

### Distribution
Shopify App Store search around checkout migration, API 2027-01, metafields and extension readiness; changelog-driven landing pages.

### Monetization hypothesis
Free single-extension scan; US$5–15 one-time migration report or low-cost monthly monitoring for agencies managing multiple stores/apps.

### Competition
Current checkout migration apps focus on Scripts/checkout.liquid/pixels. The current review did not identify a dedicated `owner_type` migration checker.

### Risk
This is a time-bounded migration niche. Best suited either as a fast micro-app or as the first module in a broader Shopify platform-change readiness product.

### Verdict
**Advance.** Strongest Wave 30 launchable micro-niche.

---

## 2. Location / fulfillment-service retirement dependency preflight

### Problem
Merchants with multiple locations, 3PLs or fulfillment services can retire a location/service while products, inventory policies, orders or routing assumptions still depend on it. Shopify exposes the underlying location/fulfillment configuration, but admins may not have a simple blast-radius view before removal.

### Product
Select a location or fulfillment service and report:
- inventory items stocked there;
- open/unfulfilled orders assigned or routed there where visible;
- products/variants relying exclusively on that location for stock;
- delivery/pickup configuration references where exposed;
- fulfillment-service associations;
- recent fulfillment activity;
- unsupported dependency classes explicitly listed.

No location/service is disabled or removed automatically.

### Distribution
App Store search around location cleanup, warehouse/3PL migration and fulfillment-service removal.

### Monetization hypothesis
Free one-location scan; US$9–19/month unlimited scans/history for multi-location merchants/agencies.

### Competition
Routing and fulfillment apps manage active operations, but current research did not surface a focused read-only retirement blast-radius checker.

### Risk
Some routing/configuration dependencies may not be exposed cleanly through APIs.

### Verdict
**Advance.** Good evergreen admin niche.

---

## 3. Shopify app/function uninstall dependency preflight

### Problem
Removing an app can affect checkout functions, Flow actions, theme extensions, metafields or merchant workflows. Shopify handles app uninstall lifecycle events, but merchants often do not have a unified dependency checklist before uninstalling a critical app.

### Product
For an installed app, assemble what can be inspected safely:
- active app extensions/functions visible to the merchant;
- Flow workflows/actions referencing the app where APIs/data allow;
- theme app extension presence;
- app-related metafield definitions/namespaces visible to the merchant;
- billing/renewal state;
- recent usage signals where exposed;
- unsupported/private dependencies clearly labeled.

The app never uninstalls other apps.

### Distribution
App Store search around uninstall cleanup, app migration and Shopify app replacement.

### Monetization hypothesis
Free one-app dependency scan; US$9–19/month for stores/agencies managing many apps.

### Competition
Current app cleanup tools focus on theme residue after uninstall. A broader pre-uninstall dependency report appears less directly served.

### Risk
Cross-app visibility is constrained by Shopify permissions and app-owned data isolation, so coverage may be partial.

### Verdict
**Advance cautiously.** Strong concept, but API feasibility is the gating issue.

## Stage 3 ranking
1. Checkout metafield `owner_type` 2027 readiness scanner
2. Location / fulfillment-service retirement dependency preflight
3. Shopify app/function uninstall dependency preflight

## Verification record
- Last verified: 2026-10-25
- Stage 3 status: complete
- Stage 5: out of scope
