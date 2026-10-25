---
title: Revenue Investigation — Wave 30 Stage 2 Viability Filter
summary: Viability filtering for Shopify App Store micro-app ideas, prioritizing platform-change readiness and lifecycle dependency utilities over crowded catalog/Markets QA categories.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 330
permalink: /projects/notes/revenue-investigation-wave-30-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-30, shopify, viability]
---

# Wave 30 Stage 2 — Viability Filter

## Evidence that changed scoring

- Generic Shopify catalog QA is now crowded, including multiple new 2026 apps for duplicate/missing SKU, barcode and product-data checks.
- Shopify Markets QA and market-price monitoring also have several current dedicated apps.
- Checkout migration/legacy script auditing already has exact current products.
- Product retirement/successor workflows have current dedicated apps.
- Shopify API version 2026-10 makes checkout-extension metafield `owner_type` optional but documents that it becomes required starting with API version 2027-01, creating a specific migration-readiness niche.
- Read-only dependency/preflight apps remain attractive because they require fewer write permissions, have lower operational risk and map well to App Store search around a specific migration/change event.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Checkout metafield `owner_type` 2027 readiness scanner | 84 | Advance |
| 2 | Shopify app/function uninstall dependency preflight | 79 | Advance cautiously |
| 3 | Location / fulfillment-service retirement dependency preflight | 77 | Advance |
| 4 | Admin API version dependency inventory | 75 | Advance cautiously |
| 5 | Product retirement dependency preflight | 67 | Hold; adjacent successor/archive apps |
| 6 | Flow app-action uninstall impact checker | 66 | Hold; visibility/API limits |
| 7 | Markets publication/price QA | 52 | Drop; direct current competitors |
| 8 | Generic product-data checker | 48 | Drop; heavily crowded |
| 9 | SKU/barcode audit | 45 | Drop; heavily crowded |
| 10 | Checkout migration audit | 44 | Drop; exact current competitor |

## Stage 3 shortlist

1. Checkout metafield `owner_type` 2027 readiness scanner
2. Location / fulfillment-service retirement dependency preflight
3. Shopify app/function uninstall dependency preflight

## Verification record
- Last verified: 2026-10-25
- Stage 2 status: complete
- Stage 5: out of scope
