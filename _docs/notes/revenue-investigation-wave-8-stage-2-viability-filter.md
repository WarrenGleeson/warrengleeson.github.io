---
title: Revenue Investigation — Wave 8 Stage 2 Viability Filter
summary: Evidence-based filtering of Wave 8 platform-change and compliance-readiness ideas, with direct competitors and official substitutes considered.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 242
permalink: /projects/notes/revenue-investigation-wave-8-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-8, viability]
---

# Wave 8 Stage 2 — Viability Filter

## Evidence that changed scoring

- Google Ads API v26 was released October 14, 2026 with breaking changes. Google publishes version diffs and sunset schedules, but the current search did not surface a strong repository scanner that maps those changes directly to an integration's source/config.
- Amazon.ca introduced new lithium-battery compliance requirements for several electronics/smart-home/home-appliance categories in late September 2026, including authorized TIC review, recent accredited test reports, model/manufacturer listing data and, for some lithium-ion products, UN 38.3/Battery Test Summary requirements.
- Amazon's January 2027 bundle-policy change already has a dedicated free Bundle Watch product, eliminating a clean wedge for a generic bundle checker.
- The Content API for Shopping sunset has already occurred; Google now provides detailed Merchant API migration tooling and an official AI/code-assist toolkit, while an open-source `gmc` CLI already offers migration and preflight commands. Generic Merchant migration tooling is therefore crowded.
- FIRE is retiring for filing season 2027 and IRIS becomes the intake system for affected information returns. IRIS schemas/business rules are actively versioned, but IRS QuickAlerts already provides schema/business-rule notifications. The opportunity, if any, must be in local diffing/impact analysis rather than alerts alone.
- A current third-party IRIS file checker already validates CSV/XML against business rules, weakening generic file-preflight ideas.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Google Ads API version-upgrade source scanner | 81 | Advance |
| 2 | Amazon.ca lithium-battery readiness workspace | 78 | Advance |
| 3 | IRIS schema/business-rule local diff + impact report | 76 | Advance |
| 4 | Google Ads API sunset / dependency inventory | 74 | Advance; merge with #1 |
| 5 | Amazon category policy-change impact scanner | 73 | Advance cautiously |
| 6 | Stripe API changelog impact scanner | 72 | Advance cautiously |
| 7 | SaaS API release-note to action-item converter | 70 | Hold; broad category |
| 8 | Amazon Product Compliance notification normalizer | 69 | Hold |
| 9 | IRS IRIS known-issues digest | 66 | Hold; QuickAlerts substitute |
| 10 | Merchant API failed-call diagnostics summarizer | 65 | Hold; native diagnostics exist |
| 11 | Amazon liability-insurance readiness tracker | 63 | Hold; narrow and legal/insurance adjacent |
| 12 | IRIS filing-size/record-limit preflight | 61 | Hold; direct checker substitute |
| 13 | Merchant API release-note impact monitor | 60 | Hold; official tooling strong |
| 14 | Amazon title + Item Highlights auditor | 55 | Drop; free exact tools exist |
| 15 | Amazon bundle policy checker | 50 | Drop; exact free competitor |
| 16 | Generic Merchant API migration scanner | 48 | Drop; official + OSS tooling |
| 17 | IRIS notification-only service | 47 | Drop; IRS QuickAlerts |
| 18 | Generic compliance-deadline calendar | 46 | Drop; many existing calendars |

## Stage 3 shortlist

1. Google Ads API version-upgrade source scanner
2. Amazon.ca lithium-battery readiness workspace
3. IRIS schema/business-rule local diff + impact report
4. Amazon category policy-change impact scanner
5. Stripe API changelog impact scanner

## Verification record

- Last verified: 2026-10-19
- Stage 2 status: complete
- Stage 5: out of scope
