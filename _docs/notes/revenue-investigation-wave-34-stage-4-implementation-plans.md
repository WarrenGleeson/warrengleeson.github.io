---
title: Revenue Investigation — Wave 34 Stage 4 Implementation Plans
summary: Stage 4 implementation and acquisition plans for the strongest WooCommerce Marketplace extension concepts. No Stage 5 development is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 348
permalink: /projects/notes/revenue-investigation-wave-34-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-34, woocommerce, stage-4]
---

# Wave 34 Stage 4 — Implementation Plans

Planning only. No development, Marketplace submission, customer testing, payments or outreach should be executed from this chat.

## Rank 1 — Shipping-zone change impact simulator

### MVP
- Native WooCommerce admin extension.
- Read current shipping zones/methods/postcode rules.
- Let merchant clone a zone configuration into a temporary proposed state.
- Allow simulated reorder, delete, postcode-region change, method removal and free-shipping threshold change.
- Re-run Woo zone matching against recent historical order shipping addresses and optional manually entered addresses.
- Compare current vs proposed matched zone/method availability.
- Summarize affected orders, customers, regions and historical order value.
- Clearly exclude third-party live carrier-rate calculations unless deterministic support is added later.
- No production configuration writes.

### Commercial model
- Standard paid Woo Marketplace extension.
- Target roughly US$39–79/year per site, depending on Marketplace fit and support burden.
- Core value should work locally without SaaS infrastructure.

### Acquisition
1. Marketplace keywords: shipping zone change, postcode shipping, shipping zone audit, shipping migration, shipping method removal.
2. Position against health-check tools: “see what changes **before** you reorder or delete a zone.”
3. Use screenshots showing actual historical orders moving from one zone/method to another.
4. Agency/consultant adoption can happen organically through Marketplace discovery and client migrations.

### Main risks
- Dynamic third-party shipping rates cannot be fully reproduced.
- Historical addresses may not represent future geographic demand.
- Large order histories require efficient batching/caching.

### Stage 4 verdict
**Best Wave 34 candidate for a separate validation/build chat.**

---

## Rank 2 — Next-Woo-version extension estate readiness report

### MVP
- Woo admin extension.
- User selects target WooCommerce, WordPress and optional PHP version.
- Inventory active Woo extensions/plugins, theme and payment gateways.
- Read installed plugin headers and available compatibility metadata.
- Flag target version beyond `WC tested up to` / WordPress `Tested up to`.
- Surface PHP minimum/version conflicts.
- Surface HPOS and Cart/Checkout Blocks compatibility declarations where available.
- Add Woo advisory/change notes only where the target release clearly intersects detected features/extensions.
- Produce ready / stale metadata / unknown / staging-required buckets.
- Generate printable/exportable pre-update checklist.
- Never update production or claim a stack is guaranteed compatible.

### Commercial model
- US$49–99/year/site.
- Potential agency/multi-site product later if Marketplace licensing allows suitable packaging.

### Acquisition
1. Search terms around WooCommerce update compatibility, Woo upgrade checker, PHP upgrade WooCommerce and extension compatibility.
2. New Woo releases create recurring discovery moments.
3. Free/light summary could show number of unknown/stale components, with paid full report if Marketplace pricing strategy permits.
4. Keep support bounded by reporting evidence rather than debugging third-party plugins.

### Main risks
- Compatibility declarations may be wrong or stale.
- Woo core may improve native compatibility reporting.
- Merchant expectations must be managed: this is a staging-readiness tool, not a guarantee.

### Stage 4 verdict
**Strong recurring maintenance product with platform-change-driven demand.**

---

## Rank 3 — Custom order-status retirement dependency preflight

### MVP
- Read-only Woo admin extension.
- Order-status picker.
- Count current and historical orders using the status.
- Inspect Woo-native email/webhook configuration references.
- Inspect Action Scheduler arguments/settings for deterministic literal references where safe.
- Optional local static scan of active plugin/theme PHP/config for status slug references.
- List dependency classes that cannot be inspected reliably.
- Generate migration/retirement checklist.
- No status deletion/rename/order mutation.

### Commercial model
- US$29–59/year/site.
- Could later expand into a broader Woo workflow-retirement toolkit only if demand validates it.

### Acquisition
1. Marketplace keywords: custom order status cleanup, remove order status, order workflow migration.
2. Position as a safety layer beside order-status management products.
3. Agency use during store cleanup/migration is a natural secondary channel.

### Main risks
- Third-party plugins can store status references arbitrarily.
- Static PHP scanning can create noisy findings.
- Smaller total addressable market than ranks 1–2.

### Stage 4 verdict
**Viable narrow extension, but less scalable than the first two.**

## Platform conclusion

Woo Marketplace is a solid fit for this research objective because standalone extensions can be sold through Woo's standard Marketplace license model, while Woo handles the billing relationship. The strongest opportunities are not generic store-health tools but narrowly scoped, locally executed utilities that help merchants safely change existing configuration.

## Wave 34 conclusion

Top three:
1. Shipping-zone change impact simulator
2. Next-Woo-version extension estate readiness report
3. Custom order-status retirement dependency preflight

## Verification record
- Last verified: 2026-10-26
- Stage 4 status: complete
- Stage 5: explicitly out of scope
