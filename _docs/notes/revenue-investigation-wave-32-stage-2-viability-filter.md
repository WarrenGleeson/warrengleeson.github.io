---
title: Revenue Investigation — Wave 32 Stage 2 Viability Filter
summary: Viability filtering for GitHub Marketplace app ideas, prioritizing repository and configuration lifecycle preflights over crowded security/CI categories.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 338
permalink: /projects/notes/revenue-investigation-wave-32-stage-2-viability-filter/
tags: [revenue-investigation, research, wave-32, github, viability]
---

# Wave 32 Stage 2 — Viability Filter

## Evidence that changed scoring

- Paid GitHub Marketplace plans are for GitHub Apps; Actions can be listed but do not use the same native paid-plan model.
- Paid GitHub Apps require verified-publisher status and at least 100 installations before paid plans can be published, so free-first utility is important.
- GitHub retains 5% of Marketplace revenue for post-2021 transactions.
- Code review, dependency/security scanning, workflow security, ruleset drift and required-check drift already have strong current competition.
- GitHub's own repository rename behavior creates specific breakage: repository web/git URLs redirect, but actions hosted in renamed repositories do not redirect and GitHub Pages URLs can be affected. That makes rename/transfer preflight a concrete lifecycle niche.
- Environment, secret/variable names and self-hosted runner labels are referenced in workflow YAML, making deterministic read-only dependency scanning feasible without handling secret values.

## Candidate ranking

| Rank | Idea | Score /100 | Decision |
|---|---|---:|---|
| 1 | Repository rename / transfer dependency preflight | 83 | Advance |
| 2 | Actions environment retirement dependency preflight | 80 | Advance |
| 3 | Actions secret / variable name retirement usage scanner | 78 | Advance |
| 4 | Self-hosted runner-label retirement preflight | 75 | Advance cautiously |
| 5 | Reusable-workflow caller impact scanner | 74 | Advance cautiously |
| 6 | Team rename / CODEOWNERS continuity audit | 72 | Hold |
| 7 | Required-check retirement preflight | 65 | Hold; direct drift tools emerging |
| 8 | Workflow security / permissions audit | 52 | Drop; crowded |
| 9 | Vendor runtime/deprecation scanner | 50 | Drop; exact current competitor |
| 10 | Generic ruleset/config drift | 47 | Drop; direct current tools |
| 11 | Secret scanning | 42 | Drop; extremely crowded/native |

## Stage 3 shortlist

1. Repository rename / transfer dependency preflight
2. Actions environment retirement dependency preflight
3. Actions secret / variable name retirement usage scanner

## Verification record
- Last verified: 2026-10-25
- Stage 2 status: complete
- Stage 5: out of scope
