---
title: Revenue Investigation — Wave 38 Stage 2 Viability Filter
summary: Viability filtering for BigCommerce Marketplace ideas, prioritizing multi-storefront lifecycle, price-list assignment simulation and storefront cutover readiness.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 362
permalink: /projects/notes/revenue-investigation-wave-38-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-38, bigcommerce, viability]
---

# Wave 38 Stage 2 — Viability Filter

## Evidence that changed scoring

- BigCommerce Marketplace has roughly 1,400 apps and mature categories in marketing, shipping, catalog/order management, analytics and site tools.
- Unified Billing lets merchants purchase apps through BigCommerce and combine charges on the BigCommerce invoice; automated billing currently carries a 15% revenue share.
- Multi-Storefront creates platform-specific complexity across products, categories, customers, price lists, scripts, pages, redirects, currencies, transactional emails and settings.
- Products must be explicitly assigned to a channel to be sold on that channel; losing an assignment can hide products without a generic platform error.
- Price-list assignment precedence depends on channel + customer group, with fallback to customer-group pricing, customer-group discounts, channel default price list or catalog price. That makes proposed reassignment simulation commercially useful.
- Generic pricing engines and broad migration services exist, but exact Marketplace searches did not surface focused preflight apps for storefront retirement or price-list assignment impact.
- Generic redirect/migration apps are less attractive than a Multi-Storefront-specific cutover report combining routes, site IDs, redirects and channel assignments.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Storefront/channel retirement dependency preflight | 84 | Advance |
| 2 | Price-list assignment change simulator | 82 | Advance |
| 3 | Storefront site/route cutover readiness preflight | 78 | Advance |
| 4 | Product/channel assignment hidden-product audit | 76 | Advance cautiously |
| 5 | Customer-group retirement pricing impact | 72 | Merge into #2 |
| 6 | Installed-app Multi-Storefront compatibility inventory | 70 | Hold |
| 7 | Generic repricing engine | 52 | Drop; direct competitors |
| 8 | Generic migration service/app | 48 | Drop; mature/native competition |
| 9 | Generic redirect manager | 47 | Drop; native/broad competition |
| 10 | Generic catalog sync | 43 | Drop; crowded |

## Stage 3 shortlist
1. Storefront/channel retirement dependency preflight
2. Price-list assignment change simulator
3. Storefront site/route cutover readiness preflight

## Verification record
- Last verified: 2026-10-26
- Stage 2 status: complete
- Stage 5: out of scope
