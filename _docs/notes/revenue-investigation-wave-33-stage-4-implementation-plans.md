---
title: Revenue Investigation — Wave 33 Stage 4 Implementation Plans
summary: Stage 4 implementation and acquisition plans for the strongest Salesforce AgentExchange/AppExchange concepts. No Stage 5 development is authorized here.
section: notes
doc_type: note
status: active
created: 2026-10-25
updated: 2026-10-25
last_verified: 2026-10-25
owner: High Director
order: 344
permalink: /projects/notes/revenue-investigation-wave-33-stage-4-implementation-plans/
tags: [revenue-investigation, research, wave-33, salesforce, stage-4]
---

# Wave 33 Stage 4 — Implementation Plans

Planning only. No development, AgentExchange/AppExchange submission, customer testing, payments or outreach should be executed from this chat.

## Rank 1 — Connected App -> External Client App migration readiness audit

### MVP
- Native Salesforce managed package, read-only wherever possible.
- Inventory accessible Connected Apps and relevant policies/usage metadata.
- Classify local/customer-managed vs packaged/vendor-owned integrations.
- Capture OAuth flow, scopes, callback URLs, policy posture and support/contact metadata where exposed.
- Flag apps whose migration is customer-controlled vs vendor-controlled.
- Build ECA migration checklist per app.
- Highlight unsupported OAuth patterns / settings requiring architecture review.
- Export an org-wide migration register and evidence pack.
- No secret rotation, migration or config mutation.

### Commercial model
- Free/light tier: limited inventory or first 3 apps.
- Paid via AgentExchange/AppExchange Checkout: roughly US$49–149/org/month or annual equivalent depending on org/app count.
- Consultant/multi-org tier later if demand exists.
- Salesforce currently takes 15% revenue share through Checkout.

### Acquisition
1. Search/listing keywords around Connected App migration, External Client App, Spring '26 and OAuth modernization.
2. Publish release-driven content tied to Salesforce's connected-app roadmap and eventual EOS announcements.
3. Free org summary should give enough value to justify installation.
4. Natural referral channel: Salesforce consultants, security architects and integration partners.
5. Position clearly against Salesforce's free configuration skills: this app inventories and prioritizes the **whole estate**.

### Main risks
- Salesforce may expand native migration tooling before broad EOS.
- Vendor-owned packaged apps may require vendor action outside customer control.
- Security review/listing cost means the app needs credible recurring value before build.

### Stage 4 verdict
**Best Salesforce concept to validate in a separate chat.**

---

## Rank 2 — Legacy Named Credential migration readiness audit

### MVP
- Native/read-only package.
- Inventory legacy Named Credentials plus modern Named Credentials/External Credentials.
- Capture endpoint/authentication metadata without reading secret values.
- Scan discoverable Apex/Flow/metadata references.
- Map permission-set/principal access dependencies.
- Flag legacy credentials with no clear modern replacement record.
- Detect duplicate endpoints/credential sprawl.
- Generate migration and rotation checklist per credential.
- Export source-linked evidence/report.
- No credential mutation or secret access.

### Commercial model
- Free basic inventory.
- Paid US$39–99/org/month or annual tier for full dependency analysis, history and recurring monitoring.
- Consultant/multi-org tier could improve economics.

### Acquisition
1. Exact-intent AppExchange/AgentExchange keywords around Legacy Named Credentials, External Credentials and Salesforce integration migration.
2. Publish migration checklists tied to future Salesforce deprecation/EOS notices.
3. Partner with integration consultants and security architects.
4. Strong privacy/security message: native, read-only, never reads credential values.

### Main risks
- Salesforce's own migration tooling may improve.
- Apex/Flow usage tracing can be incomplete.
- Enterprise buyers may expect deeper integration architecture advice than a self-serve app provides.

### Stage 4 verdict
**Strong second candidate with good security/compliance value.**

---

## Rank 3 — Queue / routing retirement dependency preflight

### MVP
- Native/read-only package.
- Queue picker.
- Show queue membership and supported objects.
- Count/list open records owned by queue.
- Inspect exposed Routing Configuration / Service Channel relationships.
- Search accessible Flow/metadata references to queue ID/name.
- Show recent assignment/routing activity where available.
- Allow admin to nominate replacement queue and generate migration checklist.
- Clearly classify unresolved dynamic routing dependencies.
- No ownership/routing mutation.

### Commercial model
- Free one-queue scan.
- Paid US$29–79/org/month for bulk queue inventory, history and retirement project reports.

### Acquisition
1. AppExchange search around queue cleanup, Omni-Channel queue consolidation, Service Cloud migration and routing administration.
2. Evergreen admin content rather than a one-time migration event.
3. Consultant/referral use during Service Cloud redesign projects.
4. Position against broad metadata tools by combining **live work + routing + metadata** in one operational retirement report.

### Main risks
- API coverage across Enhanced Omni-Channel can be incomplete.
- Dynamic Flow routing can make impact analysis uncertain.
- Lower urgency than the two platform-change candidates.

### Stage 4 verdict
**Good evergreen admin utility, but weaker economics/urgency than ranks 1–2.**

## Platform economics note

Salesforce is a materially heavier platform than Figma, Shopify or GitHub for small products. Current AgentExchange/AppExchange Checkout revenue share is 15%. Salesforce's listing guidance also cites a US$2,550 one-time security review and US$150 annual fee for paid apps. That means Salesforce ideas should target meaningful enterprise/admin value and recurring pricing rather than cheap micro-utilities.

## Wave 33 conclusion

Top three:
1. Connected App -> External Client App migration readiness audit
2. Legacy Named Credential migration readiness audit
3. Queue / routing retirement dependency preflight

Salesforce is still attractive because distribution, procurement and billing are deeply embedded, but the entry economics push us toward fewer, higher-value products. The best opportunities are platform-change readiness utilities where Salesforce itself creates the deadline and search demand.

## Verification record
- Last verified: 2026-10-25
- Stage 4 status: complete
- Stage 5: explicitly out of scope
