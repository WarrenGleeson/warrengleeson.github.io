---
title: Overlord Evidence Gaps and Blind Spots
summary: Evidence boundary, stale claims, and exact material required to verify the current Overlord documentation.
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

## Scope and evidence boundary

This checkout is `warrengleeson.github.io`, the documentation site. It does not contain a separate Overlord source checkout, submodule, live host access, AWS account access, GitHub repository state, CI artifacts, runtime logs, or benchmark artifact bundle.

The Overlord pages can therefore establish that these claims are recorded in the site, and can compare records with one another. They cannot independently prove the implementation or current operational state described by those records. This page is the required boundary for claims that remain unknown or unverified.

## Claims that remain unverifiable

Each item below needs the listed evidence. The absence of that evidence is why the claim remains unverified; it is not evidence that the capability is absent.

| Unverifiable item | Why it could not be verified | Exact evidence needed |
| --- | --- | --- |
| Current Overlord source tree, branch, and commit | No Overlord checkout is present here | A read-only source export or repository checkout, including the exact commit SHA and branch/ref |
| Application structure, dependencies, schemas, and configuration | The site contains implementation records but no source, lockfiles, migrations, or config files | Source tree, dependency/lock files, migration history, sanitized configuration, and the source commit that was deployed |
| Manager planning, DBOS durability, and canonical state ownership | These are described in phase notes only | Relevant application modules, database schema/migration output, focused tests, and CI artifacts tied to an immutable source SHA |
| Developer container, OpenCode, provider routing, and credential isolation | No container definitions, runtime process, or execution logs are available | Container/image definitions, sanitized runtime configuration, execution logs, network policy evidence, and an observable test run |
| GitHub broker, App, merge gates, approvals, and audit persistence | No GitHub repository state, App installation, check results, approval records, or audit logs are accessible | Source at the deployed SHA, repository branch/ruleset configuration, sanitized App installation/policy evidence, exact-head check and approval records, and audit log entries |
| AWS Secrets Manager and IAM boundary | Secret names in notes do not prove live secret existence or effective permissions | Sanitized AWS account/region evidence, secret metadata without values, attached IAM policy/role evidence, and a successful least-privilege read audit |
| DigitalOcean host, deployed release, services, and network exposure | No host, provider console, SSH session, service status, or deployment log is available | Host inventory, immutable deployed SHA/image digest, service/container status, firewall/listening-socket output, deployment log, and rollback evidence |
| Production health, monitoring, backups, restore, and recovery | No live logs, metrics, alert configuration, backup records, or restore test exists in this checkout | Sanitized monitoring/alert configuration, recent health/log evidence, backup schedule and retention, and a dated restore/recovery test |
| Benchmark harness, corpus, results, model selection, and reproducibility | The notes contain reported results but no corpus/artifact bundle or independently rerunnable environment | Frozen corpus and fingerprints, validator and harness source, raw prompt-free result artifacts, exact source/runtime/model versions, and reproducible rerun logs |
| Provider billing, request counts, and actual cost | Runtime-reported cost is not provider billing, and no provider account evidence is available | Provider-side usage/billing export, request identifiers mapped to the run, gateway evidence, and the applicable account/project configuration |
| Public API exposure and authentication | No deployed endpoint, ingress configuration, or live request can be observed | Route/source configuration, host ingress/firewall evidence, authentication policy, and a sanitized live request/response check |
| Current production drift from repository `main` | The notes report SHAs, but the deployed artifact and current source cannot be inspected here | Current repository ref, deployment manifest/image digest, host artifact checksum, and deployment/reconciliation log |

## Known stale or conflicting material

- The active repository page previously described Overlord as only a Markdown task-record store. Later site records describe an application and deployment, so that description is now retained only as a dated legacy snapshot.
- The template page previously presented the old v1 files as current. It is now explicitly historical; the current status of those files cannot be checked here.
- The publication page previously implied that passing checks caused an automatic merge. Later records add owner approval, exact-head checks, fail-closed evaluation, rechecks, and reconciliation.
- Phase and benchmark notes are internally dated records, not independently verified source or live evidence. Their claims remain unverified unless the evidence listed above is obtained.
- Repository `main`, deployed release, and benchmark source revisions are reported separately in the records. They must not be treated as interchangeable without deployment evidence.

## Evidence required to complete the audit

The minimum coherent verification package is:

1. An immutable Overlord source export with its commit SHA and the relevant deployment/source refs.
2. Sanitized CI, test, migration, deployment, and runtime logs tied to those SHAs.
3. Sanitized host, Docker, ingress, monitoring, backup, and restore evidence for the deployed environment.
4. Sanitized GitHub App, repository policy, exact-head check, approval, merge, and audit evidence.
5. Sanitized AWS IAM/Secrets Manager evidence showing effective access without exposing secret values.
6. Frozen benchmark corpus, raw prompt-free artifacts, rerun output, provider usage/billing evidence, and model/runtime versions.

## Maintenance rule

Do not promote a claim to verified current from a site note alone. Keep historical snapshots dated, preserve explicit source/runtime boundaries, and update the repository summary only when the required source or observable operational evidence is available.

## Verification record

- Last audited: `2026-11-17`.
- Evidence inspected: this documentation-site checkout, its Overlord pages, repository-local navigation/configuration, and the repository documentation validator.
- Evidence unavailable: Overlord source, live deployment, cloud configuration, CI artifacts, runtime logs, benchmark artifacts, and provider billing.
- Verified by: documentation audit of the current checkout.
