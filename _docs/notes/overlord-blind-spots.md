---
title: Overlord Evidence Gaps and Blind Spots
summary: Evidence that remains unavailable after the Overlord source and sanitized live snapshot audit.
section: notes
doc_type: reference
status: active
owner: High Director
created: 2026-11-17
updated: 2026-11-17
repository: Overlord
permalink: /projects/notes/overlord-blind-spots/
tags:
  - overlord
  - evidence
  - verification
  - blind-spots
---

# Overlord Evidence Gaps and Blind Spots

## Audit Boundary

The audit inspected `/context/README.txt`, the Overlord source export at `/context/overlord` (commit `b049dac6be756cd8c30f5f3b0bb76ff61f9d24f5`), and the sanitized live snapshot at `/context/overlord-live-snapshot` (captured `2026-11-17T20:28:47Z`, snapshot revision `d88028445ebcd3cd6ea2cbd77afdd9187ee82b3f`). No files under `/context` were modified.

The source and snapshot resolve the former broad blind spots: the application structure, migrations, ports/adapters, DBOS workflow code, local Docker/OpenCode execution, GitHub broker and App adapter, deployed release, service state, database schema, Docker state, network listeners, and current runtime settings are now inspectable. Claims below are only the gaps that remain.

## Remaining Blind Spots

| Remaining blind spot | What the available evidence establishes | Exactly what is still needed |
| --- | --- | --- |
| Effective AWS IAM permissions and least-privilege proof | Source uses `SecretStorePort` and the snapshot shows the configured AWS region and GitHub App secret name: `/context/overlord/docs/security-boundaries.md`, `/context/overlord-live-snapshot/snapshot/settings.env`. | A sanitized IAM role/policy attachment and a dated successful/denied least-privilege access test from the production identity, without secret values. |
| Monitoring, alerting, backups, restore, and rollback readiness | The snapshot proves current service health, migrations, and recent restart/health logs: `/context/overlord-live-snapshot/snapshot/service.txt`, `journal-tail.txt`, `database.txt`. | Sanitized alert/metric configuration, backup schedule and retention, a successful dated restore test, and a rollback rehearsal or equivalent deployment evidence. |
| Provider billing and authoritative request/cost totals | Runtime settings, logs, and benchmark artifacts expose reported usage but do not prove provider billing. The source explicitly treats reported cost as non-authoritative: `/context/overlord/docs/architecture.md`, `/context/overlord-live-snapshot/snapshot/settings.env`. | Provider-side usage/billing export for the relevant time window, with request IDs or gateway evidence mapped to the runs and account/project configuration. |
| Reproducibility of historical benchmark aggregates | The source contains benchmark harnesses and validators, and site notes report accepted results, but the complete raw artifact bundle is not mounted: `/context/overlord/benchmarks/developer/`, `/context/overlord/docs/developer-replay-harness.md`. | The frozen raw trial/replay artifacts, exact evaluator revision and runtime configuration, and rerun logs that reproduce each published aggregate. |
| External authenticated API behavior | The snapshot shows Caddy on ports 80/443 proxying to loopback Uvicorn and `OVERLORD_OWNER_API_AUTH_ENABLED=1`: `/context/overlord-live-snapshot/snapshot/network.txt`, `settings.env`. | The active ingress/TLS policy and a sanitized external authenticated request/response test, including the unauthenticated denial behavior. |
| Provider-side model/account configuration beyond redacted runtime settings | The snapshot establishes configured provider/model identifiers, but secret values and provider-console state are intentionally redacted: `/context/overlord-live-snapshot/snapshot/settings.env`. | A sanitized provider project/model configuration and request-policy record, plus provider-side usage evidence; never provide credentials or secret values. |

## Resolved During This Audit

- Current source revision, migrations, schemas, dependencies, and application boundaries: `/context/overlord/pyproject.toml`, `uv.lock`, `migrations/`, `src/`, and `docs/`.
- Current production release, host identity, service status, health/readiness, Docker image/container state, database schema, and network exposure: `/context/overlord-live-snapshot/snapshot/summary.txt`, `service.txt`, `docker.txt`, `database.txt`, `network.txt`, and `droplet.json`.
- Routine publication workflow and merge ownership: `/context/overlord/src/overlord/application/work_request_dispatch.py` automatically calls merge after eligible checks; `/context/overlord/src/overlord/adapters/workflow/dbos_developer_github_publication.py` explicitly says routine merges do not require per-task owner sign-off. The owner-approval acceptance workflow is a separate controlled scenario: `/context/overlord/deploy/accept-production-manager-delivery-approval.py`.
- Current source/deployed-release identity drift: both report `b049dac6be756cd8c30f5f3b0bb76ff61f9d24f5` in `/context/overlord-live-snapshot/snapshot/summary.txt`.

## Maintenance Rule

Do not restore resolved broad blind spots merely because older site notes predate the mounted evidence. Keep historical claims dated, cite source paths or snapshot files for current claims, and label claims unverifiable when the exact evidence listed above is not supplied.

## Verification Record

- Last audited: `2026-11-17`.
- Evidence inspected: `/context/README.txt`, `/context/overlord`, `/context/overlord-live-snapshot`, all Overlord site pages, repository navigation/configuration, and the documentation validator.
- Verified by: documentation audit of the current checkout.
