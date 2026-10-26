---
title: Revenue Investigation — Wave 34 Stage 2 Viability Filter
summary: Viability filtering for WooCommerce Marketplace ideas, prioritizing configuration-change simulation and update readiness over crowded health-check categories.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 346
permalink: /projects/notes/revenue-investigation-wave-34-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-34, woocommerce, viability]
---

# Wave 34 Stage 2 — Viability Filter

## Evidence that changed scoring

- Woo Marketplace supports paid standalone extensions with Woo-hosted billing/licensing and recurring subscription reporting.
- Generic shipping-health tools already detect zone-ordering, overlap and missing-method problems, so static shipping diagnostics are crowded.
- Woo's zone engine is first-match-only. This makes before/after simulation valuable because reordering or deleting zones can silently change which method a customer receives.
- Generic webhook monitoring and Action Scheduler health checks already have current plugins.
- Cart/Checkout Blocks compatibility scanners already exist, so that migration niche is crowded.
- Woo itself exposes extension compatibility signals such as `Tested up to`, HPOS declarations and current advisories, but merchants still have to assemble them into a decision before a core/PHP/WordPress upgrade.
- Order-status control products exist, but a read-only retirement/dependency preflight is narrower than status creation/management.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Shipping-zone change impact simulator | 84 | Advance |
| 2 | Next-Woo-version extension estate readiness report | 80 | Advance |
| 3 | Custom order-status retirement dependency preflight | 76 | Advance |
| 4 | Webhook endpoint/domain retirement preflight | 71 | Hold; monitoring tools adjacent |
| 5 | Global attribute retirement dependency preflight | 70 | Hold |
| 6 | Legacy REST API remaining-use report | 68 | Hold; time-bounded/native logs |
| 7 | Static shipping health checker | 50 | Drop; direct competitors |
| 8 | Checkout Blocks readiness scanner | 47 | Drop; exact competitor |
| 9 | Generic webhook monitor | 45 | Drop; direct competitors |
| 10 | Generic store health audit | 43 | Drop; direct competitors |

## Stage 3 shortlist
1. Shipping-zone change impact simulator
2. Next-Woo-version extension estate readiness report
3. Custom order-status retirement dependency preflight

## Verification record
- Last verified: 2026-10-26
- Stage 2 status: complete
- Stage 5: out of scope
