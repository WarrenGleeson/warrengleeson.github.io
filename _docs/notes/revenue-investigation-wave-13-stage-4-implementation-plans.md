---
title: Revenue Investigation — Wave 13 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest Wave 13 concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 264
permalink: /projects/notes/revenue-investigation-wave-13-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-13, stage-4, acquisition]
---

# Wave 13 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — Gmail third-party account retirement readiness workspace

### Core promise
Help individuals and small organizations identify every mailbox/alias/send path affected by Gmail's January 2027 removal of third-party `Send as`, Gmailify and POP, then produce a concrete migration checklist before the cutoff.

### MVP plan
- Manual/importable inventory of affected third-party email addresses, aliases and current receive/send paths.
- Classify each configuration by current Gmail feature dependency: POP, Gmailify, third-party Send-as, forwarding-only or unaffected.
- Provide migration-path checklist for provider-native web/app access, desktop IMAP/SMTP or supported mobile Gmail configuration.
- Optional SPF/DKIM/DMARC readiness checks for domains whose outbound path will change.
- Owner/status/date fields for teams managing multiple mailboxes.
- Export cutover runbook and completion evidence.
- Never request mailbox passwords or store credentials.

### Likely stack
- Browser-first checklist/workspace.
- DNS lookup service for optional authentication checks.
- CSV import/export for multi-account users.

### Pricing hypothesis
- Free: single-account readiness checklist.
- CA$10–20: one-off multi-account migration report.
- CA$15–30/month: admin/team workspace through the migration window.

### Semi-automated acquisition pipeline
1. Monitor Google's official third-party Gmail-account support page for timing or replacement-option changes.
2. Publish factual search pages around Gmail POP retirement, Gmailify shutdown and Send-as migration.
3. Free single-account checklist is the primary inbound funnel.
4. Analyze opt-in issue categories to prioritize common migration paths/providers.
5. Discover public small-business/admin communities where the retirement is being discussed for aggregate research only.
6. Produce synthetic migration examples rather than using private mailbox data.
7. Any future direct outreach should be low-volume, manually approved and compliant; intended acquisition is deadline-driven search/help content.
8. Route multi-account/admin interest to the owner.

### Main risks
- Short commercial window around the January 2027 cutoff.
- Google could extend or modify the retirement plan.
- Some migration paths are provider-specific, increasing support complexity.

### Stage 4 verdict
**Highest-priority Wave 13 candidate, but with a time-limited opportunity window.**

---

## Rank 2 — EU Data Act SaaS exit/export readiness checker

### Core promise
Show whether a SaaS/cloud service has the practical exports, interfaces, documented steps and internal dependencies needed for a customer to switch providers under the EU Data Act framework.

### MVP plan
- One workspace per SaaS/cloud service.
- Inventory export formats, API/export endpoints, attachments/files, metadata, audit/history data and identity/configuration data.
- Record documented switching/termination steps, notice periods and provider-supplied timeframes.
- Map customer workflows/integrations that depend on non-exportable features.
- Track evidence URLs/screenshots/docs and source dates.
- Produce a readiness report: exportable, partial, unknown, workflow dependency, manual review required.
- Include switching-charge/egress evidence where relevant.
- Never claim legal compliance or interpret contractual rights conclusively.

### Likely stack
- Browser-based structured checklist/workspace.
- Optional vendor documentation crawler/link inventory.
- CSV/API-based export-test modules later.

### Pricing hypothesis
- Free: one vendor checklist.
- CA$20–50: one-off detailed exit-readiness report.
- CA$20–40/month: portfolio of vendors, evidence freshness and recurring exit-plan reviews.

### Semi-automated acquisition pipeline
1. Monitor official European Commission Data Act switching/interoperability guidance and implementation updates.
2. Publish search pages around SaaS switching, data export, egress fees and exit-plan readiness.
3. Free one-vendor checklist drives inbound acquisition.
4. Build a factual library of publicly documented export/interface capabilities for popular SaaS products, clearly timestamped and not treated as legal conclusions.
5. Rank vendors by user demand and recurring switching pain.
6. Generate synthetic/customer-supplied example exit reports; do not infer hidden vendor functionality.
7. Future outreach, if any, should target SaaS operations/procurement consultants or opt-in users, remain low-volume/manual-approved, and avoid legal claims.
8. Route multi-vendor/procurement-team interest to the owner.

### Main risks
- Legal/regulatory interpretation risk.
- SaaS export capabilities change frequently.
- Broad SaaS-management platforms could absorb this workflow.

### Stage 4 verdict
**Strong current regulatory/operational niche with a longer life than the Gmail migration idea.**

---

## Rank 3 — Vendor feature/EOL dependency impact inventory

### Core promise
When a SaaS feature, API, support tier or vendor product is retired, immediately show which internal workflows, integrations and owners are affected.

### MVP plan
- Inventory vendor/product/features/APIs and internal dependent workflows.
- Assign workflow owners and criticality.
- Store renewal dates, announced retirement dates and migration links.
- Ingest public lifecycle/changelog notices or user-supplied notices.
- Produce an impact report: affected workflow, owner, deadline, renewal conflict and migration status.
- Simple evidence archive of before/after vendor notices.
- No attempt to discover every dependency automatically in the initial version.

### Likely stack
- Lightweight relational SaaS/workspace.
- Integrations with public changelog/EOL feeds where useful.
- CSV/template import for initial dependency mapping.

### Pricing hypothesis
- Free: small inventory.
- CA$10–25/month: 20–100 external dependencies/workflows.
- Consultant/MSP tier later for multiple clients.

### Semi-automated acquisition pipeline
1. Monitor high-demand vendor lifecycle/changelog sources only after users declare a dependency.
2. Generate factual deadline pages for widely used product retirements and migration events.
3. Free dependency-map template/tool is the inbound acquisition surface.
4. Track which vendors/dependency types produce recurring impact to prioritize integrations.
5. Use public tech-stack/admin communities for aggregate research, not automatic prospecting.
6. Demonstrate with synthetic workflow maps.
7. Any future outreach remains small/manual; primary acquisition should be search/templates/integration partnerships.
8. Route multi-vendor/MSP demand to the owner.

### Main risks
- User maintenance burden is substantial.
- Generic CMDB/SaaS-management platforms can substitute.
- Automatic dependency discovery would materially increase complexity.

### Stage 4 verdict
**Viable only if dependency-map setup can remain lightweight enough to sustain usage.**

## Wave 13 conclusion

Top three:

1. Gmail third-party account retirement readiness workspace
2. EU Data Act SaaS exit/export readiness checker
3. Vendor feature/EOL dependency impact inventory

Wave 13 adds deadline-driven email migration, Data Act switching operations and external-vendor lifecycle dependency management while avoiding generic supply-chain provenance and cloud-cost categories already served by native platforms.

## Verification record

- Last verified: 2026-10-19
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
