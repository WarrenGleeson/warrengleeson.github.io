---
title: Revenue Investigation — Wave 16 Stage 3 Deep Investigation
summary: Deep investigation of the strongest construction and field-trade ideas after direct competition checks.
section: notes
doc_type: note
status: active
created: 2026-10-20
updated: 2026-10-20
last_verified: 2026-10-20
owner: High Director
order: 275
permalink: /projects/notes/revenue-investigation-wave-16-stage-3-deep-investigation/
tags: [revenue-investigation, research, wave-16, deep-investigation, construction]
---

# Wave 16 Stage 3 — Deep Investigation

## 1. Contractor rebate-document / invoice preflight

### Problem
Contractors frequently provide customers with documents used for utility/government rebate applications. Current BC Hydro programs can require exact invoice fields, proof of payment, model information, permits, photographs, contractor forms and, for some heat-pump projects, heat-load calculation documentation. Missing or inconsistent information creates customer callbacks, delayed rebates and resubmissions.

### Product
A contractor-facing preflight tool that checks the documents the contractor is about to give the customer against a versioned program checklist. Initial scope would be a deliberately small set of BC programs such as residential heat-pump and EV-charger rebates.

Checks could include:
- required contractor/customer/invoice fields;
- paid/balance evidence;
- equipment make/model references;
- permit/reference numbers;
- expected photos/forms;
- application-deadline calculation;
- missing heat-load summary/report where required;
- a clean customer handoff checklist.

It does not decide eligibility or submit the rebate.

### Distribution
Search around BC rebate invoice requirements, contractor associations, electricians/HVAC installers and a free single-document checker.

### Monetization hypothesis
Free one-document check; CA$5–10 per completed rebate pack; CA$15–30/month for small contractors handling recurring installs.

### Competition
Rebate administrators publish guides and sample invoices, while full contractor CRMs exist. Current research did not surface a strong exact self-serve product focused on **preflighting contractor-generated rebate evidence before customer submission** across selected BC programs.

### Risk
Program requirements change frequently and some fields depend on customer eligibility. Rules must be source-versioned and limited to document completeness, not eligibility advice.

### Verdict
**Advance.** Strongest Wave 16 candidate.

---

## 2. WorkSafeBC subcontractor clearance evidence tracker

### Problem
WorkSafeBC states that a hiring business should obtain clearance before and after subcontracted work because it can become liable for unpaid premiums. The official clearance-letter tool generates the evidence, including letters for multiple firms, but contractors still need to remember which subcontractor/project periods are covered and preserve before/after evidence.

### Product
A small prime-contractor workspace that tracks subcontractor legal name/account number, project/contract dates, last clearance check, GoldStar advance-clearance date where applicable, and stored/link-referenced clearance letters. It flags projects missing pre-work or post-work evidence and creates a closeout checklist.

### Distribution
BC construction/search traffic, bookkeeping/accounting partners, contractor associations and a free spreadsheet/import template.

### Monetization hypothesis
Free up to 5 subcontractors; CA$10–20/month for active contractor portfolios; one-off project closeout report option.

### Competition
WorkSafeBC already provides the actual status/letter lookup and broad safety/compliance platforms exist. The niche is not replacing WorkSafeBC—it is **contract-period evidence administration for small prime contractors**.

### Risk
Very geographically narrow. Automated retrieval may not be available or appropriate, so the initial workflow may require users to upload/reference official letters themselves.

### Verdict
**Advance.** Narrow but concrete recurring administrative pain.

---

## 3. Retrospective T&M revenue-leak audit

### Problem
Dedicated field-ticket products already capture labour/material/equipment and signatures, and construction AP tools can reconcile tickets against invoices. But smaller subcontractors may still have a pile of signed PDF/paper tickets plus invoices at month-end and need to answer a simpler question: **which approved extras never made it onto an invoice, or were billed at different quantities/rates?**

### Product
Upload approved T&M tickets, agreed rate sheet and invoice export/PDF. The checker links ticket numbers/jobs, compares labour/material/equipment quantities and rates, and outputs:
- approved ticket missing from billing;
- partially billed ticket;
- rate/markup mismatch;
- duplicate billing candidate;
- invoice line without supporting ticket.

The product is retrospective audit/reconciliation only, not field capture.

### Distribution
Search around unbilled T&M/change orders, construction bookkeepers and subcontractor finance communities.

### Monetization hypothesis
CA$10–25 per month-end audit or CA$20–40/month recurring small-contractor plan.

### Competition
FieldTicket, SubTrack and Vergo already address adjacent ticket capture/reconciliation. The surviving wedge is low-commitment **upload-and-audit for contractors that do not want to replace their field workflow**.

### Risk
Document extraction and matching can be messy; competition could easily extend into retrospective audit. Manual confirmation would be needed for ambiguous matches.

### Verdict
**Advance cautiously.** Real pain, but weaker differentiation than ranks 1–2.

---

## Dropped after deeper review

### Generic field-ticket capture
Direct current competitors already solve on-site ticket creation, signatures, photos and unbilled-extra tracking.

### Equipment-rental invoice/off-rent audit
Current dedicated products already compare rental invoices with agreements, rates and off-rent evidence.

### HVAC commissioning / equipment handover
Current commissioning, O&M and asset-handover tools already handle startup records, warranties, manuals, model/serial data and QR access.

### Electrical panel schedule tooling
Current free and paid tools already create, share and audit panel schedules and labels.

## Stage 3 ranking

1. Contractor rebate-document / invoice preflight
2. WorkSafeBC subcontractor clearance evidence tracker
3. Retrospective T&M revenue-leak audit

## Advance to Stage 4

Advance those three only.

## Verification record

- Last verified: 2026-10-20
- Stage 3 status: complete
- Stage 5: out of scope
