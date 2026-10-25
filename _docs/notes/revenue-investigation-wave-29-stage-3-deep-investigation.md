---
title: Revenue Investigation — Wave 29 Stage 3 Deep Investigation
summary: Deep investigation of the strongest Atlassian Marketplace Forge app opportunities after direct competitor checks.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 327
permalink: /projects/notes/revenue-investigation-wave-29-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-29, atlassian, forge, marketplace]
---

# Wave 29 Stage 3 — Deep Investigation

## 1. Jira project archive/delete dependency preflight

### Problem
Before archiving or deleting a Jira project, admins need to know what other objects still depend on it: saved filters, boards, dashboards, shared JQL, issue links, cross-project references and ownership assumptions. Jira has project archive functionality and Marketplace archive tools, but current research did not surface a focused read-only dependency preflight that answers "what breaks if this project goes away?"

### Product
Select a project and generate a dependency inventory:
- saved filters/JQL referencing the project key;
- boards backed by those filters;
- dashboards/gadgets that depend on those filters where visible;
- cross-project linked issues;
- shared objects owned by project members/admins;
- components/versions referenced externally where APIs expose them;
- unsupported/uncheckable dependency classes explicitly listed.

Output is a review pack only; the app never archives or deletes the project.

### Distribution
Atlassian Marketplace search around Jira cleanup, project archive, deletion, migration and admin change safety.

### Monetization hypothesis
Free one-project scan; paid unlimited/site-wide scans using standard Atlassian tier pricing.

### Competition
Project Archiver handles archive/restore and configuration tools manage broader Jira changes, but the surviving wedge is a narrow, read-only **blast-radius report before retirement**.

### Verdict
**Advance.** Best Wave 29 niche.

---

## 2. Atlassian/JQL platform-change impact scanner

### Problem
Atlassian regularly changes fields, JQL behavior, APIs and platform capabilities. Admins can read release notes, but still need to determine which saved filters, boards, dashboards and configurations on their own site rely on the affected object or syntax.

### Product
Maintain versioned change-rule packs tied to published Atlassian platform changes. Scan site-visible objects for affected references and produce:
- saved filters using changed/deprecated JQL tokens or fields;
- boards and dashboards dependent on affected filters;
- project/configuration objects using affected statuses/fields where APIs expose them;
- exact source object + remediation link;
- "not inspectable" categories rather than false negatives.

The tool does not modify configurations automatically.

### Distribution
Marketplace search around Jira upgrade/deprecation readiness, plus changelog-driven landing pages for each major platform change.

### Monetization hypothesis
Freemium current-change scan; paid continuous readiness/history/reporting.

### Competition
Configuration and migration suites are broad, but current Marketplace review did not surface a dedicated changelog-to-your-instance impact scanner. The niche benefits from recurring Atlassian platform change.

### Risk
Rule maintenance is the product. Some dependency classes are not exposed through Forge APIs.

### Verdict
**Advance.** Strong recurring-content/distribution angle.

---

## 3. JSM request-type retirement dependency preflight

### Problem
JSM admins periodically rename, consolidate or retire request types. That can affect portal users, queues, reports, filters, links and operational documentation. Existing JSM standards/configuration apps compare projects, but the decision "can I safely retire this request type?" remains narrower.

### Product
Select a request type and report visible dependencies:
- current request volume and recent usage;
- queues/JQL that reference its project/issue-type/request-type identifiers where inspectable;
- public/portal wording and group placement;
- linked knowledge/configuration metadata exposed through APIs;
- issues still open under the request type;
- replacement/migration checklist;
- unsupported dependencies clearly identified.

No request types are modified or deleted.

### Distribution
Marketplace search around JSM request-type cleanup and portal rationalization.

### Monetization hypothesis
Free one request type; paid bulk/site-wide retirement scans.

### Competition
Service Project Standards for JSM covers configuration drift, while portal/admin products manage request types. The niche is the **retirement blast-radius decision**, not configuration management.

### Risk
Forge cannot read every JSM dependency, so usefulness depends on being transparent about coverage.

### Verdict
**Advance cautiously.** Good micro-app fit, but narrower than ranks 1–2.

## Dropped after deeper review

- Custom-field cleanup: several current Forge apps already compete directly.
- Permission/access auditing: multiple nearly identical current paid apps.
- Automation dependency mapping: current exact competitors.
- Workflow linting: current exact competitor.
- Confluence macro dependency scanning: current exact competitors.
- JSM knowledge coverage: current exact/free competitor.

## Stage 3 ranking

1. Jira project archive/delete dependency preflight
2. Atlassian/JQL platform-change impact scanner
3. JSM request-type retirement dependency preflight

## Verification record
- Last verified: 2026-10-25
- Stage 3 status: complete
- Stage 5: out of scope
