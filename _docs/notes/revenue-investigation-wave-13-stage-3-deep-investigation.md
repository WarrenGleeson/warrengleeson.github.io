---
title: Revenue Investigation — Wave 13 Stage 3 Deep Investigation
summary: Deep investigation of five Wave 13 finalists after competition and official-platform checks.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 263
permalink: /projects/notes/revenue-investigation-wave-13-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-13, deep-investigation]
---

# Wave 13 Stage 3 — Deep Investigation

## 1. Gmail third-party account retirement readiness workspace

### Problem
Google says Gmail will fully remove third-party `Send as`, Gmailify and POP support in January 2027. Users who rely on Gmail as a front end for external mailboxes need to identify affected accounts, aliases and forwarding/send paths before the cutoff.

### Product
A self-serve migration-readiness workspace that inventories current third-party addresses, aliases and send/receive paths, then produces a cutover checklist for native provider apps, desktop IMAP/SMTP clients or mobile Gmail app configurations. It can also include SPF/DKIM/DMARC checks for domains that will begin sending through a different path.

### Distribution
Search around Gmail POP/Gmailify/Send-as retirement, Workspace/admin communities and downloadable readiness checklist.

### Monetization hypothesis
Free single-account checklist; CA$10–20 one-off multi-account migration report; CA$15–30/month for small-business/admin teams managing many mailboxes.

### Competition
Google documents replacement options, but the current review did not identify a focused inventory/migration-readiness tool for organizations with many affected third-party Gmail-linked accounts.

### Risk
Some configuration data may not be exportable automatically. The tool may require user-entered inventory unless Workspace/admin APIs expose enough metadata.

### Verdict
**Advance.** Strong deadline-driven operational wedge.

---

## 2. EU Data Act SaaS exit/export readiness checker

### Problem
The EU Data Act requires data-processing providers to remove switching obstacles and support data portability. Switching charges disappear from 12 January 2027. SaaS/PaaS providers must make export/open-interface options available, but many vendors and buyers still need to determine whether an exit process is operationally ready.

### Product
A provider-side or buyer-side readiness workspace that inventories export formats, API/export endpoints, retained metadata, documented deletion/offboarding steps, switching timeframes, contractual notice obligations and residual dependencies. It produces an evidence-backed exit-readiness report rather than a legal compliance certificate.

### Distribution
Search around EU Data Act cloud switching, SaaS exit plans and portability; cloud/SaaS operations communities; templates/checklists.

### Monetization hypothesis
Free single-vendor checklist; CA$20–50 one-off readiness report; CA$20–40/month for organizations tracking several SaaS vendors/services.

### Competition
Broad Data Act compliance platforms and legal advisory offerings exist, but the specific operational question—**can this service actually export and transition the data/workflows needed for switching?**—is narrower and more testable.

### Risk
Legal interpretation must remain outside the product. Portability can include behavior/functionality beyond file exports, so the checker must clearly distinguish technical evidence from legal sufficiency.

### Verdict
**Advance.** Strong current regulatory timing with an operational rather than legal wedge.

---

## 3. Vendor feature/EOL dependency impact inventory

### Problem
Teams often discover too late that a vendor feature, API, support tier or product is being retired. The missing information is not the retirement notice itself—it is which internal workflows, integrations and owners depend on it.

### Product
A lightweight dependency map: vendor/product → feature/API → internal workflow/integration → owner → renewal/migration date. Public vendor notices or manually supplied announcements trigger an impact report showing affected workflows, owners and migration deadlines.

### Distribution
Search/templates for SaaS deprecation impact, internal operations communities, integration with public changelog/EOL sources.

### Monetization hypothesis
Free small inventory; CA$10–25/month for 20–100 dependencies; consultant/MSP tier later.

### Competition
Generic vendor/EOL monitors are common. The surviving wedge is the internal workflow dependency map, similar to an operational mini-CMDB specifically for external SaaS/API lifecycle risk.

### Risk
Users must maintain the dependency map. Without integrations or easy import, the product can become administrative overhead.

### Verdict
**Advance cautiously.** Differentiation exists but adoption friction is higher than ranks 1–2.

---

## 4. SaaS export-format completeness audit

### Problem
A vendor may claim to provide exports while omitting relationships, attachments, metadata, audit history or other information needed for switching.

### Finding
This is valuable, but it is naturally one section of candidate 2 rather than a standalone product. The same buyer needs to know both what can be exported and whether the broader exit process is workable.

### Verdict
**Merge into candidate 2.**

---

## 5. npm trusted-publishing readiness scanner

### Problem
npm trusted publishing replaces long-lived tokens with OIDC but has specific requirements around npm/Node versions, repository URL matching, workflow identity and `id-token: write` permissions.

### Finding
The checks are deterministic, but npm's documentation is already detailed and the setup surface is relatively small. A free linter could be useful, but willingness to pay is likely low.

### Verdict
**Hold.** Useful open-source utility, weaker standalone business.

## Stage 3 ranking

1. Gmail third-party account retirement readiness workspace
2. EU Data Act SaaS exit/export readiness checker
3. Vendor feature/EOL dependency impact inventory

## Advance to Stage 4

Advance those three only.

## Verification record

- Last verified: 2026-10-19
- Stage 3 status: complete
- Stage 5: out of scope
