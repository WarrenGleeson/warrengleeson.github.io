---
title: "EirePolitic Instagram Growth: Insights and Measurement"
description: "Plan for creating the analytics feedback loop needed to measure audience acquisition and content performance."
group: "Notes"
order: 61
---

# Insights and Measurement

## Objective

Create a reliable measurement layer that connects Instagram performance data to EirePolitic publications so future growth decisions are evidence-based.

## Questions to answer

- What Instagram Insights data is available through the current account/API setup?
- Which metrics are available at account, media, carousel, and Reel level?
- How can published Instagram media be mapped back to existing publication IDs and content-series metadata?
- What retention period and polling frequency are appropriate?
- What data already exists in AWS/DynamoDB or other stores?
- What minimum schema is needed before experiments begin?

## Evidence to inspect

- Instagram publishing code and stored publication metadata.
- Current AWS data stores used by the pipeline.
- Any Meta Graph API permissions already configured.
- Existing post IDs / media IDs / schedule records.
- Existing analytics or reporting code.
- Current Meta documentation for Insights fields and API limits.

## Candidate metrics

- non-follower reach;
- accounts reached;
- profile visits;
- follows attributable to content where available;
- follows per 1,000 accounts reached;
- shares;
- saves;
- comments;
- likes;
- Reel plays, watch time, and retention;
- carousel interactions where exposed;
- publication time, content family, hook variant, topic, and format.

## Investigation tasks

- [ ] Audit current publishing metadata and identifiers.
- [ ] Determine exact Insights fields available to the account.
- [ ] Define publication-to-performance join strategy.
- [ ] Define minimum viable analytics schema.
- [ ] Define ingestion frequency and backfill strategy.
- [ ] Define derived growth KPIs.
- [ ] Define reporting views needed for experiments.
- [ ] Identify privacy, API quota, and retention constraints.

## Candidate implementation path

Do not implement until the investigation above is complete.

Likely implementation components may include:
- a scheduled Insights ingestion job;
- durable storage for time-series media metrics;
- a mapping between Instagram media IDs and EirePolitic publication IDs;
- a derived metrics layer;
- a lightweight dashboard or query/reporting interface.

## Success criteria

The system should make it possible to answer, with data:
- Which content families generate the most non-follower reach?
- Which posts convert reach into follows most efficiently?
- Which cover/hook variants produce better acquisition?
- Which formats generate disproportionately high shares/saves?
- Which posting times or topic classes materially change performance?

## Risks / safeguards

- Do not change production publishing behaviour during analytics work.
- Do not expose tokens, credentials, or private account data.
- Do not create a complex analytics platform before validating the minimum useful dataset.

## Questions for the user

Only ask if repository/API inspection cannot answer them.

Examples:
- Is there historical Instagram Insights export data outside the repository?
- Is there an existing preferred reporting surface such as Power BI?

## Handoff instructions for future LLM chats

Inspect the production repository and AWS-related documentation first. Do not invent schema names, tables, Lambdas, or permissions before verifying current infrastructure. Produce a concrete data model and ingestion plan before proposing code changes.
