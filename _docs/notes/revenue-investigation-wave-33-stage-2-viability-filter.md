---
title: Revenue Investigation — Wave 33 Stage 2 Viability Filter
summary: Viability filtering for Salesforce AgentExchange/AppExchange ideas, prioritizing platform-change migration readiness and routing lifecycle over crowded metadata/admin categories.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 342
permalink: /projects/notes/revenue-investigation-wave-33-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-33, salesforce, viability]
---

# Wave 33 Stage 2 — Viability Filter

## Evidence that changed scoring

- Salesforce's current ISVforce model supports AgentExchange/AppExchange checkout with 15% revenue share, but paid apps also carry security-review/listing overhead. This favors higher-value admin utilities rather than very small micro-apps.
- Broad metadata impact analysis, field cleanup, permission audits and technical-debt cleanup are already mature, including Elements.cloud and newer specialized apps.
- Salesforce restricted creation of new Connected Apps in Spring '26 and is steering customers toward External Client Apps. Existing Connected Apps continue to work, but Salesforce is recommending inventory and migration preparation ahead of future end-of-support.
- Salesforce already publishes free AgentExchange skills for configuring Connected Apps/ECAs, so a viable paid product must focus on org-wide inventory, migration readiness and evidence—not configuration tutorials.
- Legacy Named Credentials are deprecated and are documented as unsupported in future releases; current AgentExchange skills help create modern Named/External Credentials but do not replace a cross-org migration/readiness audit.
- Standard Omni-Channel reached end of life in Summer '26. Queue/routing configuration remains operationally important in Enhanced Omni-Channel, creating an evergreen queue/routing retirement-preflight niche rather than a broad migration product.
- User deactivation and permission analysis already have free/direct apps, so generic integration-user cleanup is downgraded.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Connected App -> External Client App migration readiness audit | 82 | Advance |
| 2 | Legacy Named Credential migration readiness audit | 80 | Advance |
| 3 | Queue / routing retirement dependency preflight | 77 | Advance |
| 4 | Agentforce action retirement dependency preflight | 73 | Advance cautiously; emerging native skills |
| 5 | Integration-user retirement dependency audit | 68 | Hold; user-deactivation apps overlap |
| 6 | Enhanced Omni post-migration gap audit | 67 | Hold; deadline has passed |
| 7 | Permission-set cleanup/audit | 52 | Drop; heavily crowded/native |
| 8 | Field/picklist cleanup | 49 | Drop; direct current competitors |
| 9 | Generic metadata dependency analysis | 45 | Drop; mature market |
| 10 | User deactivation | 44 | Drop; exact free competitor |

## Stage 3 shortlist

1. Connected App -> External Client App migration readiness audit
2. Legacy Named Credential migration readiness audit
3. Queue / routing retirement dependency preflight

## Verification record
- Last verified: 2026-10-25
- Stage 2 status: complete
- Stage 5: out of scope
