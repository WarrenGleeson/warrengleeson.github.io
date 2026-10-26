---
title: Revenue Investigation — Wave 34 Stage 3 Deep Investigation
summary: Deep investigation of the strongest WooCommerce Marketplace extension opportunities after direct competitor checks.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 347
permalink: /projects/notes/revenue-investigation-wave-34-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-34, woocommerce, marketplace]
---

# Wave 34 Stage 3 — Deep Investigation

## 1. Shipping-zone change impact simulator

### Problem
WooCommerce shipping zones are first-match-only. Reordering, narrowing or deleting a zone can therefore change which shipping methods customers receive without producing a configuration error. Existing shipping-health plugins diagnose the current setup, but merchants still lack a simple before/after impact report using their own recent order geography.

### Product
A read-only admin extension that lets the merchant model a proposed zone/method change and compare current vs proposed behavior across recent orders or uploaded test addresses. It reports:
- orders/addresses whose matched zone would change;
- shipping methods gained/lost;
- historical order value affected;
- postcode/country regions newly uncovered or captured by another zone;
- free-shipping threshold/method changes where deterministic;
- ambiguous third-party method behavior explicitly excluded.

No production shipping settings are modified.

### Distribution
Woo Marketplace search around shipping zone changes, postcode rules, shipping migration and checkout troubleshooting.

### Monetization hypothesis
Annual Woo Marketplace license in the roughly US$39–79 range, with one-site usage and recurring updates/support.

### Competition
Shipping Doctor and store-audit plugins inspect current configuration and test individual addresses. The surviving wedge is **proposed-change simulation against actual historical order geography**, not static health checking.

### Risk
Third-party carrier extensions may calculate rates dynamically and cannot be fully simulated. Scope should focus on zone/method selection rather than guaranteed rate calculation.

### Verdict
**Advance.** Strongest Wave 34 concept.

---

## 2. Next-Woo-version extension estate readiness report

### Problem
Woo recommends staging updates and checking each active extension/theme/payment gateway against compatibility signals such as `Tested up to`, release notes and supported features. Store owners with many extensions must manually assemble this evidence before a WooCommerce, WordPress or PHP upgrade.

### Product
Select a target WooCommerce/WordPress/PHP version and generate a stack-readiness report:
- installed extension/theme current version;
- declared Woo/WordPress/PHP requirements and tested-up-to metadata;
- HPOS / Cart & Checkout Blocks declarations where available;
- active extension with target-version gap;
- known Woo advisories/change areas relevant to detected extensions or hooks where deterministic;
- extension update available before target upgrade;
- risk bucket: declared ready / stale metadata / unknown / requires staging test.

It never claims compatibility from metadata alone and never updates production automatically.

### Distribution
Woo Marketplace search around WooCommerce update compatibility, PHP upgrade, WordPress upgrade and extension compatibility.

### Monetization hypothesis
US$49–99/year per site; agency tier later if marketplace policy supports the model.

### Competition
Woo exposes compatibility metadata and existing plugins cover specific migrations such as Checkout Blocks, but current research did not surface a focused Marketplace product assembling the **entire active Woo stack into a target-version readiness report**.

### Risk
Metadata can be stale or inaccurate. The product must position the report as evidence for staging decisions, not proof that an upgrade is safe.

### Verdict
**Advance.** Useful recurring maintenance utility.

---

## 3. Custom order-status retirement dependency preflight

### Problem
Stores using custom statuses can accumulate statuses referenced by email triggers, webhooks, automation plugins, exports, reports and operational procedures. Removing/renaming a status can silently change order workflows even if no orders currently use it.

### Product
Select an order status and report discoverable dependencies:
- current/historical orders using it;
- Woo email settings/triggers tied to it where exposed;
- active webhooks/topics/settings referencing it;
- scheduled actions or configuration records with literal status references where safely discoverable;
- plugin/theme code references where local static scanning is enabled;
- unresolved dynamic/plugin-owned dependency classes;
- retirement/migration checklist.

No status or order is modified.

### Distribution
Woo Marketplace search around custom order-status cleanup, status migration and store workflow maintenance.

### Monetization hypothesis
US$29–59/year per site.

### Competition
Order Status Control and similar products create/manage statuses. Current review did not surface a focused **retirement blast-radius** extension.

### Risk
Third-party plugins can store references in arbitrary schemas, making complete coverage impossible. The app must clearly distinguish checked vs unknown dependency classes.

### Verdict
**Advance cautiously.** Good niche, but cross-plugin visibility is the limiting factor.

## Stage 3 ranking
1. Shipping-zone change impact simulator
2. Next-Woo-version extension estate readiness report
3. Custom order-status retirement dependency preflight

## Verification record
- Last verified: 2026-10-26
- Stage 3 status: complete
- Stage 5: out of scope
