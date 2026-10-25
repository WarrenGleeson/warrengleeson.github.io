---
title: Revenue Investigation — Wave 29 Stage 4 Implementation Plans
summary: Stage 4 implementation and acquisition plans for the three strongest Atlassian Marketplace Forge app concepts. No Stage 5 development is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 328
permalink: /projects/notes/revenue-investigation-wave-29-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-29, atlassian, forge, stage-4]
---

# Wave 29 Stage 4 — Implementation Plans

Planning only. No development, Marketplace submission, customer testing, payments or outreach should be executed from this chat.

## Rank 1 — Jira project archive/delete dependency preflight

### MVP
- Forge-only, read-only app.
- Project picker.
- Scan saved filters/JQL references to project key/ID.
- Resolve boards backed by affected filters.
- Resolve visible dashboards/gadgets referencing affected filters where APIs allow.
- Count cross-project issue links and open work.
- Show unsupported dependency classes explicitly.
- Export/copy retirement checklist and evidence summary.
- No archive/delete/write permissions.

### Commercial model
Paid via Atlassian. Free single-project scan or limited findings; paid unlimited scans/history/export. Keep pricing low enough for individual Jira admins to install without procurement friction.

### Marketplace acquisition
- Listing title/keywords: Jira project deletion, archive cleanup, dependency, impact, admin.
- Changelog/content pages around safe Jira project retirement.
- Runs on Atlassian / zero-egress positioning if achievable.
- Screenshots should demonstrate one-click project selection and exact downstream dependencies.

### Main risk
Forge cannot expose every possible dependency. Coverage transparency is essential.

### Stage 4 verdict
**Best first Atlassian micro-app to validate in a separate chat.**

---

## Rank 2 — Atlassian/JQL platform-change impact scanner

### MVP
- Versioned YAML/JSON rule packs for specific announced Atlassian changes.
- Scan admin-visible saved filters and dependent boards/dashboards.
- Detect affected JQL tokens, field IDs/names or configuration references.
- Link every finding to the originating Atlassian change notice and affected Jira object.
- Mark dependency categories unavailable to Forge as unchecked.
- Historical scan snapshots to show remediation progress.

### Commercial model
Free scan for the latest high-profile change; paid continuous monitoring, historical reports and all rule packs via Atlassian Marketplace licensing.

### Marketplace acquisition
Each major Atlassian platform change becomes its own search/discovery event and documentation page. This creates recurring organic acquisition without cold outreach.

### Main risk
Ongoing rule maintenance. If Atlassian stops making impactful customer-visible changes, usage becomes episodic.

### Stage 4 verdict
**Strong recurring distribution model; potentially more scalable than rank 1 if rule maintenance remains manageable.**

---

## Rank 3 — JSM request-type retirement dependency preflight

### MVP
- Forge read-only app for JSM Cloud.
- Request-type picker.
- Show open/recent requests and usage trend.
- Inspect accessible request-type configuration, groups and relevant queue/filter dependencies.
- Build retirement/replacement checklist.
- Clearly list JSM settings Forge cannot inspect.
- No request-type mutation.

### Commercial model
Free one-request-type scan; paid bulk/project-wide cleanup report using Paid via Atlassian licensing.

### Marketplace acquisition
Target JSM admins searching for request-type cleanup, portal rationalization and service-desk consolidation. Cross-listing language should focus on a single job: "before you delete or merge a request type, see what still depends on it."

### Main risk
JSM API visibility is incomplete, which may cap the app's value.

### Stage 4 verdict
**Good micro-app shape, but narrower and more API-constrained than ranks 1–2.**

## Platform economics note

Atlassian Marketplace is unusually well aligned with this research direction because Forge provides hosting/authentication primitives and Paid via Atlassian provides licensing/billing. As of 2026, Forge partners receive 100% of gross revenue on their first US$1M of lifetime Forge revenue, after which the standard Marketplace share applies.

## Wave 29 conclusion

Top three:
1. Jira project archive/delete dependency preflight
2. Atlassian/JQL platform-change impact scanner
3. JSM request-type retirement dependency preflight

The key lesson is that Atlassian is attractive economically but highly competitive. The best opportunities are tiny, read-only admin utilities around specific change decisions rather than broad Jira enhancement products.

## Verification record
- Last verified: 2026-10-25
- Stage 4 status: complete
- Stage 5: explicitly out of scope
