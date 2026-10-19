---
title: Revenue Investigation — Wave 9 Stage 3 Deep Investigation
summary: Deep investigation of five Wave 9 finalists after competition and official-policy checks.
section: notes
doc_type: note
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: High Director
order: 247
permalink: /projects/notes/revenue-investigation-wave-9-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-9, deep-investigation]
---

# Wave 9 Stage 3 — Deep Investigation

## 1. AWS service-sunset exposure scanner for IaC

### Problem
AWS now publishes lifecycle states, end-of-support dates, migration guidance and even open lifecycle datasets. The information problem is therefore largely solved. The remaining operational problem is determining which lifecycle events actually affect a team's deployed architecture or infrastructure code.

### Product
A local CLI/GitHub Action that scans Terraform and CloudFormation for resources associated with AWS services/features entering maintenance, sunset or end-of-support. It outputs exact file/resource references, deadline, lifecycle state and the official AWS migration/source link.

### Distribution
GitHub Marketplace, Terraform/AWS search traffic, release-specific pages and free local CLI.

### Monetization hypothesis
Free single-repo scan; CA$10–25/month for organization history, multi-repo scanning and recurring lifecycle reports.

### Competition
AWS provides lifecycle trackers, datasets and migration guidance, including sample account scanners, but the current review did not identify a strong lightweight product focused specifically on **source/IaC exposure mapping**. The wedge is repo impact, not lifecycle data.

### Risks
Not every use of a service is statically visible in IaC. Rules need precise scope and must avoid implying that every service-name match means production exposure.

### Verdict
**Advance.** Strongest Wave 9 concept.

---

## 2. Canadian Value-Added evidence/calculation workspace

### Problem
Canada's strategic Buy Canadian procurement policy now applies at a lower $5M threshold, substantially expanding the number of covered procurements. Canadian Value-Added can account for 25% of evaluation and offerors may need a line-item breakdown plus evidence supporting the Canadian value claimed.

Official policy defines Canadian Value-Added differently for goods and services and can include qualifying Canadian R&D, sales/marketing, manuals, customization, installation/support, warehousing/distribution/logistics, training and after-sales service. False or unsupported attestations can have serious procurement consequences.

### Product
A conservative self-serve worksheet/workspace that:

- imports offer line items;
- separates goods/services and mandatory Canadian materials;
- records claimed Canadian Value-Added amounts and supporting evidence references;
- calculates the policy's published CVA percentage/score scenarios;
- flags lines without evidence;
- exports a working evidence pack aligned to the official attestation structure.

It must not decide whether a good legally qualifies as Canadian or provide CUSMA origin determinations.

### Distribution
Search traffic around Canadian Value-Added, Buy Canadian bids and attestation forms; procurement communities; downloadable free calculator as product-led acquisition.

### Monetization hypothesis
Free single-offer calculator; CA$15–30 one-off evidence workbook/export; CA$15–39/month for saved offers/evidence library/history.

### Competition
Current Canadian tender-screening products focus primarily on bid fit, requirements and compliance matrices. The review did not identify a strong dedicated CVA calculation/evidence workspace.

### Risks
Policy interpretation is sensitive and sector-specific validation methods may evolve. Every calculation must be tied to user-entered assumptions and official definitions rather than automated legal conclusions.

### Verdict
**Advance.** Fresh policy-driven niche with clear document burden.

---

## 3. Federal Vendor Performance Management supplier evidence organizer

### Problem
PSPC's Vendor Performance Management policy is now active and expanding. Covered supplier performance is scored around contractual obligations such as cost, schedule, quality and management, with scorecards reviewed in SAP Business Network. Finalized performance can inform future bid evaluations.

Small suppliers may have the operational evidence scattered across emails, change records, acceptance notes, schedule updates and issue logs when a scorecard is received.

### Product
A supplier-side evidence workspace that maps a contract's performance dimensions to factual supporting records:

- contract milestones and approved changes;
- delivery/acceptance dates;
- quality/defect evidence;
- issue and corrective-action logs;
- customer approvals/communications;
- scorecard review history;
- dated evidence index for response/dispute preparation.

It does not predict a government score or automate objections.

### Distribution
Search around Canada VPM supplier scorecards, government-contractor communities and a free evidence checklist/template.

### Monetization hypothesis
CA$10–25 per active contract/month or CA$29–59 one-off evidence pack for a scorecard review.

### Competition
General vendor-performance software is aimed at buyers/procurement departments. The niche here is **supplier-side evidence readiness for the Canadian federal VPM process**. Current CanadaBuys guidance explains how suppliers review scorecards but does not organize the underlying evidence for them.

### Risks
Small addressable market and slow procurement cycles. The product must remain an evidence organizer, not a legal/dispute advisory service.

### Verdict
**Advance.** Narrow but differentiated and recurring for active federal contractors.

---

## 4. EU PID carrier-export transformation tool

### Problem
From 1 November 2026, relevant EU e-commerce declarations require merchant and manufacturer product identifiers. Merchant catalog structures do not always match carrier/import-declaration formats.

### Finding
The need is current, but shipping providers are already adding automatic PID handling and dedicated Shopify/catalog checkers are appearing. A generic transformation layer risks becoming carrier-specific integration work.

### Verdict
**Hold.** Better as a feature within a shipping platform than an independent first product unless a widely used unsupported carrier format is identified.

---

## 5. Buy Canadian solicitation applicability checker

### Problem
The Buy Canadian framework contains thresholds, sector/policy conditions and evaluation methods that suppliers need to recognize quickly.

### Finding
The official policy and supplier Q&A are reasonably explicit, while current tender-screening tools already assess bid requirements. A standalone applicability checker would be too narrow and overlaps broader tender screening.

### Verdict
**Hold/drop as standalone.** Applicability rules could be a discovery feature feeding the CVA workspace.

## Stage 3 ranking

1. AWS service-sunset exposure scanner for IaC
2. Canadian Value-Added evidence/calculation workspace
3. Federal Vendor Performance Management supplier evidence organizer

## Advance to Stage 4

Advance those three only.

## Verification record

- Last verified: 2026-10-19
- Stage 3 status: complete
- Stage 5: out of scope
