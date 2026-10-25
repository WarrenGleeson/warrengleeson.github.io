---
title: Revenue Investigation — Wave 29 Stage 2 Viability Filter
summary: Viability filtering for Atlassian Marketplace Forge app ideas, prioritizing narrow change-risk utilities over crowded admin-tool categories.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 326
permalink: /projects/notes/revenue-investigation-wave-29-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-29, atlassian, forge]
---

# Wave 29 Stage 2 — Viability Filter

## Evidence that changed scoring

- Atlassian Marketplace is highly mature: permission audits, custom-field cleanup, filter/dashboard hygiene, automation dependency mapping, workflow linting, release readiness, stale Confluence content, broken links and JSM project-standard drift all have current products.
- Forge's read APIs create hard boundaries. Automation rules, some JSM settings and private objects cannot always be inspected; ideas that depend on full configuration visibility are downgraded.
- The less crowded space is change-risk analysis: detecting downstream dependencies before an admin retires an object/project/request type, or when Atlassian announces a platform/JQL behavior change.
- Read-only Forge apps with no data egress fit this model well and reduce support/security burden.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Jira project archive/delete dependency preflight | 80 | Advance |
| 2 | Atlassian/JQL platform-change impact scanner | 78 | Advance |
| 3 | JSM request-type retirement dependency preflight | 76 | Advance |
| 4 | Jira plan-downgrade dependency inventory | 72 | Advance cautiously; API feasibility risk |
| 5 | Jira resolution/status hygiene audit | 68 | Hold; adjacent resolution-compliance apps |
| 6 | Marketplace-app uninstall dependency preflight | 67 | Hold; API visibility incomplete |
| 7 | Confluence required-section/template audit | 64 | Hold; content-quality competition |
| 8 | JSM knowledge coverage audit | 60 | Drop; direct current competitor |
| 9 | Jira permission/access audit | 48 | Drop; heavily crowded |
| 10 | Jira custom-field cleanup | 45 | Drop; heavily crowded |
| 11 | Automation dependency/cost map | 44 | Drop; exact current competitors |
| 12 | Workflow linter | 43 | Drop; exact current competitor |
| 13 | Release readiness | 42 | Drop; exact current competitor |
| 14 | Confluence macro usage | 41 | Drop; exact current competitor |

## Stage 3 shortlist

1. Jira project archive/delete dependency preflight
2. Atlassian/JQL platform-change impact scanner
3. JSM request-type retirement dependency preflight

## Verification record
- Last verified: 2026-10-25
- Stage 2 status: complete
- Stage 5: out of scope
