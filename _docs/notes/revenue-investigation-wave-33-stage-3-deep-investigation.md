---
title: Revenue Investigation — Wave 33 Stage 3 Deep Investigation
summary: Deep investigation of the strongest Salesforce AgentExchange/AppExchange opportunities after direct competitor checks.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 343
permalink: /projects/notes/revenue-investigation-wave-33-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-33, salesforce, appexchange]
---

# Wave 33 Stage 3 — Deep Investigation

## 1. Connected App -> External Client App migration readiness audit

### Problem
Salesforce restricted creation of new Connected Apps in Spring '26 and recommends migrating toward External Client Apps (ECAs). Existing Connected Apps still work, but Salesforce has said future end-of-support is coming. Many orgs have a mixed estate of locally created Connected Apps, packaged integrations, OAuth policies, callback URLs, scopes, certificates, support owners and third-party dependencies. The actual migration problem is not “how do I create an ECA?” but “which Connected Apps do I have, which ones can I migrate myself, which ones depend on vendors, and what security/operational differences must be reviewed?”

### Product
A native read-only readiness app that inventories accessible Connected Apps and classifies:
- local vs packaged/vendor-owned app;
- OAuth flow and scope profile;
- callback URLs and policy configuration;
- current owner/contact/support metadata where available;
- last-use / active-use indicators where APIs expose them;
- migration responsibility: customer vs ISV/vendor;
- candidate ECA mapping checklist;
- unsupported/unknown settings requiring manual review;
- source-linked evidence export for change control/security review.

It does not migrate, rotate secrets or modify Connected Apps automatically.

### Distribution
AgentExchange/AppExchange search around Connected App migration, External Client Apps, Spring '26, OAuth modernization and Salesforce integration security.

### Monetization hypothesis
Given Salesforce's listing/security-review economics, price as a higher-value admin product rather than a micro-app: free org summary or limited scan, then roughly US$49–149/org/month or annual equivalent for full inventory, reports and recurring readiness monitoring.

### Competition
Salesforce now publishes free skills that help configure Connected Apps and ECAs, and vendors are releasing their own replacement ECAs. Current review did not surface a dedicated AppExchange product whose primary job is **org-wide Connected App migration inventory/readiness across first-party, local and packaged integrations**.

### Risk
Salesforce metadata/API visibility may not expose every runtime dependency or vendor-specific migration requirement. The app must distinguish factual inventory from vendor consultation requirements.

### Verdict
**Advance.** Strongest Wave 33 concept.

---

## 2. Legacy Named Credential migration readiness audit

### Problem
Legacy Named Credentials are deprecated and Salesforce documents that they will be unsupported in future releases. Orgs often have integrations split across legacy Named Credentials, modern Named Credentials, External Credentials, permission sets and Apex/Flow callouts. Admins need an inventory of which legacy credentials are actually in use, who depends on them and what must be recreated before retirement.

### Product
Inventory legacy and modern credentials and produce a migration-readiness report:
- legacy Named Credentials still present;
- endpoint/authentication type;
- Apex/Flow/metadata references where discoverable;
- permission-set or principal access dependencies;
- candidate modern Named Credential + External Credential structure;
- missing principal assignments;
- endpoint duplicates / inconsistent credential naming;
- migration/rotation checklist and evidence export;
- explicit unknowns where usage cannot be proven statically.

No secret values are read, displayed or modified.

### Distribution
AgentExchange/AppExchange search around legacy Named Credentials, External Credentials, Salesforce integration migration and credential modernization.

### Monetization hypothesis
Free limited inventory; paid org-wide report, recurring monitoring and consultant/multi-org tier in the US$39–99/org/month range or annual pricing.

### Competition
Salesforce's own current AgentExchange skills cover creation/configuration of modern integration plumbing. Current research did not surface an exact native product centered on **legacy credential estate discovery + migration impact/readiness**.

### Risk
Usage tracing across Apex, Flow and external integrations can be incomplete. High trust/security expectations mean the app should remain native/read-only and never touch credential values.

### Verdict
**Advance.** Strong platform-change niche with enterprise willingness to pay.

---

## 3. Queue / routing retirement dependency preflight

### Problem
Queues remain operationally important in Service Cloud and Enhanced Omni-Channel. Before renaming, consolidating or retiring a queue, admins need to know what work, routing configuration, flows, ownership and service-channel assumptions still depend on it. Broad metadata analyzers can show references, but the operational decision includes live records, members, routing behavior and open work.

### Product
Select a queue and generate a retirement blast-radius report:
- current members and supported object types;
- open records currently owned by the queue;
- routing configurations/service-channel relationships where exposed;
- Flow/automation metadata references to queue ID/name where discoverable;
- queue email / notification settings;
- recent assignment/routing activity;
- possible replacement queue and migration checklist;
- unresolved dependency classes clearly listed.

No queue, ownership or routing configuration is changed automatically.

### Distribution
AppExchange search around queue cleanup, queue consolidation, Service Cloud migration and Omni-Channel administration.

### Monetization hypothesis
Free single-queue scan; paid bulk queue inventory, retirement projects and recurring routing hygiene. Pricing could fit US$29–79/org/month or annual admin tier.

### Competition
Broad Salesforce metadata-impact platforms can identify references, but current research did not surface a focused operational **queue retirement preflight** combining metadata with live ownership/routing context.

### Risk
Queue/Omni APIs and metadata coverage vary by feature. Operational routing logic can include dynamic Flow decisions that are hard to resolve statically.

### Verdict
**Advance cautiously.** Good evergreen niche; less time-sensitive than ranks 1–2.

---

## Dropped after deeper review

- Generic metadata impact analysis: mature, led by Elements.cloud and similar products.
- Field cleanup/usage: current paid specialists already exist.
- Permission/access reporting: Salesforce provides free tooling and multiple AppExchange apps.
- User deactivation: exact free AppExchange product exists.
- Standard Omni migration readiness: Standard Omni reached end of life in Summer '26, so the primary migration window has passed.
- Generic Agentforce architecture/dependency analysis: Salesforce now publishes first-party AgentExchange skills in this area.

## Stage 3 ranking

1. Connected App -> External Client App migration readiness audit
2. Legacy Named Credential migration readiness audit
3. Queue / routing retirement dependency preflight

## Verification record
- Last verified: 2026-10-25
- Stage 3 status: complete
- Stage 5: out of scope
