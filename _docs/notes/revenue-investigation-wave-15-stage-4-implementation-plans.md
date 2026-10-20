---
title: Revenue Investigation — Wave 15 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest Wave 15 concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 272
permalink: /projects/notes/revenue-investigation-wave-15-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-15, stage-4, acquisition]
---

# Wave 15 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — Shorter-TLS-lifetime manual-renewal exposure scanner

### Core promise
Identify public TLS certificates that are still operationally dependent on manual, undocumented or ownerless renewal processes before industry certificate lifetimes become too short for those workflows to remain reliable.

### MVP plan
- Accept a user-supplied domain/certificate inventory or authorized endpoint list.
- Collect public certificate metadata: issuer, SANs, validity window, chain and renewal cadence history where available.
- Record user-supplied renewal method, DNS/validation dependency, responsible owner and automation status.
- Flag certificates with no documented owner, manual-ticket renewal, bespoke validation steps, stale CAA/issuer assumptions or renewal cadence incompatible with future shorter lifetimes.
- Provide an ACME/automation-readiness checklist rather than implementing certificate issuance itself.
- Export a prioritized migration/readiness report with source dates and uncertainty labels.
- Never request or store private keys.

### Likely stack
- Python certificate/DNS inspection service.
- Browser dashboard plus CSV import/export.
- Optional scheduled public-endpoint rescans.

### Pricing hypothesis
- Free: small inventory/readiness audit.
- CA$20–50: one-off portfolio report.
- CA$15–40/month: recurring ownership/readiness monitoring.

### Semi-automated acquisition pipeline
1. Monitor CA/Browser Forum certificate-validity schedules plus major browser/root-program implementation notices.
2. Publish factual search pages around 200-day/100-day/47-day certificate transitions and ACME readiness.
3. Free readiness worksheet/scan is the primary inbound funnel.
4. Analyze opt-in portfolio issue types to prioritize CA/DNS/provider-specific guidance.
5. Use public certificate transparency/DNS data only for aggregate market research and user-authorized scans; do not mass-contact domain owners.
6. Produce synthetic/sample inventories showing manual-renewal failure modes.
7. Future outreach, if ever used, should remain low-volume/manual-approved and secondary to search/PKI consultant referrals.
8. Route multi-domain/MSP/consultant interest to the owner.

### Main risks
- Mature CLM vendors can move down-market.
- Renewal automation cannot always be inferred externally.
- Opportunity becomes less distinct once automation adoption is widespread.

### Stage 4 verdict
**Highest-priority Wave 15 candidate.**

---

## Rank 2 — `unload` behavior replacement / regression test pack

### Core promise
Show developers what actually breaks now that Chromium no longer fires `unload` handlers by default, rather than merely telling them that the code contains an unload listener.

### MVP plan
- Local Playwright-based CLI/test harness.
- Scan supported source files for `unload` handlers as candidate locations.
- User defines or records key navigation/close/background flows.
- Run flows under current Chromium default behavior and, where possible, comparison/legacy opt-out behavior.
- Capture network beacons, local/session storage, IndexedDB/state, navigation completion and user-defined assertions.
- Produce a regression report showing behavior differences and exact candidate source locations.
- Link to current Chrome migration guidance; do not auto-rewrite production code.

### Likely stack
- TypeScript + Playwright.
- YAML test-flow/assertion format.
- GitHub Action for CI.

### Pricing hypothesis
- Open-source/free local core.
- CA$10–25/month: hosted CI history, scheduled browser runs and team reporting.

### Semi-automated acquisition pipeline
1. Monitor Chromium unload/deprecation guidance and related browser adoption changes.
2. Publish search pages for concrete breakage patterns such as unsent analytics, unsaved state and cleanup workflows.
3. Free CLI/GitHub Action drives product-led acquisition.
4. Collect only opt-in anonymous failure categories to prioritize fixtures/templates.
5. Use open-source/sample applications for demonstrations.
6. Future validation can target maintainers reporting unload-related breakage in public issue trackers, but any contact must be manual and non-spammy.
7. Build partner/referral relationships with web migration consultants/framework communities rather than relying on ongoing cold outreach.
8. Route hosted/team CI interest to the owner.

### Main risks
- Time-limited market as migrations complete.
- Meaningful regression testing requires customer-specific flows.
- General browser-testing platforms could add equivalent templates.

### Stage 4 verdict
**Timely developer tool with a narrower commercial window.**

---

## Rank 3 — Browser-deprecation CI gate

### Core promise
Fail or warn in CI when a repository contains high-confidence browser APIs/features with an announced deprecation/removal deadline relevant to the project's target browsers.

### MVP plan
- Local CLI/GitHub Action.
- Maintain a deliberately small ruleset for announced browser removals with authoritative deadlines.
- Detect exact source/markup/CSS patterns where static matching is reliable.
- User selects target browser families/versions.
- Output file/line finding, deprecation date/removal version, severity and official migration source.
- Optional pre-Stable Chromium smoke-test hook for selected high-risk changes.
- SARIF/JSON output.
- Do not attempt to become a universal browser-compatibility linter.

### Likely stack
- TypeScript/Python static scanner.
- Versioned YAML rule packs.
- GitHub Action + optional hosted multi-repo history.

### Pricing hypothesis
- Free: local/single-repo scan.
- CA$10–25/month: scheduled multi-repo scans/history/team policy controls.

### Semi-automated acquisition pipeline
1. Monitor Chrome/Chromium deprecation/removal notices and selected Firefox/WebKit equivalents.
2. Convert only high-confidence announced removals into candidate rules, with human verification before release.
3. Publish release-specific pages for significant removals and migration deadlines.
4. Free CLI/GitHub Action is the primary discovery channel.
5. Use public GitHub search only for aggregate prevalence analysis and rule prioritization; no automatic issue/PR creation.
6. Demonstrate against open-source/sample repositories.
7. Any future direct contact remains manually approved and secondary to GitHub/search acquisition.
8. Route multi-repo/agency interest to the owner.

### Main risks
- Existing linters/compatibility services can overlap.
- Maintaining browser-specific rules can expand quickly.
- Static detection must stay conservative to avoid noisy CI.

### Stage 4 verdict
**Potentially durable if kept as a narrow deprecation-deadline gate rather than a generic compatibility tool.**

## Wave 15 conclusion

Top three:

1. Shorter-TLS-lifetime manual-renewal exposure scanner
2. `unload` behavior replacement / regression test pack
3. Browser-deprecation CI gate

Wave 15 adds certificate-automation readiness and browser-removal operations while deliberately rejecting crowded CLM, DMARC, PCI script-monitoring and exact XSLT migration-checker categories.

## Verification record

- Last verified: 2026-10-19
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
