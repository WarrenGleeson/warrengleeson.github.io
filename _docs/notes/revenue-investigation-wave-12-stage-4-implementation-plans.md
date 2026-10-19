---
title: Revenue Investigation — Wave 12 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest Wave 12 concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 260
permalink: /projects/notes/revenue-investigation-wave-12-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-12, stage-4, acquisition]
---

# Wave 12 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — Chrome extension privacy/disclosure vs manifest preflight

### Core promise
Before a Chrome Web Store submission or update, compare the extension manifest, permission changes, stated single purpose, privacy policy and store disclosures for obvious policy inconsistencies.

### MVP plan
- Local CLI plus optional browser/web report.
- Parse `manifest.json`, permissions, host permissions and optional permissions.
- Compare current manifest against prior release to classify permission deltas.
- Developer supplies store-listing purpose/disclosure text and privacy-policy text.
- Flag permissions/data categories missing from disclosures.
- Flag stated data uses that appear unrelated to the declared single purpose for manual review.
- Highlight added permissions likely to trigger release/user reapproval considerations.
- Link each finding to current Chrome Web Store policy/docs.
- Never claim guaranteed approval or legal privacy compliance.

### Likely stack
- TypeScript/Node CLI or Python parser.
- Versioned policy/rule pack.
- GitHub Action for release CI.
- Optional repository history dashboard later.

### Pricing hypothesis
- Free: local/single-release scan.
- CA$10–20: one-off submission readiness report.
- CA$10–25/month: repository history, scheduled release checks and team policies.

### Semi-automated acquisition pipeline
1. Monitor official Chrome Web Store policy/update pages.
2. Convert changes into proposed deterministic rules; require human verification before publishing.
3. Publish search pages around specific policy changes, permission prompts and disclosure requirements.
4. Free CLI/GitHub Action acts as primary acquisition.
5. Use public extension manifests/open-source repos only for aggregate rule testing and market sizing; never auto-contact maintainers.
6. Create factual demo reports using open-source/sample extensions.
7. In future validation chats, any direct outreach must be manually approved, low-volume and compliant; long-term acquisition should be GitHub/search/product-led.
8. Route multi-extension/team interest to the owner.

### Main risks
- Policy interpretation can be contextual.
- Chrome may expand native submission linting.
- Privacy-policy text analysis can only surface review candidates, not definitive violations.

### Stage 4 verdict
**Highest-priority Wave 12 candidate.**

---

## Rank 2 — Atlassian Marketplace pre-submission trust/security checker

### Core promise
Give Forge/Marketplace developers one pre-submission readiness report covering the app configuration and evidence Atlassian expects before formal Marketplace/security review.

### MVP plan
- Local CLI/workspace for Forge app repositories.
- Parse manifest scopes, egress, storage/remote configuration and selected Marketplace metadata.
- Checklist for Partner Verification prerequisites.
- Privacy & Security tab evidence mapper.
- Security requirement checklist and unresolved-evidence inventory.
- Data-residency / Runs on Atlassian readiness section using official platform checks where available rather than duplicating them.
- Optional Atlassian Enterprise Certified preparation section.
- Source-linked report with “ready / missing evidence / review required.”
- Never imply certification or guaranteed approval.

### Likely stack
- TypeScript/Node CLI aligned with Forge tooling.
- Versioned rules/checklists sourced from Atlassian docs.
- GitHub Action and optional lightweight evidence workspace.

### Pricing hypothesis
- Free: basic app/repository preflight.
- CA$20–40: detailed submission-readiness export.
- CA$15–30/month: multiple apps, release history and reusable partner evidence.

### Semi-automated acquisition pipeline
1. Monitor official Marketplace approval, security enforcement, privacy/security and trust-program docs.
2. Diff requirement changes and queue checklist/rule updates for human approval.
3. Publish submission-specific search pages such as Forge Marketplace security checklist and AEC readiness.
4. Free CLI becomes the primary product-led acquisition path.
5. Use public Forge sample repositories and app manifests for deterministic test coverage.
6. Create synthetic/public example readiness reports; do not scrape private partner tickets or security responses.
7. Future validation outreach, if any, should target voluntarily public Atlassian app developers/consultants, remain low-volume and manually approved.
8. Route multi-app/consultant readiness interest to the owner.

### Main risks
- Atlassian already provides official scanners and may expand preflight tooling.
- Some partner-verification/security evidence is organizational rather than technical.
- Requirements can change quickly.

### Stage 4 verdict
**Strong marketplace-operations niche if positioned as consolidation/preparation rather than certification.**

---

## Rank 3 — SaaS plan-feature removal impact inventory

### Core promise
Help small teams understand which internal workflows will be affected when a SaaS vendor removes, downgrades or moves a relied-on feature between plans.

### MVP plan
- User creates a vendor/application record and lists depended-on features/workflows.
- Import or manually capture current plan/features and renewal date.
- Monitor public vendor pricing/plan/changelog pages for changes, or allow user-supplied change notices.
- Map changed/removed features against internal workflows, owners and renewal timing.
- Produce an impact checklist: unaffected, review, migration required, cost increase.
- Preserve before/after evidence and source URL.
- Do not attempt contract/legal interpretation.

### Likely stack
- Lightweight SaaS inventory/database.
- Public page/change-monitor integrations rather than rebuilding a crawler initially.
- Rule-based workflow dependency map.

### Pricing hypothesis
- Free: 2–3 vendors.
- CA$10–20/month: 20–50 vendors/workflows.
- Small MSP/ops tier for multiple clients later.

### Semi-automated acquisition pipeline
1. Use existing page-change APIs/services or public changelogs as change sources where economical.
2. Generate factual search/content around notable SaaS plan migrations and feature removals.
3. Free dependency inventory/template becomes the main acquisition surface.
4. Track which vendor changes create the most workflow impacts and prioritize integrations.
5. Discover public SaaS-admin/operations communities for aggregate pain research.
6. Demonstrations use synthetic teams/workflows rather than inferring a company's stack.
7. Any future outreach remains controlled/manual; intended acquisition is search/templates/integrations.
8. Route multi-vendor/MSP interest to the owner.

### Main risks
- Generic website change-monitoring is already crowded.
- Value depends on users maintaining their internal dependency map.
- SaaS management platforms could add this feature.

### Stage 4 verdict
**Promising only as workflow-impact mapping; generic vendor-change monitoring is not differentiated.**

## Wave 12 conclusion

Top three:

1. Chrome extension privacy/disclosure vs manifest preflight
2. Atlassian Marketplace pre-submission trust/security checker
3. SaaS plan-feature removal impact inventory

Wave 12 adds developer-store submission readiness and SaaS dependency-impact management while avoiding generic AI compliance, vendor-risk and webpage-monitoring categories already served by broader platforms.

## Verification record

- Last verified: 2026-10-19
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
