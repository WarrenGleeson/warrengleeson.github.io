---
title: Revenue Investigation — Wave 38 Stage 4 Implementation Plans
summary: Stage 4 implementation and acquisition plans for the strongest BigCommerce Marketplace concepts. No Stage 5 development is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 364
permalink: /projects/notes/revenue-investigation-wave-38-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-38, bigcommerce, stage-4]
---

# Wave 38 Stage 4 — Implementation Plans

Planning only. No development, Marketplace submission, customer testing, payments or outreach should be executed from this chat.

## Rank 1 — Storefront/channel retirement dependency preflight

### MVP
- Embedded BigCommerce app using read-only scopes wherever possible.
- Channel/storefront picker.
- Inventory product/category channel assignments.
- Flag products/categories assigned only to the selected channel.
- Inventory price-list/customer-group assignments involving the channel.
- Resolve channel -> site -> route/domain relationships.
- Inventory site-specific redirects and exposed scripts/pages/widgets/themes.
- Include channel-specific settings/currencies/emails where APIs expose them.
- Show recent orders by channel and installed-app Multi-Storefront compatibility metadata where available.
- Export retirement checklist/report.
- Never deactivate/delete the channel.

### Commercial model
- Free one-channel summary.
- Paid roughly US$29–79/month or annual equivalent for full dependency reports, exports and multi-channel estates.
- Use BigCommerce Unified Billing so charges appear on the merchant's BigCommerce invoice.
- Current automated-billing revenue share: 15% of net revenue.

### Acquisition
1. Marketplace keywords: Multi-Storefront cleanup, storefront retirement, channel consolidation, storefront migration.
2. Position around one question: “What stops working if I retire this storefront?”
3. Screenshots should show products, price lists, routes and content grouped by dependency type.
4. Multi-storefront agencies/consultants are a natural secondary channel, but Marketplace discovery remains primary.

### Main risks
- Third-party private app state may be invisible.
- Large catalogs require careful batching/caching.

### Stage 4 verdict
**Best Wave 38 candidate for separate validation/build.**

---

## Rank 2 — Price-list assignment change simulator

### MVP
- Embedded read-only BigCommerce app.
- Import current price lists, assignments, customer groups and relevant catalog prices.
- Merchant selects a proposed assignment/unassignment or retirement scenario.
- Evaluate BigCommerce-native precedence for selected channel/customer-group/product combinations.
- Flag customers/segments whose effective price source changes.
- Flag variants that fall back to catalog pricing.
- Flag customer-group discount conflicts and bulk-tier interactions where deterministic.
- Produce before/after matrix and CSV.
- No live assignment or price changes.

### Commercial model
- Free small simulation.
- Paid US$19–59/month depending on catalog/segment scale.
- Unified Billing preferred.

### Acquisition
1. Marketplace terms around price lists, B2B pricing, customer groups and Multi-Storefront pricing.
2. Position against repricing engines: this app does not change prices; it shows the consequence before an assignment change.
3. Merchant-facing screenshots should show current price → proposed price → source rule.

### Main risks
- Theme/custom checkout logic can alter final displayed price beyond native precedence.
- Complex B2B setups may require careful scope boundaries.

### Stage 4 verdict
**Strong deterministic utility with obvious financial value.**

---

## Rank 3 — Storefront site/route cutover readiness preflight

### MVP
- Storefront/site picker.
- Inventory current channel/site/routes/domains.
- Model proposed target route/domain/storefront state.
- Flag duplicate/missing routes and site mismatches.
- Inventory 301 redirects by `site_id` and identify old URLs lacking planned coverage.
- Flag catalog assignments missing from the target channel.
- Include exposed page/script/widget/theme assignments still tied to the old site.
- Export old-to-new URL/cutover checklist.
- No DNS/route/redirect changes.

### Commercial model
- US$39–99 per project if Marketplace packaging supports it cleanly, or recurring agency/multi-storefront plan.
- Unified Billing preferred where recurring pricing is used.

### Acquisition
1. Marketplace keywords: Catalyst migration, headless migration, storefront cutover, domain migration, Multi-Storefront launch.
2. Content tied to storefront redesigns and channel consolidations.
3. Agency use is likely more important here than for ranks 1–2.

### Main risks
- Episodic use.
- DNS/CDN/headless configuration exists outside BigCommerce and must be listed as external checklist items.

### Stage 4 verdict
**Useful event-driven utility, but less recurring than ranks 1–2.**

## Platform economics note

BigCommerce remains viable for this platform-native strategy. Approved apps receive Marketplace distribution, and Unified Billing lets merchants purchase apps through BigCommerce with the charge included on their BigCommerce invoice. Current automated-billing terms give BigCommerce 15% of net app revenue. The ecosystem is smaller than Shopify but Multi-Storefront and B2B/channel complexity creates higher-value administrative niches.

## Wave 38 conclusion

Top three:
1. Storefront/channel retirement dependency preflight
2. Price-list assignment change simulator
3. Storefront site/route cutover readiness preflight

Wave 38 reinforces the same winning pattern: use the host platform's internal configuration graph to answer a narrow, high-consequence “what changes if I do this?” question that generic ecommerce tools cannot answer reliably.

## Verification record
- Last verified: 2026-10-26
- Stage 4 status: complete
- Stage 5: explicitly out of scope
