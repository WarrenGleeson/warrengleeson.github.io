---
title: Revenue Investigation — Wave 9 Stage 4 Implementation Plans
summary: Stage 4 implementation, validation and acquisition plans for the three strongest Wave 9 concepts. No Stage 5 development or testing is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 248
permalink: /projects/notes/revenue-investigation-wave-9-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-9, stage-4, acquisition]
---

# Wave 9 Stage 4 — Implementation Plans

Planning only. No customer testing, ads, payments, outreach campaigns or product development should be executed from this chat.

## Rank 1 — AWS service-sunset exposure scanner for IaC

### Core promise
Scan Terraform/CloudFormation and show which AWS services/features in the codebase are entering maintenance, sunset or end-of-support, with exact source references and official migration guidance.

### MVP plan
- Local CLI and GitHub Action.
- Parse Terraform and CloudFormation resource types plus selected module/service references.
- Versioned lifecycle dataset sourced from official AWS Product Lifecycle information and official service notices.
- Map affected resources to lifecycle state, announcement date, end-of-support date and migration guide.
- File/resource-level evidence and confidence level.
- Ignore unsupported guesses: unknown resources are marked unclassified, not affected.
- Optional JSON/SARIF output for CI tooling.

### Likely stack
- Python or TypeScript parser/rules engine.
- Versioned JSON/YAML lifecycle mapping.
- GitHub Action + local CLI.
- Optional hosted multi-repo history later.

### Pricing hypothesis
- Free: local/single-repository scan.
- CA$10–25/month: scheduled multi-repo scans, history and organization dashboard.
- Optional MSP tier for multiple client repositories.

### Semi-automated acquisition pipeline
1. Monitor AWS Product Lifecycle pages, service availability announcements and official lifecycle datasets.
2. Diff new lifecycle notices into rule proposals and require human verification before release.
3. Generate search pages for specific transitions such as “Amazon DevOps Guru end of support Terraform scan.”
4. Free GitHub Action/CLI acts as the primary acquisition channel.
5. Use public GitHub code search only for aggregate market sizing and supported-resource prioritization; do not automatically contact repository owners.
6. For future controlled validation, generate factual scan examples from public demo/sample repos or voluntarily supplied repositories.
7. If direct outreach is ever used, keep it low-volume, manually approved and compliant; continuous cold outreach is not part of the intended model.
8. Route opt-in organization/MSP interest to the owner.

### Main risks
- IaC does not reveal every runtime dependency.
- AWS lifecycle terminology/services can be granular; mapping must be conservative.
- AWS's own lifecycle tooling could expand into repo scanning.

### Stage 4 verdict
**Highest-priority Wave 9 candidate.**

---

## Rank 2 — Canadian Value-Added evidence/calculation workspace

### Core promise
Help Canadian federal suppliers calculate, document and organize their own claimed Canadian Value-Added for a bid using the published government methodology and evidence references.

### MVP plan
- Import line items from CSV/XLSX or enter manually.
- Separate goods, services and mandatory Canadian materials.
- User records offer value, claimed Canadian Value-Added and evidence reference per line.
- Calculate published CVA percentage/score scenarios using user-entered solicitation weighting.
- Flag missing evidence and totals that do not reconcile.
- Generate a working line-item evidence schedule aligned to the official attestation form.
- Preserve source-policy version/date.
- Never determine CUSMA origin, legal Canadian-good status or eligibility automatically.

### Likely stack
- Browser-first spreadsheet-style web utility.
- Deterministic calculation engine.
- Local/browser processing for free tier where practical.
- Optional account/history only for repeat users.

### Pricing hypothesis
- Free: calculator/sample offer.
- CA$15–30: one-off evidence workbook/report.
- CA$15–39/month: saved offers, evidence library and revision history.

### Semi-automated acquisition pipeline
1. Monitor CanadaBuys Buy Canadian policy, supplier Q&A and compliance-framework revisions.
2. Diff official changes and require human review before updating rules/templates.
3. Publish factual search pages for Canadian Value-Added calculation, attestations and bid evidence requirements.
4. Free calculator becomes the primary inbound acquisition path.
5. Use public CanadaBuys solicitation data to identify which sectors/solicitations actually include CVA criteria and prioritize examples/content.
6. Create synthetic sample bids showing calculation mechanics only; never claim a real bidder's goods/services qualify without evidence.
7. For future validation, public supplier directories may be used to identify relevant companies, score fit and prepare factual examples, but any contact must be controlled, compliant and manually approved.
8. Route qualified repeat users or procurement-advisor partnership interest to the owner.

### Main risks
- High consequence if users mistake the tool for legal/origin advice.
- Sector-specific evidence methodologies may evolve.
- Addressable market is tied to covered Canadian federal procurements.

### Stage 4 verdict
**Strong policy-driven self-serve niche if positioned strictly as calculation/evidence organization.**

---

## Rank 3 — Federal Vendor Performance Management supplier evidence organizer

### Core promise
Give Canadian federal contractors a structured evidence file for upcoming or received Vendor Performance Management scorecards across cost, schedule, quality and management.

### MVP plan
- Create one workspace per covered contract.
- Record contract milestones, approved amendments/change orders, delivery/acceptance events and issue/corrective-action records.
- Attach/link factual supporting documents and communications.
- Organize evidence under the relevant VPM performance dimensions.
- Maintain dated review/scorecard history.
- Generate a neutral evidence index for scorecard review or response preparation.
- Never predict the government's score, draft legal objections or alter source evidence.

### Likely stack
- Lightweight document/evidence SaaS.
- Object metadata + links rather than mandatory document uploads where possible.
- Scheduled milestone/review reminders.

### Pricing hypothesis
- CA$29–59 one-off scorecard evidence pack.
- CA$10–25/month per active contract.
- Small contractor team plan for several concurrent contracts.

### Semi-automated acquisition pipeline
1. Monitor official Canada VPM policy, implementation plan and supplier guidance for expansion dates or scorecard changes.
2. Maintain a public applicability timeline by department/method of supply based only on official sources.
3. Publish search pages and free templates around VPM scorecard evidence preparation.
4. Use CanadaBuys award/public contract data to estimate the number of suppliers likely to encounter VPM; do not infer confidential scores.
5. Discover public federal-contractor directories for market sizing and fit scoring.
6. Create synthetic example evidence packs that demonstrate structure without using confidential contract material.
7. In any future validation chat, outreach must be low-volume, factual, manually approved and compliant; primary long-term acquisition should be search/referrals/procurement-advisor channels.
8. Triage inbound questions and alert owner only for qualified active-contract interest.

### Main risks
- Small/narrow market and government contracting cycles.
- Evidence may contain sensitive commercial information; strong privacy/security design would be necessary in Stage 5.
- General document-management tools are substitutes if workflow differentiation is weak.

### Stage 4 verdict
**Narrow but differentiated operational tool for active federal contractors.**

## Wave 9 conclusion

Top three:

1. AWS service-sunset exposure scanner for IaC
2. Canadian Value-Added evidence/calculation workspace
3. Federal Vendor Performance Management supplier evidence organizer

Wave 9 adds cloud lifecycle risk and two newly expanded Canadian procurement workflows without returning to generic bid-generation or cold-outreach-heavy services.

## Verification record

- Last verified: 2026-10-19
- Stage 4 status: complete
- Stage 5: explicitly out of scope for this chat
