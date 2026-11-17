---
title: Overlord Repository and Control-Plane System
summary: Audited documentation record for Overlord's application, durable workflow, local-container Developer execution, GitHub delivery, and single-host deployment boundaries.
section: repositories
doc_type: repository
status: active
owner: High Director
created: 2026-08-07
updated: 2026-11-17
repository: Overlord
---

# Overlord Repository and Control-Plane System

> **Evidence boundary:** This page was audited against `/context/overlord` at commit `b049dac6be756cd8c30f5f3b0bb76ff61f9d24f5` and `/context/overlord-live-snapshot` captured at `2026-11-17T20:28:47Z`. Claims without source or snapshot evidence remain marked as unverifiable.

## Purpose

Overlord is an owner-controlled control plane that plans work, runs bounded Developer tasks, publishes repository changes, and records durable state. PostgreSQL is canonical application state; DBOS is workflow coordination; Developer execution uses disposable local Docker containers and OpenCode; GitHub mutation is brokered and audited; and production runs as a single host. Evidence: `/context/overlord/docs/architecture.md`, `/context/overlord/docs/production-live-host.md`, `/context/overlord/src/overlord/application/github_broker.py`, `/context/overlord-live-snapshot/snapshot/service.txt`, `docker.txt`, and `database.txt`.

The source and live snapshot establish the implementation and observed deployment state at the cited revisions. They do not establish provider billing, backup/restore readiness, or every historical benchmark result; those remain on the blind-spots page.

## Repository maturity

The documented maturity is beyond the earlier Markdown-only snapshot:

- Phase 0 records describe a Python application, domain persistence, provider-neutral planning contracts, and a DBOS durable Manager workflow.
- Phase 1 records describe a local Manager loop and API boundary.
- Phase 2 records describe bounded Developer execution, recovery, and benchmark infrastructure.
- Phase 3 records describe GitHub policy/audit boundaries and a GitHub App plus AWS Secrets Manager adapter.
- Phase 4 records describe local Docker developer environments and a single DigitalOcean host.

The earlier Markdown/task-record material is retained below as a dated legacy snapshot. It is not the current implementation authority.

## Documented current boundaries

The related records describe these boundaries:

- PostgreSQL is canonical application state for work requests, plans, tasks, decisions, agent runs, deliveries, and audit records.
- DBOS coordinates durable workflows and checkpoints; it is not canonical domain state.
- Developer execution occurs in disposable local Docker containers through OpenCode and a configured model provider.
- GitHub mutation is constrained to the GitHub port/broker/adapter path and is durably audited.
- Production is described as a single host; remote workers and distributed infrastructure remain deferred.

Evidence: `/context/overlord/docs/architecture.md`, `/context/overlord/docs/security-boundaries.md`, `/context/overlord/docs/production-live-host.md`, `/context/overlord-live-snapshot/snapshot/settings.env`, `service.txt`, `network.txt`, and `docker.txt`.

## Legacy Markdown snapshot

The 2026-08-07 repository snapshot documented a README, work/personal task directories, eight `test-task-*` fixtures, and three Markdown templates. It also correctly recorded that those files had no verified executable behavior at that time. The snapshot is preserved in [the legacy template reference](../notes/overlord-versioned-task-project-meeting-templates.md), but it must not be used as the current repository description.

## Legacy work/personal partition

Task records are partitioned by directory:

- `tasks/work/` — work-context task records;
- `tasks/personal/` — personal-context task records.

Observed work fixtures also contain front matter `context: "work"`, so directory and metadata currently reinforce the same classification.

No code enforces consistency between directory and `context`; the convention is manual.

## Legacy record format

Observed fixture records use YAML front matter followed by five Markdown sections.

### Legacy front matter

Observed fields:

| Field | Observed role |
| --- | --- |
| `title` | Human-readable record title. |
| `slug` | Filename/identifier-style slug. |
| `context` | Observed partition/context value such as `work`. |
| `template_type` | Record/template class; fixtures use `task`. |
| `template_version` | Version identifier; fixtures use `v1`. |
| `status` | Lifecycle/status label. |
| `created_at` | Creation timestamp. |
| `updated_at` | Last-updated timestamp. |

The repository does not contain a formal schema definition or parser that proves these fields are mandatory, typed, unique, or validated.

### Legacy body sections

Observed records contain:

1. `## Overview`
2. `## Notes`
3. `## Next Actions`
4. `## Open Questions`
5. `## Changelog`

Fixtures typically fill empty-content sections with text such as `No information currently` and add a creation entry under `Changelog`.

## Legacy status/lifecycle conventions

Observed fixture statuses include:

- `active`;
- `done`.

For example, `test-task-1.md` is `active`, while `test-task-8.md` is `done`.

These are observed values only. No repository source defines:

- an allowed status vocabulary;
- status transitions;
- automatic completion rules;
- reopening behavior;
- archival rules;
- validation that status and content agree.

Do not describe `active -> done` as an enforced state machine. It is only an observed manual convention.

## Legacy timestamp conventions

Fixtures use ISO-8601-like timestamps, but formatting is not fully normalized:

- some values are quoted strings;
- at least one observed `updated_at` is unquoted YAML;
- timezone offsets vary, including `+00:00` and `-07:00`.

No formatter or validator enforces one canonical timestamp representation.

## Legacy slug/filename convention

Observed examples align filename and `slug`, such as:

- file: `tasks/work/test-task-1.md`;
- front matter: `slug: "test-task-1"`.

This appears to be a convention rather than an enforced invariant. No code checks filename/slug equivalence or uniqueness.

## Legacy template metadata relationship

Fixture records include:

- `template_type: "task"`;
- `template_version: "v1"`.

The repository also contains `templates/tasks/task_v1.md`, which establishes a plausible provenance convention between records and template files.

However, the current template files contain only Markdown body headings; they do not include front matter, and no generator links a record automatically to a template. Template metadata is therefore manually maintained.

## Legacy manual record lifecycle

Based strictly on repository evidence, the practical lifecycle is manual:

1. choose a work/personal directory;
2. create a Markdown record;
3. populate front matter fields;
4. use the standard body headings;
5. update content/status/timestamps manually;
6. append changelog entries manually as desired.

No repository process automates these steps.

## Legacy fixtures and examples

`tasks/work/test-task-1.md` through `test-task-8.md` provided evidence of the snapshot record shape and formatting variability.

They should be treated as legacy examples/fixtures, not current production subsystems. Their placeholder content also means they are poor evidence for rich business-process semantics beyond the record format itself.

## Dependencies and verification boundary

The related records name Python dependencies, PostgreSQL, DBOS, Docker, OpenCode, provider APIs, GitHub, AWS Secrets Manager, and DigitalOcean. None of those dependencies or their configured versions can be verified from this site checkout. The exact source tree, lockfiles, tests, CI runs, deployment release, host state, effective cloud permissions, provider billing, and current runtime configuration are listed as blind spots rather than inferred.

## Legacy security and data considerations

The snapshot repository structure allowed personal-context records under `tasks/personal/`, but that directory was empty in the inspected snapshot.

Because that snapshot was a Git repository, its committed record content was repository data. The snapshot source did not implement:

- field-level access control;
- encryption;
- secret scanning specific to task fields;
- privacy labels;
- personal/work access separation beyond directory naming.

Do not infer privacy or access controls from the `personal` directory name.

## Legacy failure modes

Within the snapshot, failure modes were primarily data-quality/manual-maintenance issues:

- malformed YAML front matter;
- missing expected metadata fields;
- filename/slug mismatch;
- inconsistent `context` and directory partition;
- unsupported/unexpected status strings;
- stale `updated_at` timestamps;
- changelog not updated with record changes;
- body sections omitted or renamed;
- template metadata not matching the skeleton actually used;
- formatting drift between records;
- accidental storage of information unsuitable for the repository's access model.

No automated validator in that snapshot detected these issues.

## Current limitations and open evidence

- This site checkout is not the Overlord source repository; current source evidence is mounted separately under `/context/overlord`.
- The old Markdown/task-record page and template details are historical, not current application authority.
- Monitoring configuration, backup retention, restore testing, rollback readiness, and effective AWS IAM permissions are not established by the available source export and snapshot.
- Provider-side billing and request totals are not established by the snapshot.
- Benchmark artifacts, provider billing, and reproducibility of reported runs are not verifiable here.
- A public Caddy reverse proxy is visible and owner API authentication is enabled in the snapshot, but an authenticated external request/response and complete ingress policy are not available.

## Related documentation

- [Overlord Publication Process](../systems/overlord-publication-process.md)
- [Overlord Versioned Task, Project, and Meeting Templates](../notes/overlord-versioned-task-project-meeting-templates.md)
- [Overlord Evidence Gaps and Blind Spots](../notes/overlord-blind-spots.md)
- [Overlord Documentation Workstream Plan](../high-director/overlord-documentation-workstream-plan.md)
- [Repository Scan: Overlord](../high-director/repository-scan-overlord.md)
- [Documentation Target Catalogue](/projects/high-director/documentation-target-catalogue/)

## Continuation

Maintain this page as the current site-level summary of the documented Overlord boundaries, while keeping independently unverifiable claims explicitly marked. Update it from the mounted Overlord source and live evidence when those revisions change; do not restore the old Markdown-only description.
