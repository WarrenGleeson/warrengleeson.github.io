---
title: Revenue Investigation — Wave 12 Stage 2 Viability Filter
summary: Evidence-based filtering of Wave 12 ideas across AI Act transparency, Chrome Web Store policy readiness, Atlassian Marketplace trust/security, software commercial-term drift and vendor governance.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 258
permalink: /projects/notes/revenue-investigation-wave-12-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-12, viability]
---

# Wave 12 Stage 2 — Viability Filter

## Evidence that changed scoring

- EU AI Act Article 50 transparency obligations have applied since 2 August 2026, and the Commission has now published both guidelines and a Code of Practice. This confirms a real operational need, but broad AI transparency/compliance tooling is likely to be crowded and embedded into larger content/governance platforms.
- Chrome Web Store policy changes announced in July 2026 require data collection to be necessary to an extension's disclosed single purpose, require prominent disclosure of all data collection, and require developers to disclose data-handling changes after installation. Enforcement began 1 August 2026. These requirements map directly to extension manifests, permissions, privacy policies and store listings.
- Chrome also continues to enforce narrow/minimum permission usage, creating a deterministic audit opportunity.
- Atlassian's 2026 Marketplace requirements include partner verification, security checks, privacy/security disclosures, vulnerability handling, and ongoing security enforcement. The new Atlassian Enterprise Certified program adds a pre-submission scorecard for Forge apps.
- Atlassian already performs its own scanners and approval checks, so the best opportunity is a local/pre-submission readiness tool rather than a competing certification platform.
- Generic SaaS pricing/terms monitoring and vendor privacy monitoring are already crowded by procurement, contract-management and vendor-risk products.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Chrome extension privacy/disclosure vs manifest preflight | 81 | Advance |
| 2 | Atlassian Marketplace pre-submission trust/security checker | 79 | Advance |
| 3 | Chrome extension permission-change release preflight | 77 | Advance |
| 4 | Atlassian Forge egress/data-residency configuration audit | 76 | Advance |
| 5 | AI-generated content label coverage checker | 72 | Advance cautiously |
| 6 | AI provenance metadata preservation checker | 70 | Advance cautiously |
| 7 | Atlassian Privacy & Security tab completeness preflight | 69 | Merge into #2 |
| 8 | Chrome single-purpose/data-use consistency scanner | 69 | Merge into #1 |
| 9 | Chrome minimum-permissions auditor | 68 | Merge into #1/#3 |
| 10 | Atlassian AEC readiness report | 67 | Merge into #2 |
| 11 | SaaS plan-feature removal impact inventory | 64 | Hold |
| 12 | AI provider terms/data-use change monitor | 63 | Hold; broad monitoring competition |
| 13 | SaaS subprocessor change monitor | 61 | Hold; vendor-risk platforms already cover this |
| 14 | Vendor evidence freshness monitor | 60 | Hold |
| 15 | SaaS pricing/limit monitor | 58 | Drop; crowded |
| 16 | Generic AI transparency dashboard | 55 | Drop; broad and platform-embedded |
| 17 | Generic vendor privacy/security monitor | 52 | Drop; crowded |
| 18 | SaaS contract renewal extractor | 49 | Drop; mature category |

## Stage 3 shortlist

1. Chrome extension privacy/disclosure vs manifest preflight
2. Atlassian Marketplace pre-submission trust/security checker
3. Chrome extension permission-change release preflight
4. Atlassian Forge egress/data-residency configuration audit
5. AI-generated content label coverage checker

## Verification record

- Last verified: 2026-10-19
- Stage 2 status: complete
- Stage 5: out of scope
