---
title: Revenue Investigation — Wave 38 Stage 3 Deep Investigation
summary: Deep investigation of the strongest BigCommerce Marketplace opportunities after direct competitor checks.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 363
permalink: /projects/notes/revenue-investigation-wave-38-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-38, bigcommerce, marketplace]
---

# Wave 38 Stage 3 — Deep Investigation

## 1. Storefront/channel retirement dependency preflight

### Problem
BigCommerce Multi-Storefront allows products, categories, customers, price lists, scripts, pages, redirects, currencies, emails and settings to be channel-specific. Retiring or consolidating a storefront/channel can therefore affect far more than its domain. BigCommerce's own compatibility guidance requires apps to be channel-aware because many resources carry channel/site assignments.

### Product
Select a storefront/channel and generate a retirement blast-radius report:
- products/categories assigned only to the selected channel;
- customer/customer-group access tied to the channel where exposed;
- price-list assignments involving the channel;
- site/routes/domain association;
- redirects with the channel's site ID;
- scripts/pages/widgets/theme assignments where APIs expose them;
- channel-specific currencies/settings/emails;
- recent order activity by channel;
- installed apps marked/not marked Multi-Storefront compatible;
- unsupported dependency classes clearly identified.

No channel/storefront is deleted or deactivated automatically.

### Distribution
BigCommerce Marketplace search around Multi-Storefront cleanup, storefront retirement, channel consolidation, brand/site migration and channel deletion.

### Monetization hypothesis
Free one-channel summary; US$29–79/month or annual equivalent for full dependency reports, exports and multi-channel estates using Unified Billing.

### Competition
Multi-Storefront-compatible apps manage active workflows, and migration services handle replatforming. Current exact searches did not surface a focused read-only **storefront retirement blast-radius** app.

### Risk
Not every third-party app's private channel-specific state is inspectable. The report must separate BigCommerce-native dependencies from external unknowns.

### Verdict
**Advance.** Strongest Wave 38 concept.

---

## 2. Price-list assignment change simulator

### Problem
BigCommerce price-list precedence depends on channel and customer-group combinations. A proposed reassignment can therefore change shopper pricing in ways that are not obvious from looking at the price-list table alone. Missing variant records can also fall back to catalog pricing.

### Product
Let the merchant model a proposed assignment/unassignment without applying it, then evaluate selected products/variants/customer groups/channels under current vs proposed rules. Report:
- effective current price source;
- effective proposed price source;
- shopper segments whose price changes;
- variants falling back to catalog pricing;
- customer-group discount conflicts;
- bulk-pricing behavior affected by price records;
- price-list retirement/reassignment dependencies;
- before/after CSV/report.

No live price-list assignment is modified.

### Distribution
Marketplace search around BigCommerce price lists, B2B pricing, customer groups, Multi-Storefront pricing and price-list cleanup.

### Monetization hypothesis
US$19–59/month depending on catalog/segment size, with a free limited simulation.

### Competition
Pricing engines such as Pricewave automate price creation/changes. The surviving wedge is **read-only effective-price simulation before changing BigCommerce's own assignment precedence**, not repricing automation.

### Risk
Final storefront price can be further customized by theme/custom logic, so the app must state that it simulates BigCommerce-native price-list/customer-group precedence rather than every storefront customization.

### Verdict
**Advance.** Strong deterministic B2B/Multi-Storefront utility.

---

## 3. Storefront site/route cutover readiness preflight

### Problem
BigCommerce storefront changes can involve channels, Sites, Routes, domains and site-specific 301 redirects. Multi-Storefront redirects carry `site_id`, and storefront-generated links depend on correct Sites/Routes configuration. During a Catalyst/headless/domain/storefront cutover, missing or misassigned routes/redirects can create broken links or wrong-storefront navigation.

### Product
Select a storefront/site and proposed cutover state, then report:
- current channel -> site -> route/domain mapping;
- missing/duplicate route candidates;
- existing redirects associated with the site;
- URLs likely to lose redirect coverage;
- page/script/widget/theme assignments that remain on the old site where exposed;
- storefront links/domain references in accessible configuration;
- target storefront/channel catalog assignment gaps;
- old-to-new cutover checklist and URL map.

No DNS, route or redirect is changed automatically.

### Distribution
Marketplace search around BigCommerce Catalyst migration, storefront domain migration, Multi-Storefront cutover and headless launch readiness.

### Monetization hypothesis
US$39–99 per cutover project or recurring agency plan; Unified Billing can still support recurring licensing if packaged as an ongoing storefront-change utility.

### Competition
BigCommerce provides a free Data Migration app and agency migration ecosystem, but those focus on getting data into BigCommerce. Current research did not surface a focused **internal storefront/site-route cutover preflight** for merchants changing between BigCommerce storefronts/channels.

### Risk
DNS and external CDN/headless configuration exist outside BigCommerce. Scope must remain BigCommerce-native plus explicit external checklist items.

### Verdict
**Advance cautiously.** Strong event-driven utility with somewhat episodic usage.

## Stage 3 ranking
1. Storefront/channel retirement dependency preflight
2. Price-list assignment change simulator
3. Storefront site/route cutover readiness preflight

## Verification record
- Last verified: 2026-10-26
- Stage 3 status: complete
- Stage 5: out of scope
