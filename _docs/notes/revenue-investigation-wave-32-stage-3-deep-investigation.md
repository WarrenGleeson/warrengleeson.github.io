---
title: Revenue Investigation — Wave 32 Stage 3 Deep Investigation
summary: Deep investigation of the strongest GitHub Marketplace app opportunities after direct competitor checks.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 339
permalink: /projects/notes/revenue-investigation-wave-32-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-32, github, marketplace]
---

# Wave 32 Stage 3 — Deep Investigation

## 1. Repository rename / transfer dependency preflight

### Problem
GitHub redirects most repository URLs after a rename, but important exceptions remain. GitHub documents that actions hosted in a renamed repository do not redirect and can break consuming workflows. GitHub Pages project-site URLs can also be affected, and external references such as badges, submodules, package metadata, deployment configs and documentation may retain the old owner/repository slug.

### Product
Install the GitHub App on an organization or selected repositories, choose a repository, and scan for references to its current owner/name across accessible repos and configuration:
- `uses: owner/repo@...` GitHub Actions references;
- reusable workflow references;
- git submodule URLs;
- repository URLs in README/docs/config files;
- badges and release/download links;
- GitHub Pages project-site references;
- package/source metadata where detectable;
- webhook/integration destinations that expose repository slugs;
- exact unsupported/external dependency classes listed separately.

For transfers, also report references to the old owner plus organization/team assumptions that need review.

The app never renames or transfers a repository automatically.

### Distribution
GitHub Marketplace search around repository rename, repository transfer, migration, organization rename and GitHub Actions breakage.

### Monetization hypothesis
Free single-repository scan to drive installs toward the 100-install paid threshold; paid organization-wide scans, historical snapshots, exports and multi-repository migration batches.

### Competition
GitHub documents rename caveats, but current Marketplace review did not surface a focused App that performs a cross-repository rename/transfer blast-radius scan.

### Risk
External references outside installed repositories cannot be discovered reliably. Output must distinguish inspected GitHub scope from external unknowns.

### Verdict
**Advance.** Strongest Wave 32 candidate.

---

## 2. Actions environment retirement dependency preflight

### Problem
GitHub Actions environments are often referenced indirectly across deployment workflows. Before deleting or renaming an environment such as `production`, an admin needs to know which workflows use it, which environment-level variables/secrets/protection rules are attached, and whether reusable workflows or deployment jobs will fail after the change.

### Product
Select an environment and generate a read-only dependency report:
- workflows/jobs declaring `environment:` with the selected name;
- environment URLs where defined;
- environment variables/secrets by **name only**, never value;
- protection/reviewer configuration exposed by GitHub APIs;
- recent deployments to the environment;
- reusable workflow callers that pass or construct the environment name where statically detectable;
- literal vs dynamic environment references separated by confidence;
- rename/delete migration checklist.

No environment, secret, or workflow is changed automatically.

### Distribution
Marketplace search around GitHub environment cleanup, production environment rename, deployment migration and Actions administration.

### Monetization hypothesis
Free one-environment scan; paid org-wide environment inventory, dependency history and batch retirement reports.

### Competition
General repository-settings management and drift tools exist, but current research did not identify a focused Marketplace App centered on **environment retirement impact**.

### Risk
Dynamic expressions can make environment names impossible to resolve statically. The app must show definite vs possible references.

### Verdict
**Advance.** Clear, deterministic admin job with low data sensitivity.

---

## 3. Actions secret / variable name retirement usage scanner

### Problem
GitHub does not expose secret values, but teams can safely enumerate secret names and repository contents. When retiring or renaming a secret/variable such as `AWS_ROLE_ARN`, admins need to know which workflows, reusable workflows, composite actions and scripts still reference that name before deleting it.

### Product
Select or enter an Actions secret/variable name and scan accessible repositories for references:
- `${{ secrets.NAME }}` and `${{ vars.NAME }}`;
- environment-level secret/variable scopes where names are exposed;
- reusable workflow secret declarations and inheritance patterns;
- composite actions and shell scripts referencing mapped environment variables;
- organization secret selected-repository scope;
- exact vs inferred references;
- migration checklist for rename/retirement.

The app never reads secret values and never deletes or changes secrets/variables.

### Distribution
Marketplace search around unused GitHub Actions secrets, rename secret, variable cleanup and migration.

### Monetization hypothesis
Free one-name scan; paid organization-wide unused-name inventory, batch migrations and recurring hygiene reports.

### Competition
Secret-scanning products detect leaked credential values, while settings-management tools create/sync secrets. The surviving niche is **usage/dependency analysis of secret and variable names**, which is materially different.

### Risk
A secret may be consumed indirectly after being mapped to another environment variable or passed to an external script. Coverage must be confidence-scored.

### Verdict
**Advance.** Strong low-risk GitHub-native utility.

## Dropped after deeper review

- Generic workflow security: crowded by ActionScope, pipeline scanners and native GitHub security features.
- Required-check drift: a current Marketplace Action already targets required-check drift.
- Vendor runtime/deprecation scanning: a current Marketplace Action already scans dated runner/runtime/vendor breakages.
- Generic configuration drift/ruleset management: existing actions and apps cover repository settings and drift.
- Secret-value scanning: heavily crowded and native functionality exists.

## Stage 3 ranking

1. Repository rename / transfer dependency preflight
2. Actions environment retirement dependency preflight
3. Actions secret / variable name retirement usage scanner

## Verification record
- Last verified: 2026-10-25
- Stage 3 status: complete
- Stage 5: out of scope
