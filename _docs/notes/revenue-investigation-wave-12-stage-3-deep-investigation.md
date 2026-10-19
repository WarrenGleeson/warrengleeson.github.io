---
title: Revenue Investigation — Wave 12 Stage 3 Deep Investigation
summary: Deep investigation of the strongest Wave 12 ideas after direct competition and official-platform capability checks.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 259
permalink: /projects/notes/revenue-investigation-wave-12-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-12, deep-investigation]
---

# Wave 12 Stage 3 — Deep Investigation

## 1. Chrome extension privacy/disclosure vs manifest preflight

### Problem
Chrome Web Store policy changes now require all data collection to be prominently disclosed and strictly necessary to the extension's disclosed single purpose. Extensions must also request only the narrowest permissions needed. A developer therefore needs consistency across `manifest.json`, permissions, privacy policy, store listing and actual declared data uses before submitting an update.

### Product
A local CLI/web checker that ingests an extension manifest plus developer-supplied privacy-policy/store-listing text and produces a deterministic mismatch report: undeclared host/API permissions, broad permissions requiring review, data-collection claims lacking matching disclosure, disclosure text that refers to data not plausibly needed for the stated purpose, and update-time permission changes requiring explicit release review.

### Distribution
Chrome extension developer search, GitHub Marketplace/CLI, Chrome Web Store development communities and release-specific SEO pages.

### Monetization hypothesis
Free local scan; CA$10–20 one-off release report; CA$10–25/month for monitored repositories/history/team policies.

### Competition
Generic extension security scanners exist, but the current review did not identify a strong product whose central job is **policy consistency between manifest permissions, stated single purpose, data collection disclosures and release changes** under the 2026 Web Store policy.

### Risk
The tool can flag inconsistencies but cannot determine policy approval with certainty. Privacy-policy interpretation must stay conservative and evidence-based.

### Verdict
**Advance.** Strongest Wave 12 concept.

---

## 2. Atlassian Marketplace pre-submission trust/security checker

### Problem
Atlassian's current Marketplace submission process combines partner verification, privacy/security disclosures, vulnerability/security requirements and app-level checks. Enterprise-facing Forge apps can also target trust programs such as Atlassian Enterprise Certified. Small app developers need to know whether the evidence/configuration they already have is ready before entering formal review.

### Product
A pre-submission CLI/workspace that validates an app manifest/configuration against a versioned checklist and lets the developer map required submission evidence: security/privacy tab answers, egress declarations, data-residency claims, support/security contacts, partner-verification prerequisites and selected AEC readiness items. It produces a source-linked readiness report, not certification.

### Distribution
Atlassian Marketplace developer search, Forge communities, GitHub CLI and partner consultants.

### Monetization hypothesis
Free basic checklist; CA$20–40 one-off detailed readiness report; CA$15–30/month for teams maintaining multiple apps/release evidence.

### Competition
Atlassian already performs official approval/security scans and provides built-in eligibility checks for some programs. The surviving wedge is **before formal submission**: consolidating distributed requirements/evidence into one developer-controlled readiness pass.

### Risk
Official workflows can change quickly and Atlassian may expand native preflight tooling. The product must never imply guaranteed approval/certification.

### Verdict
**Advance.** Good marketplace-specific operations niche.

---

## 3. Chrome extension permission-change release preflight

### Problem
Adding or broadening permissions can trigger user reapproval/disable flows and policy scrutiny. Teams need to see the permission delta before releasing an extension update.

### Product
Diff two extension manifests/releases and classify added/removed permissions, host scope changes, optional-to-required changes and likely user-visible reapproval implications. Link every finding to current Chrome policy/docs.

### Distribution
GitHub Action/CLI, extension developer search and CI integration.

### Monetization hypothesis
Free local diff; CA$5–15/month scheduled release checks/history.

### Competition / scope finding
Useful, but it fits naturally as a high-value feature inside candidate 1 rather than a separate business.

### Verdict
**Merge into candidate 1.**

---

## 4. Atlassian Forge egress/data-residency configuration audit

### Problem
Forge apps that use egress or remote infrastructure have data-residency and trust implications.

### Competition / scope finding
Atlassian already provides programmatic eligibility checks for Runs on Atlassian and Forge handles residency automatically for hosted storage in many cases. A standalone residency checker is therefore too weak.

### Verdict
**Merge into candidate 2** as one readiness section.

---

## 5. AI-generated content label coverage checker

### Problem
EU AI Act Article 50 transparency obligations now apply, creating marking/labelling requirements for certain AI-generated/deepfake content.

### Finding
The problem is real and current, but it depends heavily on content type, provider/deployer role and publishing workflow. CMS/social/content platforms can absorb much of the operational burden. A generic checker would have difficulty proving whether content is AI-generated or correctly marked.

### Verdict
**Hold.** Potential feature/vertical opportunity later, but weaker than the developer-platform ideas.

## Stage 3 ranking

1. Chrome extension privacy/disclosure vs manifest preflight
2. Atlassian Marketplace pre-submission trust/security checker
3. AI-generated content label coverage checker — hold, not advanced

## Advance to Stage 4

Advance the top two plus a third distinct candidate from the pool: **SaaS plan-feature removal impact inventory**, focused narrowly on identifying business workflows dependent on features being removed/downgraded from a vendor plan before renewal.

## Verification record

- Last verified: 2026-10-19
- Stage 3 status: complete
- Stage 5: out of scope
