---
title: Revenue Investigation — Wave 15 Stage 3 Deep Investigation
summary: Deep investigation of Wave 15 finalists after direct competition checks across TLS automation readiness and browser-deprecation operations.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 271
permalink: /projects/notes/revenue-investigation-wave-15-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-15, deep-investigation]
---

# Wave 15 Stage 3 — Deep Investigation

## 1. Shorter-TLS-lifetime manual-renewal exposure scanner

### Problem
Public TLS certificate maximum validity periods are on a scheduled path toward 47 days by 2029. The certificate-management market is mature, but organizations still have certificates renewed through manual tickets, vendor portals, bespoke DNS validation or unclear ownership. Those are the assets most likely to fail as renewal frequency increases.

### Product
Import a certificate/domain inventory or scan user-authorized public endpoints, classify each certificate by issuer, validity, apparent automation method, CAA/DNS prerequisites and responsible owner, then flag certificates whose renewal path appears manual, undocumented or dependent on validation steps that will not scale safely under shorter validity periods.

### Distribution
Search around 47-day certificates/ACME migration, PKI consultant communities and a free inventory report.

### Monetization hypothesis
Free small-domain audit; CA$20–50 one-off readiness report; CA$15–40/month recurring portfolio checks/history.

### Competition
Full CLM products from major PKI/security vendors are abundant. The wedge is a low-cost **pre-CLM readiness and ownership audit** for teams that first need to discover which renewals are still manual before choosing automation tooling.

### Risk
Automation state cannot always be inferred externally; user-supplied process/owner data may be required. The tool must not claim a certificate is manually renewed merely because ACME evidence is absent.

### Verdict
**Advance.** Strongest Wave 15 concept.

---

## 2. `unload` behavior replacement / regression test pack

### Problem
Chrome completed deprecating the `unload` event in October 2026. Source detection is available in DevTools, but finding an event listener does not show what user-visible behavior breaks when the handler no longer runs. Sites may have relied on unload for saving state, analytics beacons, resource cleanup or application-specific workflows.

### Product
A Playwright/browser test harness that runs a user-defined navigation/close/background fixture set with unload disabled/default behavior, captures network/storage/state differences, and produces a before/after regression report. Optional source scan identifies candidate unload handlers, but the primary value is behavioral testing.

### Distribution
GitHub Marketplace/CLI, search around Chrome unload breakage and framework/vendor migration communities.

### Monetization hypothesis
Open-source/local test pack; CA$10–25/month hosted CI history/multi-site scheduled checks.

### Competition
Chrome DevTools can identify unload usage, and vendor guidance explains replacements, but the current review did not identify a strong purpose-built product centered on **behavioral regression testing of workflows that previously depended on unload**.

### Risk
The opportunity may shrink as sites complete migration. User-defined fixtures are required for meaningful behavioral tests.

### Verdict
**Advance.** Timely but likely a narrower/shorter-lived developer-tool market.

---

## 3. Browser-deprecation CI gate

### Problem
Browser vendors publish deprecations/removals through release notes, DevTools warnings and platform-status feeds. Teams with large web codebases still need to know which announced removals actually appear in their repository and whether current tests exercise the affected paths.

### Product
A repository/CI scanner with a deliberately small versioned ruleset for high-confidence browser removals. It identifies exact API/CSS/markup patterns, links them to announced removal versions, and can optionally run selected smoke tests against Stable and pre-Stable Chromium. It is not a generic browser-compatibility database.

### Distribution
GitHub Marketplace, web developer search and release-specific pages.

### Monetization hypothesis
Free local scanner; CA$10–25/month scheduled multi-repo scans/history/team policy rules.

### Competition
Generic compatibility linters and browser-testing platforms exist. The surviving wedge is **deadline-oriented deprecation inventory tied to source evidence and CI**, with high-confidence rules only.

### Risk
Broadening too far would collide with mature compatibility tooling. The product must stay focused on announced removals/deprecations with deadlines.

### Verdict
**Advance cautiously.** More durable than a single-deprecation tool if scope remains disciplined.

---

## 4. Client-side XSLT dependency / migration scanner

### Competition finding
An exact current competitor now exists: `xslt-migrate-check` scans local projects for `XSLTProcessor`, XML stylesheet processing instructions and XSL files, produces migration-readiness reports and suggested fixes specifically for Chrome 158's November 2026 removal.

### Verdict
**Drop.** No clean standalone wedge remains.

---

## 5. Certificate renewal owner inventory

### Finding
Ownership mapping is important, but it is most valuable as a section of candidate 1 rather than a separate business.

### Verdict
**Merge into candidate 1.**

## Stage 3 ranking

1. Shorter-TLS-lifetime manual-renewal exposure scanner
2. `unload` behavior replacement / regression test pack
3. Browser-deprecation CI gate

## Advance to Stage 4

Advance those three only.

## Verification record

- Last verified: 2026-10-19
- Stage 3 status: complete
- Stage 5: out of scope
