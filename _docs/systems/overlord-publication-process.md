---
title: Overlord Publication Process
summary: Current Overlord lifecycle from owner request through bounded execution, checked publication, automatic exact-head merge, and reconciliation, with owner decisions only for blocked or specially protected work.
section: systems
doc_type: system
status: active
created: 2026-11-16
updated: 2026-11-17
last_verified: 2026-11-17
repository: Overlord
system: Overlord
---

# Overlord Publication Process

> **Evidence boundary:** This page was audited against the read-only Overlord source at `/context/overlord` and the sanitized live snapshot at `/context/overlord-live-snapshot`. Source citations below identify implementation evidence; snapshot citations identify observed production state.

Overlord starts with a bounded request from the owner. The documented lifecycle is:

1. The Manager plans the work and records canonical planning state.
2. A Developer agent implements the work in a disposable workspace.
3. The result is validated before publication.
4. Overlord publishes the change and opens a pull request.
5. The exact pull-request head and required checks are observed. Missing, stale, failed, or mismatched evidence fails closed.
6. Once the merge evaluation is eligible, the automatic dispatcher starts the durable exact-head merge workflow; routine merges do not require per-task owner approval.
7. The GitHub broker performs the exact-head squash merge.
8. Overlord reconciles repository delivery state and only then completes the task and any dependent planning state.

The implementation rule is: checks and exact-head/mergeability gates pass, then the dispatcher merges automatically through the broker. Owner decisions still stop blocked work, and the separate approval endpoint is an explicit acceptance/control path rather than a routine merge prerequisite. PostgreSQL is canonical application state, while DBOS provides workflow coordination rather than the canonical task or delivery record. Evidence: `/context/overlord/src/overlord/application/work_request_dispatch.py`, `/context/overlord/src/overlord/adapters/workflow/dbos_developer_github_publication.py`, `/context/overlord/src/overlord/application/developer_github_merge.py`, and `/context/overlord/src/overlord/application/github_broker.py`.

The detailed operational record is [Overlord Phase 4 — Live MVP Host](../notes/overlord-phase-4-live-host.md).

## Current Evidence

- Production source revision and deployed release: `b049dac6be756cd8c30f5f3b0bb76ff61f9d24f5`, `/context/overlord-live-snapshot/snapshot/summary.txt`.
- Production service is active and `/health` plus `/ready` returned success: `/context/overlord-live-snapshot/snapshot/service.txt` and `journal-tail.txt`.
- Production merge policy is the `quality` check for Overlord's own repository: `/context/overlord/src/overlord/config/settings.py` and `/context/overlord/deploy/accept-production-developer-merge.py`.

## Verification record

- Inspected source: `/context/overlord/src/overlord/application/work_request_dispatch.py`, `/context/overlord/src/overlord/application/developer_github_merge.py`, `/context/overlord/src/overlord/application/github_broker.py`, and `/context/overlord/src/overlord/adapters/workflow/dbos_developer_github_publication.py`.
- Inspected live evidence: `/context/overlord-live-snapshot/snapshot/summary.txt`, `service.txt`, `journal-tail.txt`, `settings.env`, and `network.txt`.
- Not established by available evidence: provider billing, backup/restore testing, and a fresh external live merge beyond the acceptance records in source.
