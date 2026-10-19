---
title: Revenue Investigation — Wave 11 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest Wave 11 concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 256
permalink: /projects/notes/revenue-investigation-wave-11-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-11, stage-4, acquisition]
---

# Wave 11 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — CRA product support-period vs dependency-support checker

### Core promise
Show a manufacturer whether important software/runtime dependencies are scheduled to lose upstream support before the end of the product support period it has committed to under the EU Cyber Resilience Act.

### MVP plan
- Import CycloneDX/SPDX SBOM or simple dependency CSV.
- User enters product version, market date and declared support-end date.
- Normalize top-level components plus selected runtimes/base images/frameworks.
- Query/version-match only authoritative or clearly sourced lifecycle data.
- Flag dependencies with known upstream EOL before the product support end date.
- Separate confirmed mismatch, unknown lifecycle and review-needed findings.
- Optional public-disclosure check for support-end month/year consistency.
- Export engineering-risk/evidence report with source dates.
- Never declare CRA compliance/noncompliance.

### Likely stack
- Python rules/matching engine.
- Local CLI plus lightweight web upload.
- Versioned lifecycle-source adapters.
- Optional scheduled portfolio monitoring later.

### Pricing hypothesis
- Free: one product/SBOM check.
- CA$10–25: one-off portfolio report.
- CA$15–40/month: recurring support-window monitoring and history.

### Semi-automated acquisition pipeline
1. Monitor official CRA guidance plus authoritative upstream lifecycle sources for supported component families.
2. Queue lifecycle-source changes for human verification before changing risk rules.
3. Publish factual search pages around CRA support periods, dependency EOL and product-lifetime planning.
4. Free local/web check becomes the primary inbound acquisition surface.
5. Use public package/lifecycle datasets only for market sizing and supported-ecosystem prioritization.
6. For controlled validation in a future chat, create synthetic product/SBOM examples showing clear support-window mismatches.
7. If direct outreach is used later, target only clearly relevant product manufacturers, keep it low-volume/manual-approved, and make no compliance accusations.
8. Route recurring portfolio/MSP interest to the owner.

### Main risks
- Lifecycle data is incomplete for many proprietary components.
- Product support-period determination itself is contextual and cannot be automated safely.
- CRA platforms may expand into this feature.

### Stage 4 verdict
**Highest-priority Wave 11 candidate.**

---

## Rank 2 — Microsoft Graph / Entra deprecated endpoint and auth source scanner

### Core promise
Scan a codebase/configuration for Microsoft Graph and Entra patterns that are deprecated, retired or require migration, then point developers to the exact official replacement guidance.

### MVP plan
- CLI/GitHub Action.
- Detect known Graph endpoint paths, API-version references and SDK major versions.
- Detect selected Entra auth/config patterns that can be identified statically.
- Versioned rule pack with retirement/deprecation dates and migration links.
- Exact file/line evidence where possible.
- Classify findings as definite match vs runtime/tenant review required.
- JSON/SARIF output for CI integration.
- Never request/store tenant secrets.

### Likely stack
- TypeScript or Python scanner.
- YAML/JSON Microsoft lifecycle rules.
- GitHub Action + local CLI.
- Optional multi-repo dashboard later.

### Pricing hypothesis
- Free: local/single-repo scan.
- CA$10–25/month: scheduled multi-repo scans/history/team policies.
- Consultant/MSP tier for client portfolios.

### Semi-automated acquisition pipeline
1. Monitor official Microsoft Graph deprecation/version pages and Entra retirement notices.
2. Convert candidate notices into scanner rules only after human verification.
3. Publish retirement-specific pages such as legacy Graph security alerts migration checks.
4. Free GitHub Action/CLI is the primary acquisition channel.
5. Use public GitHub search only to measure prevalence of supported deprecated patterns, never to auto-open issues/PRs.
6. Generate factual examples using Microsoft/public demo repositories or synthetic code.
7. In any future validation chat, direct contact remains low-volume/manual-approved and secondary to GitHub/search discovery.
8. Route multi-repo or consultant interest to the owner.

### Main risks
- Many Entra issues require tenant telemetry, not just source analysis.
- Microsoft migration tooling may expand.
- Static string matching could create false positives without parser-aware checks.

### Stage 4 verdict
**Strong product-led developer-tool candidate.**

---

## Rank 3 — AI model migration regression-test pack

### Core promise
When an AI model is being retired, verify whether a candidate replacement still satisfies the application's own acceptance criteria before production cutover.

### MVP plan
- Local CLI/config-driven harness.
- User defines old model, candidate replacement and a fixture set.
- Run deterministic checks for structured-output/schema validity, tool/function calls, response status, latency, token usage and cost.
- Allow user-defined exact/regex/JSON assertions.
- Optional semantic scoring is explicitly separate and opt-in.
- Generate side-by-side migration report and CI pass/fail thresholds.
- Provider credentials remain local/CI secrets.
- Import model-retirement metadata from existing deprecation tools rather than rebuilding that registry.

### Likely stack
- Python/TypeScript CLI.
- Provider adapters for OpenAI, Anthropic, Gemini/Vertex, Bedrock/Azure as demand warrants.
- YAML test fixtures.
- GitHub Action for CI.

### Pricing hypothesis
- Open-source/local core.
- CA$10–30/month: hosted history, team dashboards, scheduled re-runs and trend comparisons.
- Usage-based hosted runs if customers do not want CI setup.

### Semi-automated acquisition pipeline
1. Consume current model-retirement feeds from existing open-source deprecation registries/tools.
2. Generate migration-specific search pages and example test packs for major announced retirements.
3. Free local CLI/GitHub Action drives product-led acquisition.
4. Monitor public developer discussions/issues for recurring migration failure modes and add deterministic assertion templates.
5. Use synthetic fixtures and public examples for demos; never collect customer prompts/data by default.
6. For future validation, target maintainers already using model-deprecation Actions and present the migration-testing tool as the next step after detection.
7. Keep any direct outreach small, factual and manually approved; primary acquisition should be GitHub/search/integration partnerships.
8. Route team/history/hosted-run interest to the owner.

### Main risks
- General LLM evaluation platforms are substitutes.
- Provider API costs complicate hosted pricing.
- Semantic behavior cannot be reduced to a universal pass/fail test; users must define their own acceptance criteria.

### Stage 4 verdict
**Promising operational tool if positioned as migration acceptance testing, not generic LLM evaluation.**

## Wave 11 conclusion

Top three:

1. CRA product support-period vs dependency-support checker
2. Microsoft Graph / Entra deprecated endpoint and auth source scanner
3. AI model migration regression-test pack

Wave 11 adds product-lifecycle compliance engineering, Microsoft identity/API migration tooling and AI-model migration QA without duplicating the increasingly crowded generic CRA/SBOM or model-deprecation scanner categories.

## Verification record

- Last verified: 2026-10-19
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
