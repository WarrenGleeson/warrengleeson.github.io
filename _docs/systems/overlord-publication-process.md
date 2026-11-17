---
title: Overlord Publication Process
summary: Documented Overlord lifecycle from owner request through bounded execution, checked publication, owner approval, exact-head merge, and reconciliation.
section: systems
doc_type: system
status: active
created: 2026-11-16
updated: 2026-11-17
last_verified: 2026-11-16
repository: Overlord
system: Overlord
---

# Overlord Publication Process

> **Evidence boundary:** This page summarizes the current Overlord records in this documentation checkout. The Overlord source tree, live host, GitHub state, and runtime logs are not present here, so the implementation and operational claims remain unverified independently. See [Overlord Evidence Gaps and Blind Spots](../notes/overlord-blind-spots.md).

Overlord starts with a bounded request from the owner. The documented lifecycle is:

1. The Manager plans the work and records canonical planning state.
2. A Developer agent implements the work in a disposable workspace.
3. The result is validated before publication.
4. Overlord publishes the change and opens a pull request.
5. The exact pull-request head and required checks are observed. Missing, stale, failed, or mismatched evidence fails closed.
6. The owner gives the canonical merge approval.
7. Approval is rechecked before and during the durable merge workflow, followed by a fresh merge evaluation.
8. The GitHub broker performs the exact-head squash merge.
9. Overlord reconciles repository delivery state and only then completes the task and any dependent planning state.

The simplified rule is therefore not “checks pass, then automatic merge”: checks permit evaluation, but owner approval and exact-head gates remain required before mutation. PostgreSQL is documented as canonical application state, while DBOS provides workflow coordination rather than the canonical task or delivery record.

The detailed operational record is [Overlord Phase 4 — Live MVP Host](../notes/overlord-phase-4-live-host.md).

## Verification record

- Documented source: Overlord phase and deployment records in this site checkout.
- Independently unverified: source implementation, current deployed release, live GitHub checks/approval, host state, and reconciliation logs.
