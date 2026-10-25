---
title: Revenue Investigation — Wave 32 Stage 4 Implementation Plans
summary: Stage 4 implementation and acquisition plans for the strongest GitHub Marketplace app concepts. No Stage 5 development is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 340
permalink: /projects/notes/revenue-investigation-wave-32-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-32, github, marketplace, stage-4]
---

# Wave 32 Stage 4 — Implementation Plans

Planning only. No development, Marketplace submission, customer testing, payments or outreach should be executed from this chat.

## Rank 1 — Repository rename / transfer dependency preflight

### MVP
- GitHub App, read-only where possible.
- Install on selected repositories or an organization.
- Repository picker.
- Scan accessible repository contents for old `owner/repo` references.
- Detect GitHub Actions `uses:` / reusable workflow references.
- Detect submodule URLs, README/docs links, badges, package/source metadata and GitHub Pages project-site references.
- Separate definite internal dependencies from external/unknown dependency classes.
- Generate rename/transfer migration checklist and downloadable report.
- No rename/transfer/write actions.

### Commercial model
- Free tier: one repository scan, enough value to drive installations toward GitHub's 100-install paid-plan requirement.
- Paid tier after eligibility: organization-wide scans, batch migration projects, exports/history and scheduled dependency snapshots.
- Paid via GitHub Marketplace; GitHub retains 5% of post-2021 transaction revenue.

### Acquisition
1. Marketplace keywords: repository rename, transfer repository, organization migration, GitHub Action rename, migration preflight.
2. Documentation around GitHub's documented action-hosting rename exception.
3. Free single-repo report should be genuinely useful, not crippleware.
4. Organization-wide tier creates natural upgrade after teams discover multiple dependencies.

### Main risks
- External references outside installed GitHub scope remain unknowable.
- Content scanning across large organizations must be efficient and permission-minimal.

### Stage 4 verdict
**Best Wave 32 candidate for a separate validation/build chat.**

---

## Rank 2 — Actions environment retirement dependency preflight

### MVP
- GitHub App with read-only Actions/environment/repository-content permissions.
- Environment picker.
- Parse workflow YAML for literal and dynamic `environment:` references.
- List environment secret/variable names only, never values.
- Include protection/reviewer settings and recent deployment activity where exposed.
- Follow local reusable workflows and classify unresolved dynamic references.
- Generate rename/delete checklist.
- No mutation.

### Commercial model
- Free one-environment scan.
- Paid organization-wide environment inventory, batch scans, recurring hygiene and report exports once Marketplace paid eligibility is reached.

### Acquisition
- Marketplace keywords around GitHub environment rename/delete, deployment environment cleanup and Actions migration.
- Practical content: “before deleting a GitHub environment, find every workflow that still references it.”
- Useful to platform teams and consultancies performing environment consolidation.

### Main risk
- Dynamic expressions reduce certainty.
- Some organization/environment metadata may require elevated read permissions that reduce install conversion.

### Stage 4 verdict
**Strong evergreen GitHub-admin micro-app.**

---

## Rank 3 — Actions secret / variable name retirement usage scanner

### MVP
- Read-only GitHub App.
- Enumerate secret/variable **names** where API permissions allow; never access values.
- User selects a name or runs repository-wide inventory.
- Scan workflow YAML, reusable workflows and composite actions for `secrets.*` / `vars.*` references.
- Trace direct environment-variable mappings where deterministic.
- Show organization/repository/environment scope and selected-repository availability where exposed.
- Produce definite/possible/unknown usage categories.
- Export migration checklist.
- No secret mutation.

### Commercial model
- Free one-name scan.
- Paid org-wide unused-name inventory, batch rename/retirement reports and scheduled hygiene scans after paid Marketplace eligibility.

### Acquisition
- Marketplace/search terms: unused GitHub secret, rename Actions secret, GitHub variable usage, secret cleanup.
- Position clearly against security scanners: this app does not search for leaked secret values; it answers “is this secret/variable name still used?”

### Main risk
- Indirect usage through shell scripts and dynamically constructed names can create false negatives if scope is overstated.

### Stage 4 verdict
**Very good low-security-risk utility with clear differentiation.**

## Platform economics note

GitHub Marketplace is attractive once distribution exists: paid GitHub Apps use GitHub's billing flow, developers can offer flat-rate or per-unit plans, and GitHub remits 95% of the sale price. The main friction is that paid GitHub Apps require verified-publisher status and at least 100 installations first, so ideas need a compelling free tier before monetization begins.

## Wave 32 conclusion

Top three:
1. Repository rename / transfer dependency preflight
2. Actions environment retirement dependency preflight
3. Actions secret / variable name retirement usage scanner

The key lesson is that GitHub Marketplace is not as immediately monetizable as Figma/Shopify because of the 100-install paid-plan threshold, but it is still attractive for free-first admin utilities that naturally expand into organization-wide paid scans.

## Verification record
- Last verified: 2026-10-25
- Stage 4 status: complete
- Stage 5: explicitly out of scope
