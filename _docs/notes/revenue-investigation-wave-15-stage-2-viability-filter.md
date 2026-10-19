---
title: Revenue Investigation — Wave 15 Stage 2 Viability Filter
summary: Evidence-based filtering of Wave 15 ideas across TLS lifecycle readiness, browser deprecations, email authentication and PCI e-commerce evidence tooling.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 270
permalink: /projects/notes/revenue-investigation-wave-15-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-15, viability]
---

# Wave 15 Stage 2 — Viability Filter

## Evidence that changed scoring

- CA/Browser Forum SC-081 establishes a staged reduction in public TLS certificate lifetimes, eventually reaching 47 days by 2029, with shorter validation-data reuse windows. Certificate lifecycle management is already mature, so the opportunity is not another CLM platform but identifying **where manual renewal dependencies still exist** before short validity makes them operationally unsafe.
- AWS ACM already offers 45-day ACME-issued certificates, explicitly positioning them for the shorter-validity future and reinforcing that automation is becoming mandatory rather than optional.
- Chrome has completed deprecating the `unload` event as of Chrome 155; handlers no longer fire by default. This turns old unload-dependent behavior into a concrete regression/migration problem.
- Chrome plans to disable client-side XSLT for normal Stable users in Chrome 158 on 17 November 2026, with only temporary origin-trial/enterprise-policy escape hatches thereafter.
- PCI payment-page script inventory/tamper monitoring is a heavily populated market with specialized vendors, CDN/WAF products and free tools.
- DMARC/SPF/DKIM monitoring is similarly mature, especially for multi-domain/MSP use cases.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Client-side XSLT dependency / migration scanner | 82 | Advance |
| 2 | Shorter-TLS-lifetime manual-renewal exposure scanner | 80 | Advance |
| 3 | `unload` behavior replacement/regression test pack | 78 | Advance |
| 4 | Browser deprecation CI gate | 75 | Advance; merge into #1/#3 |
| 5 | Certificate inventory vs renewal-method audit | 74 | Merge into #2 |
| 6 | Chrome enterprise-policy exception tracker | 71 | Feature of #1 |
| 7 | Deprecated browser API inventory | 69 | Hold; broad |
| 8 | Sender-domain alignment preflight | 67 | Hold; crowded email-auth tooling |
| 9 | SPF include-chain risk report | 65 | Hold |
| 10 | Payment-page script ownership inventory | 63 | Hold; direct competition |
| 11 | Payment-page header baseline diff | 61 | Hold; commercial tools cover it |
| 12 | PCI evidence exporter | 59 | Hold |
| 13 | DMARC multi-domain inventory | 57 | Drop; mature category |
| 14 | Generic certificate expiry monitor | 53 | Drop; commodity |
| 15 | Full certificate lifecycle manager | 47 | Drop; established enterprise market |
| 16 | Generic PCI script monitor | 45 | Drop; saturated |

## Stage 3 shortlist

1. Client-side XSLT dependency / migration scanner
2. Shorter-TLS-lifetime manual-renewal exposure scanner
3. `unload` behavior replacement/regression test pack
4. Browser deprecation CI gate
5. Certificate renewal owner inventory

## Verification record

- Last verified: 2026-10-19
- Stage 2 status: complete
- Stage 5: out of scope
