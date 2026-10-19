---
title: Revenue Investigation — Wave 7 Stage 2 Viability Filter
summary: Evidence-based filtering of Wave 7, emphasizing low-touch acquisition, current platform changes, competition and maintenance burden.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 238
permalink: /projects/notes/revenue-investigation-wave-7-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-7, viability]
---

# Wave 7 Stage 2 — Viability Filter

## Evidence that changed scoring

- YouTube currently accepts podcast RSS ingestion in many countries, but has YouTube-specific constraints: invalid title/description characters are rejected, RSS-updated show details are not automatically synchronized, re-uploaded audio does not automatically replace published YouTube videos, and branded content requires disclosure. This creates a specific preflight problem beyond generic RSS validation.
- Google updated merchant-listing documentation in July 2026 to clarify sale-duration structured data using `validFrom`, `validThrough` and `priceValidUntil`, and also added `Product.category` guidance. That creates a recent narrow audit opportunity.
- Generic product price/availability mismatch checking is already crowded with current purpose-built tools, so Wave 7 should not pursue another broad Merchant Center checker.
- Shopify introduced multiple 2026 action-required changes around metafield definitions, customer-account access, JSON metafield limits, API mutations and shipping-profile behavior. This supports app-developer upgrade/readiness tooling, but generic metafield editing is already highly saturated.
- Generic PWA manifest validation is crowded with several current free tools that already inspect manifest fields, icons and installability.
- Chargeback evidence packet assembly, invoice-sequence auditing and defined-term checking all have current direct products or tools.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | YouTube podcast RSS compatibility/preflight checker | 80 | Advance |
| 2 | Shopify API-version/action-required upgrade scanner | 79 | Advance |
| 3 | Merchant sale-window structured-data validator | 77 | Advance |
| 4 | Shopify customer-account metafield access auditor | 76 | Advance |
| 5 | Shopify webhook/event-subscription coverage checker | 74 | Advance |
| 6 | Podcast RSS metadata/artwork audit | 72 | Advance cautiously |
| 7 | Podcast episode replacement/change-log helper | 71 | Advance cautiously |
| 8 | Shopify JSON-metafield size-risk scanner | 70 | Advance cautiously |
| 9 | Shopify carrier-service shipping-profile audit | 69 | Hold |
| 10 | Product schema GTIN/MPN consistency audit | 68 | Hold |
| 11 | Payment processor fee reconciliation checker | 66 | Hold; broad accounting competition |
| 12 | Merchant payout-to-order reconciliation | 66 | Hold |
| 13 | Form/PDF website version mismatch detector | 65 | Hold |
| 14 | Cron timezone/DST hazard checker | 64 | Hold; many developer substitutes |
| 15 | Contract defined-term checker | 58 | Drop; direct legal-tech substitute |
| 16 | Chargeback evidence packet assembler | 55 | Drop; direct current substitute |
| 17 | Invoice number gap/duplicate audit | 54 | Drop; direct free substitute |
| 18 | PWA manifest asset completeness validator | 50 | Drop; crowded free-tool category |
| 19 | Merchant price/availability mismatch checker | 48 | Drop; crowded direct competition |
| 20 | PWA screenshot/icon packaging checker | 47 | Drop; crowded generators/validators |

## Stage 3 shortlist

1. YouTube podcast RSS compatibility/preflight checker
2. Shopify API-version/action-required upgrade scanner
3. Merchant sale-window structured-data validator
4. Shopify customer-account metafield access auditor
5. Shopify webhook/event-subscription coverage checker

## Current sources

- YouTube Help: RSS podcast ingestion, publishing and re-upload behavior
- Google Search Central July 2026 merchant-listing documentation update
- Google Merchant Center sale-price/effective-date specifications
- Shopify 2026 changelog and customer-account/metafield documentation
- current merchant-data, PWA, chargeback and legal-document competitors

## Verification record

- Last verified: 2026-10-19
- Stage 2 status: complete
- Stage 5: out of scope
