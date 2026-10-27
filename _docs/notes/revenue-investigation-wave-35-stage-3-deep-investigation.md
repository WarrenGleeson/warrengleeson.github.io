---
title: Revenue Investigation — Wave 35 Stage 3 Deep Investigation
summary: Deep investigation of the strongest Microsoft Teams / Microsoft 365 marketplace opportunities after direct competitor checks.
section: notes
doc_type: note
status: active
created: 2026-10-26
updated: 2026-10-26
last_verified: 2026-10-26
owner: High Director
order: 351
permalink: /projects/notes/revenue-investigation-wave-35-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-35, microsoft-teams, appsource]
---

# Wave 35 Stage 3 — Deep Investigation

## 1. Teams Workflows orphan-owner / continuity audit

### Problem
Microsoft's replacement for legacy Teams incoming webhooks relies on Workflows/Power Automate. Microsoft documents that Workflows are tied to specific owners and can become orphaned if the owner leaves unless co-owners are assigned. For operationally important channel automations, that creates a concrete continuity risk: the webhook or workflow may still appear configured but no longer have a viable owner, connection or support path.

### Product
A Teams/Microsoft 365 admin app that inventories accessible Teams-linked workflows and flags:
- single-owner workflows with no co-owner;
- owner disabled/departed or account at risk of removal;
- workflow connection owned by a different/departed user;
- disabled workflow still referenced by a critical Teams channel/process;
- webhook/workflow with no documented business owner;
- team/channel owner mismatch with workflow owner;
- critical workflow without backup owner;
- source-linked continuity checklist and handoff evidence pack.

The app never changes owners or credentials automatically.

### Distribution
Teams Store/AppSource search around orphaned flows, Teams Workflows, Power Automate ownership, webhook continuity and employee departure.

### Monetization hypothesis
Free tenant summary or first 10 workflows; paid flat-rate tenant plan in the US$29–79/month range depending on workflow count and reporting depth.

### Competition
Broad Power Platform governance tools exist, but current exact searches did not surface a lightweight Teams-focused continuity app whose main job is identifying **workflow ownership risk for Teams operational automations**.

### Risk
Power Automate/Graph API permissions and tenant-admin consent may create install friction. Scope should remain read-only and narrowly focused.

### Verdict
**Advance.** Strongest Wave 35 concept.

---

## 2. Team / channel retirement dependency preflight

### Problem
Archiving or deleting a Team/channel can affect more than messages. Private/shared channels may have associated SharePoint sites, apps/tabs, workflow dependencies, files, ownership and external participants. Microsoft supports channel archive/restore, but admins still need a practical blast-radius report before retirement.

### Product
Select a Team/channel and report accessible dependencies:
- active members/owners/guests;
- private/shared channel type and connected SharePoint site;
- installed tabs/apps and channel-specific app availability;
- recent message/file/activity indicators;
- linked Teams Workflows/webhook processes where discoverable;
- open ownership/continuity risks;
- externally shared participants or shared-channel relationships;
- archive/delete implications and handoff checklist;
- unsupported dependency classes explicitly identified.

No Team/channel is archived or deleted automatically.

### Distribution
AppSource/Teams Store search around Teams archive, channel cleanup, team retirement, M365 group cleanup and tenant rationalization.

### Monetization hypothesis
Free one Team/channel scan; paid tenant-wide lifecycle inventory, batch retirement reports and export/history at US$39–99/month.

### Competition
Broad governance suites manage Teams lifecycle, but the surviving wedge is a simple **before-you-archive/delete blast-radius report** rather than lifecycle automation or policy enforcement.

### Risk
Large tenants and private/shared channel permissions complicate visibility. Admin consent requirements can reduce self-serve conversion.

### Verdict
**Advance.** Good evergreen admin utility.

---

## 3. Shared/private-channel app compatibility audit

### Problem
Apps behave differently across standard, private and shared channels. Microsoft documents that app installation/availability depends on host-team context and manifest/capability support, and shared/private channel behavior continues to evolve. Teams admins and app owners can therefore discover too late that a business-critical app is unavailable or behaves differently when teams restructure around shared/private channels.

### Product
Inventory selected Teams/channels/apps and flag:
- app installed in host team but unavailable in a shared/private channel context;
- required channel feature capability missing from app manifest where inspectable;
- shared-in channel whose host-team app dependencies differ from consuming team expectations;
- tabs/apps present in standard channels but absent from private/shared equivalents;
- external-participant/channel topology that may affect app availability;
- compatibility matrix by channel type;
- migration/readiness checklist before converting processes to a new channel topology.

The app does not install or reconfigure third-party apps automatically.

### Distribution
Teams Store/AppSource search around shared channels, private channels, app compatibility and Teams migration/readiness.

### Monetization hypothesis
Free small compatibility matrix; paid tenant-wide audit at US$29–69/month.

### Competition
Microsoft documentation explains the behavior, but current exact Marketplace searches did not surface a dedicated compatibility-audit product centered on **app availability across shared/private/standard channel topology**.

### Risk
Manifest and runtime capability details can be incomplete or change over time. Some results may need to be labeled “requires live test.”

### Verdict
**Advance cautiously.** Good platform-specific niche, but less urgent than ranks 1–2.

## Stage 3 ranking
1. Teams Workflows orphan-owner / continuity audit
2. Team / channel retirement dependency preflight
3. Shared/private-channel app compatibility audit

## Verification record
- Last verified: 2026-10-26
- Stage 3 status: complete
- Stage 5: out of scope
