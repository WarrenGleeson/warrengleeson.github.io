---
title: Revenue Investigation — Wave 13 Stage 2 Viability Filter
summary: Evidence-based filtering of Wave 13 ideas across Gmail retirement readiness, EU Data Act portability, software provenance, cloud-cost operations and vendor lifecycle administration.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 262
permalink: /projects/notes/revenue-investigation-wave-13-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-13, viability]
---

# Wave 13 Stage 2 — Viability Filter

## Evidence that changed scoring

- Gmail will fully remove third-party `Send as`, Gmailify and POP support in January 2027. That creates a near-term migration-readiness problem for users and small organizations relying on Gmail as a multi-account front end.
- The EU Data Act removes switching charges, including data-egress charges required for switching, from 12 January 2027 and requires SaaS/PaaS providers to make data portable through open interfaces or commonly used machine-readable formats.
- GitHub now provides built-in artifact attestations and attestation management, while npm supports OIDC trusted publishing and provenance. Generic provenance/SBOM coverage tooling therefore has substantial native-platform competition.
- AWS now provides AI-assisted cost anomaly investigations at no additional charge and extensive cost-efficiency tooling, weakening generic cloud-cost anomaly products.
- Vendor lifecycle/EOL tracking is a crowded broad category, but mapping vendor lifecycle events to a team's declared workflow/software dependencies remains more differentiated.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Gmail third-party account retirement readiness workspace | 80 | Advance |
| 2 | EU Data Act SaaS exit/export readiness checker | 79 | Advance |
| 3 | Vendor feature/EOL dependency impact inventory | 76 | Advance |
| 4 | SaaS export-format completeness audit | 75 | Advance |
| 5 | Gmail SMTP/IMAP replacement-path planner | 74 | Merge into #1 |
| 6 | SaaS exit-plan dependency inventory | 73 | Merge into #2 |
| 7 | npm trusted-publishing readiness scanner | 70 | Advance cautiously |
| 8 | GitHub attestation coverage checker | 68 | Hold; native tooling strong |
| 9 | Release asset vs attestation mismatch checker | 67 | Hold |
| 10 | SaaS/API support-window inventory | 66 | Hold |
| 11 | Vendor migration-guide-to-task mapper | 65 | Hold |
| 12 | Cloud-tagging vs cost allocation audit | 64 | Hold; established FinOps tooling |
| 13 | AI token-cost allocation mapper | 63 | Hold; rapidly commoditizing |
| 14 | Marketplace policy-to-SKU impact mapper | 61 | Hold; platform-specific maintenance high |
| 15 | Generic seller fee-impact calculator | 58 | Drop; commodity |
| 16 | AWS cost anomaly workflow | 54 | Drop; native AWS tooling strong |
| 17 | Generic provenance dashboard | 52 | Drop; GitHub/npm native support |
| 18 | Software portfolio EOL calendar | 50 | Drop; crowded |

## Stage 3 shortlist

1. Gmail third-party account retirement readiness workspace
2. EU Data Act SaaS exit/export readiness checker
3. Vendor feature/EOL dependency impact inventory
4. SaaS export-format completeness audit
5. npm trusted-publishing readiness scanner

## Verification record

- Last verified: 2026-10-19
- Stage 2 status: complete
- Stage 5: out of scope
