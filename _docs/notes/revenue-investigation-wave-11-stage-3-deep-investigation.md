---
title: Revenue Investigation — Wave 11 Stage 3 Deep Investigation
summary: Deep investigation of five Wave 11 finalists after direct competition checks across AI lifecycle, Microsoft Graph/Entra and Cyber Resilience Act operations.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 255
permalink: /projects/notes/revenue-investigation-wave-11-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-11, deep-investigation]
---

# Wave 11 Stage 3 — Deep Investigation

## 1. CRA product support-period vs dependency-support checker

### Problem
The Cyber Resilience Act requires manufacturers to determine and publish a product support period and continue effective vulnerability handling during it. A product can therefore commit a manufacturer to support years beyond the upstream support life of operating systems, frameworks, runtimes, libraries or components it depends on.

### Product
Import a product SBOM plus declared support-end date. The tool compares component/runtime support windows where authoritative lifecycle data is available and highlights dependencies whose upstream support ends before the product's committed support period. Output is an engineering-risk/evidence report, not a legal compliance determination.

### Distribution
CRA/support-period search traffic, SBOM/dev-security communities and a free local CLI/web checker.

### Monetization hypothesis
Free single-product check; CA$10–25 one-off portfolio report; CA$15–40/month recurring component/support-window monitoring.

### Competition
Current CRA platforms track SBOMs, vulnerabilities and support periods, but the current review did not identify a strong lightweight product whose central task is **support-period mismatch analysis between a manufacturer's commitment and upstream component lifecycle**.

### Risk
Reliable lifecycle data varies by component. Unknown support windows must remain unknown rather than inferred.

### Verdict
**Advance.** Strongest Wave 11 wedge.

---

## 2. Microsoft Graph / Entra deprecated endpoint and auth source scanner

### Problem
Microsoft Graph regularly retires APIs and supports only the latest major SDK. The legacy security alerts endpoint stopped returning data on October 15, 2026, and Entra has also retired authentication behaviors such as service-principal-less app authentication. Teams need to determine whether their code/config still references retired or soon-to-retire patterns.

### Product
A repository scanner/GitHub Action for Microsoft Graph and Entra integrations. It detects known deprecated endpoints, SDK versions, selected auth patterns and configuration references, then maps them to official migration guidance and retirement dates.

### Distribution
GitHub Marketplace, Microsoft developer search and release/retirement-specific pages.

### Monetization hypothesis
Free single-repo scanner; CA$10–25/month multi-repo history/scheduled checks; MSP/consultant tier later.

### Competition
Microsoft provides excellent migration docs but the current review did not surface a strong focused repo-impact scanner covering Graph endpoints + Entra auth patterns. Generic deprecation scanners are broader and less context-specific.

### Risk
Some auth exposure is tenant/runtime-specific and cannot be proved from source alone. Findings need definite vs review-needed classifications.

### Verdict
**Advance.** Strong product-led developer-tool candidate.

---

## 3. AI model migration regression-test pack

### Problem
Model deprecation detection itself is now crowded: multiple current GitHub Actions already find retiring model IDs across major providers. The harder problem comes after detection—teams need to know whether the recommended replacement preserves their application's required structured outputs, tool calls, latency/cost bounds and task-specific behavior.

### Product
A local migration harness that runs a developer-supplied fixture set against old and candidate replacement models, then compares deterministic outputs: JSON/schema validity, tool/function call names/arguments, refusal/success states, latency and token/cost metrics. Optional semantic evaluation must be user-configured and clearly separated from deterministic checks.

### Distribution
GitHub Marketplace/CLI, AI developer search and integration with existing deprecation scanners rather than competing with them.

### Monetization hypothesis
Open-source local harness; CA$10–30/month hosted history/team dashboards or pay-per-run CI service.

### Competition
General LLM evaluation platforms exist, but the narrow trigger—**model retirement migration acceptance testing**—is more operationally specific. It can consume deprecation data from existing tools instead of maintaining its own registry.

### Risk
API usage costs are borne somewhere, and semantic equivalence cannot be guaranteed. Product must emphasize user-defined acceptance tests rather than claiming one model is universally equivalent.

### Verdict
**Advance.** Better wedge than another deprecation scanner.

---

## 4. Multi-provider AI model sunset source scanner

### Competition finding
The category is already crowded by current tools including `llm-sunset`, AppliedBenchmark Sunset and LLM Model Deprecation Check, all of which scan repositories and maintain provider retirement registries.

### Verdict
**Drop as standalone.** Use these tools/data as inputs to candidate 3 instead.

---

## 5. CRA support-end-date disclosure checker

### Problem
CRA user information must include support-period information, and manufacturers need to make support expectations clear.

### Finding
A public-page/document checker could verify whether month/year support information appears consistently, but this is likely a feature of a broader CRA support-period workspace. By itself the willingness-to-pay case is weak.

### Verdict
**Merge into candidate 1** as an optional published-disclosure consistency check.

## Stage 3 ranking

1. CRA product support-period vs dependency-support checker
2. Microsoft Graph / Entra deprecated endpoint and auth source scanner
3. AI model migration regression-test pack

## Advance to Stage 4

Advance those three only.

## Verification record

- Last verified: 2026-10-19
- Stage 3 status: complete
- Stage 5: out of scope
