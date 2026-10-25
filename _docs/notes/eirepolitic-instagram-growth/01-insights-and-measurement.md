---
title: "EirePolitic Instagram Growth: Insights and Measurement"
description: "Detailed plan for creating the analytics feedback loop needed to measure audience acquisition and content performance."
group: "Notes"
order: 61
---

# Insights and Measurement

## Status

**Planning state:** detailed investigation/implementation guide prepared.  
**Production changes:** none.  
**Priority:** highest. This workstream should precede most growth optimisation because it establishes the feedback loop used to judge the other experiments.

## Objective

Build a reliable, low-maintenance measurement layer that connects Instagram account/media performance to EirePolitic's existing publication records and future growth-experiment metadata.

The system should answer practical acquisition questions rather than merely collect statistics:

- Which EirePolitic formats reach people who do not already follow the account?
- Which posts turn reach into profile visits and followers?
- Which formats create shares, saves, and reposts?
- Which cover, hook, CTA, subject, posting-time, and format variants outperform their alternatives?
- Which performance differences persist at 72 hours, 7 days, and 30 days rather than reflecting post age?

Likes are useful diagnostic data but are not the primary optimisation target.

---

## Current repository state already established

The production source of truth is `warrengleeson/Eirepolitic-data-pipeline`.

The existing publishing system gives this workstream a strong starting point.

### Canonical publication ledger

Production publishing uses DynamoDB table:

`eirepolitic-publications`

The table is the canonical publication/schedule control plane. Existing documentation explicitly separates it from EventBridge Scheduler, which is only the live execution mirror for scheduled publications.

Relevant production documentation/code:

- `instagram/PUBLISHING.md`
- `docs/operations/instagram_publishing_standard.md`
- `publishing/dynamodb_ledger.py`
- `publishing/dynamodb_runtime.py`
- `publishing/execution.py`
- `publishing/meta_http_client.py`
- `infra/publishing/dynamodb.yml`
- `infra/publishing/lambda.yml`

### Publication identity already exists

A `PublicationRequest` already records:

- `publication_id`;
- `publication_version`;
- `project_id`;
- `period`;
- asset package;
- exact caption;
- parsed hashtags and caption mentions;
- Instagram post type;
- collaborators/tags/location/first-comment options where used.

This means the analytics layer should reuse the existing publication identity rather than create a second content-ID system.

### Permanent Instagram media ID is already persisted

The publisher's durable execution record stores:

`published_media_id`

against the corresponding publication ID/version after Meta returns the permanent published media result.

This is the key architectural finding for this workstream.

The primary join should therefore be:

```text
EirePolitic publication_id + publication_version
        ↓
existing execution record
        ↓
published_media_id
        ↓
Instagram media object / media Insights
```

No caption matching, timestamp guessing, or image matching should be required for posts published through the current production path.

### Current Meta client

The production publisher currently:

- uses `graph.facebook.com`;
- stores `ig_user_id` and access token in the existing Instagram publishing secret;
- pins Graph API `v25.0` by default;
- contains publishing operations only.

As of the October 2026 review, Meta's latest Graph API version is `v26.0`, released July 29, 2026. `v25.0` remains supported until July 29, 2028.

**Do not upgrade the production publisher merely to implement analytics.** API-version migration is a separate compatibility decision. The Insights implementation should first work against the production-compatible version unless a current Meta requirement makes that impossible.

### No existing Insights ingestion layer found

No established Instagram Insights collector, analytics schema, or recurring performance-ingestion workflow was identified in the inspected repository state.

That should be treated as a greenfield analytics layer beside the working publisher, not as a reason to refactor the publisher.

---

## Architecture principle

**Keep measurement read-only with respect to production publishing.**

The analytics system may read publication/execution records and Meta Insights, but it should not be able to approve, schedule, edit, or publish Instagram content.

Recommended logical flow:

```text
Meta Instagram API
        ↓ read-only Insights/media/profile calls
Instagram Insights collector
        ↓
Analytics storage
        ↓
Derived KPI/reporting layer
        ↓
Growth experiments / 30-60-90 plan

Existing eirepolitic-publications table
        ↓ read-only publication/media-ID lookup
Instagram Insights collector
```

The existing publisher remains unchanged unless a later implementation task explicitly requires a narrowly scoped integration.

---

## Architectural decision gates

These decisions materially affect AWS/runtime design and must be confirmed before implementation.

### Decision A — analytics storage

**Recommended:** create a separate analytics store rather than writing high-frequency performance snapshots into `eirepolitic-publications`.

Working name:

`eirepolitic-instagram-analytics`

Why this is preferred:

- preserves `eirepolitic-publications` as the publication control plane;
- avoids analytics writes affecting a production-critical table;
- allows retention/indexing to evolve independently;
- makes removal/rebuild of derived analytics data safer;
- creates a clean boundary between immutable publishing authority and mutable performance observations.

Do not create this table until explicitly approved.

### Decision B — collector runtime

**Recommended:** a separate, small scheduled Lambda rather than adding an Insights action to `eirepolitic-instagram-publisher`.

Working name:

`eirepolitic-instagram-insights`

The collector should receive only:

- read permission on relevant publication-ledger items;
- write permission on the analytics store;
- read permission for the existing Instagram credential secret if that credential is reused;
- CloudWatch logging permissions.

It should not receive publication/scheduling permissions.

### Decision C — Meta credential

**Preferred sequence:**

1. inspect the permissions/scopes on the credential already used successfully for publishing;
2. determine whether Insights permission is already present;
3. if yes, reuse that secret read-only from the collector;
4. if not, determine whether the existing Meta app/token can be safely re-authorised with the required Insights permission;
5. do not rotate or replace the working publishing credential merely for tidiness;
6. create a separate credential only if required by Meta permission constraints or security separation.

Never paste the access token into chat, GitHub, logs, or documentation.

### Decision D — first reporting surface

Do not build a complex dashboard before the data model is proven.

Recommended sequence:

1. raw/normalised analytics storage;
2. deterministic KPI calculation;
3. a simple machine-readable export and human-readable summary;
4. only then decide whether Power BI or another dashboard is justified.

---

## Phase 0 — read-only capability audit

This phase should happen before infrastructure is created.

### Goal

Establish exactly what the current EirePolitic Meta account/token can read in October 2026.

Meta changes metrics, names, breakdown compatibility, and permissions over time. The implementation must therefore discover actual supported capabilities rather than hard-code assumptions from old documentation.

### Capability audit checklist

- [ ] Confirm current `ig_user_id` can be read using the existing secret without exposing its value publicly.
- [ ] Confirm current token remains valid.
- [ ] Confirm account is an Instagram professional account supported by the Insights API.
- [ ] Determine whether the current login path is the existing Facebook Login path implied by `graph.facebook.com`.
- [ ] Confirm required Insights scope(s) are present.
- [ ] Read basic account fields such as `username`, `followers_count`, and `media_count` where supported.
- [ ] Read the account's media list.
- [ ] Read one known image post.
- [ ] Read one known carousel album.
- [ ] Read one Reel when EirePolitic has a suitable Reel available.
- [ ] Probe the supported media Insights metrics for each product/type.
- [ ] Probe account-level Insights metrics and available breakdowns.
- [ ] Record unsupported metric/type combinations rather than treating them as fatal errors.
- [ ] Record observed API response latency/availability for recent media.
- [ ] Record current Graph API version and relevant deprecation dates.

### Metrics expected to be candidates in the current API

The capability probe should test, rather than assume, the following.

**Account/profile:**

- `followers_count` from the IG User object;
- `media_count`;
- `views`;
- `reach`;
- `accounts_engaged`;
- `total_interactions`;
- `likes`;
- `comments`;
- `saves`;
- `shares`;
- `reposts`;
- `follows_and_unfollows`;
- `profile_links_taps`;
- available follower/non-follower and media-product breakdowns.

**Feed image/carousel media:**

- `views`;
- `reach`;
- `likes`;
- `comments`;
- `saved`;
- `shares`;
- `reposts`;
- `total_interactions`;
- `follows` where supported;
- `profile_visits` / `profile_activity` where supported.

**Reels:**

Test all applicable metrics above plus current Reel-specific metrics such as:

- average watch time;
- total watch time;
- skip-rate/early-retention metric if exposed to the account/API version.

Do not use deprecated `impressions`/`plays` as primary new fields. Modern Meta Insights has moved toward `views`, and metric support varies by API version and media type.

### Capability matrix artifact

The implementation chat should produce a checked-in, non-secret capability record similar to:

```yaml
verified_at: 2026-XX-XX
graph_version: v25.0
login_path: facebook_login
account:
  followers_count: supported
  reach: supported
  reach_follow_type_breakdown: supported
media:
  IMAGE:
    reach: supported
    follows: supported
  CAROUSEL_ALBUM:
    reach: supported
    follows: supported
  REELS:
    reach: supported
    avg_watch_time: supported
```

Exact values are examples only. Populate from live read-only tests.

---

## Phase 1 — establish the baseline and historical mapping

### Goal

Create a useful pre-experiment baseline before changing content strategy.

### Pipeline-published posts

For current production publications:

1. read publication control metadata;
2. locate the corresponding execution record;
3. read `published_media_id`;
4. query the Instagram media object;
5. store its timestamp, media type/product type, permalink, and supported performance metrics;
6. preserve the EirePolitic `publication_id`, version, `project_id`, and `period` as dimensions.

### Older/manual Instagram posts

The account may contain media created before the current publisher became canonical.

The baseline process should also enumerate available account media from Meta.

For each media item:

- if its media ID matches an existing publication execution, attach the canonical EirePolitic publication identity;
- otherwise retain it as an unmapped historical media record, for example `source=instagram_unmapped`;
- do not invent a publication ID for old manual content;
- optionally enrich unmapped records later if a reliable mapping exists.

This allows historical content to contribute to the baseline without contaminating the production publication ledger.

### Backfill window

Do not assume a fixed historical retention period from memory. At implementation time:

1. verify Meta's current account/media Insights retention and query-window limits;
2. retrieve the maximum useful history available without excessive API calls;
3. prioritise at least the most recent 60-90 days if available because that is sufficient to establish an initial baseline;
4. retain longer media history where inexpensive and supported.

---

## Proposed analytics data model

This is a planning model, not yet an approved DynamoDB schema.

### 1. Media registry / latest state

One logical record per Instagram media object.

Suggested fields:

```text
instagram_media_id
publication_id              nullable for historical/unmapped media
publication_version         nullable
project_id                  nullable
period                      nullable
source                      pipeline | instagram_unmapped
media_type
media_product_type
permalink
published_at_utc
caption_hash                optional; do not duplicate full captions unless needed
post_type                   image | carousel | reel | story where applicable
first_seen_at_utc
last_collected_at_utc
next_collection_at_utc
collection_state
```

### 2. Media metric snapshots

Store timestamped observations rather than only overwriting a latest total.

Suggested fields:

```text
instagram_media_id
captured_at_utc
post_age_hours
views
reach
likes
comments
saved
shares
reposts
total_interactions
follows
profile_visits
profile_activity
reel_avg_watch_time_ms
reel_total_watch_time_ms
reel_skip_rate
raw_metric_presence
api_version
```

Fields unsupported for a media type should be null/absent, not zero.

### 3. Daily account snapshot

Suggested fields:

```text
account_id
snapshot_date
followers_count
media_count
views
reach
accounts_engaged
total_interactions
likes
comments
saves
shares
reposts
follows
unfollows
profile_links_taps
reach_followers
reach_non_followers
reach_unknown
views_followers
views_non_followers
views_unknown
api_version
```

Only populate breakdown fields that the live capability audit confirms.

### 4. Experiment/content metadata

Do not add experiment fields to the publication approval fingerprint merely to support analytics.

Instead maintain a logically separate growth-metadata record keyed to `publication_id`/version.

Candidate dimensions:

```text
experiment_id
variant
content_family
subject_area
hook_archetype
headline_style
cover_style
carousel_slide_count
caption_variant
caption_length_bucket
cta_variant
topicality              topical | evergreen | procedural
format                   image | carousel | reel
scheduled_local_hour
scheduled_weekday
collaboration_type
```

Where possible, derive these values automatically from existing factory/project metadata. Only manually label variables that cannot be inferred reliably.

### Why snapshots are required

A lifetime metric taken today cannot fairly be compared with a post published yesterday.

Experiments should therefore compare standard post-age checkpoints.

Recommended checkpoints:

- ~72 hours — early discovery signal;
- ~7 days — primary short-term comparison point;
- ~30 days — long-tail result;
- ~90 days — optional final/evergreen observation.

A 24-hour observation may be retained operationally but should not be the primary experiment decision point because Meta metrics can be delayed/revised.

---

## Phase 2 — automated collection cadence

### Account-level collection

Run once daily.

Because recent values may arrive late or be revised, re-fetch a short trailing window rather than ingesting only one immutable “yesterday” value.

Recommended starting rule:

- refresh the most recent 3 calendar days on every run;
- upsert by account + metric date;
- record `captured_at_utc` and API version.

Adjust after observing actual Meta latency.

### Media-level collection

Do not query every historical media item every day.

Recommended starting cadence:

| Post age | Collection cadence | Purpose |
|---|---|---|
| 0-3 days | daily | early discovery trajectory |
| 4-14 days | every ~3 days | short-term stabilisation |
| 15-30 days | weekly | long-tail comparison |
| 31-90 days | at final scheduled checkpoint(s) | evergreen/final value |
| >90 days | stop by default | minimise API calls |

The registry can store `next_collection_at_utc` so each scheduled collector run fetches only due media.

### New-publication discovery

The production table currently does not have an analytics-specific index over published execution records.

For the initial low-volume system, the collector may perform a **read-only bounded scan** for execution items containing `published_media_id`, then register newly observed media in the analytics store.

This is preferable to changing the working publisher solely to emit analytics events.

If scale later makes scans inefficient, reassess one of these options:

- a dedicated GSI;
- an EventBridge publication-success event;
- a minimal registration write from the publisher.

Do not introduce those changes pre-emptively.

---

## KPI definitions

All rate metrics should define their denominator explicitly.

### Primary acquisition KPIs

**Follows per 1,000 reached**

```text
(media_follows / media_reach) * 1000
```

Use only if the live API exposes reliable media-attributed follows for that media type.

If not available, do not fabricate attribution from account follower growth.

**Profile visits per 1,000 reached**

```text
(media_profile_visits / media_reach) * 1000
```

Where supported.

**Profile-visit-to-follow conversion**

```text
media_follows / media_profile_visits
```

Where both metrics are supported.

### Discovery KPIs

**Non-follower reach share**

```text
non_follower_reach / total_reach
```

Use at the level at which Meta actually exposes the follower/non-follower breakdown. Do not assume a per-media breakdown if the API exposes it only at account level.

**Views per reached account**

```text
views / reach
```

Useful for repeat exposure, not as an acquisition metric by itself.

### Distribution/utility KPIs

**Shares per 1,000 reached**

```text
(shares / reach) * 1000
```

**Saves per 1,000 reached**

```text
(saved / reach) * 1000
```

**Reposts per 1,000 reached**

```text
(reposts / reach) * 1000
```

### Reel KPIs

Where supported:

- average watch time;
- average watch time divided by video duration;
- early skip rate;
- shares per 1,000 reached;
- follows per 1,000 reached.

### Account growth KPIs

- net follower change per day/week;
- gross follows and unfollows where available;
- follower count trend;
- non-follower reach trend;
- profile-link activity trend.

Account-level changes should be treated as supporting evidence, not attributed to a single post unless Meta explicitly provides that attribution.

---

## Experiment comparison rules

The analytics layer should enforce several rules to avoid misleading conclusions.

1. Compare posts at the same age checkpoint where possible.
2. Use rates per reach for share/save/follow comparisons, not raw totals alone.
3. Separate feed/carousel/Reel comparisons unless the experiment explicitly tests format.
4. Retain subject area and topicality as dimensions because a breaking political event can swamp a visual-design experiment.
5. Do not treat one viral/outlier post as sufficient evidence.
6. Record experiment/control metadata before results are examined where practical.
7. Keep raw observations so derived KPI formulas can be changed later without recollecting data.
8. Preserve unsupported/missing metrics as missing values rather than converting them to zero.

---

## Reporting outputs required before a dashboard

The first useful reporting layer should be able to produce:

### Weekly account summary

- start/end follower count;
- gross follows/unfollows where available;
- reach and non-follower reach;
- views;
- shares/saves/reposts;
- profile activity;
- top acquisition posts by standardised checkpoint.

### Per-publication performance table

Minimum columns:

```text
publication_id
project_id
published_at
media_type
experiment_id
variant
72h_reach
72h_follows_per_1000
72h_shares_per_1000
72h_saves_per_1000
7d_reach
7d_follows_per_1000
7d_shares_per_1000
7d_saves_per_1000
30d_reach
30d_follows_per_1000
```

Use only metrics that capability testing confirms.

### Experiment summary

For each experiment:

- control/treatment definition;
- sample sizes;
- median and mean results;
- individual-post results;
- major topical/contextual confounders;
- decision: continue, reject, or gather more observations.

Do not auto-declare statistical significance unless the test design and sample size justify it.

---

## Proposed repository structure for implementation

Do not create these paths until architecture is approved. They are a suggested destination for a future implementation PR.

```text
analytics/
└── instagram_insights/
    ├── __init__.py
    ├── client.py
    ├── capabilities.py
    ├── models.py
    ├── collector.py
    ├── backfill.py
    ├── store.py
    └── kpis.py

infra/
└── analytics/
    └── instagram_insights.yml

docs/
└── operations/
    └── instagram_insights.md
```

A manual/read-only GitHub Actions workflow may be useful for capability testing or backfill, but recurring production collection should not depend on a developer remembering to dispatch a workflow.

---

## Implementation sequence for a future LLM chat

### Stage 1 — repository and live-state audit

1. Read this document.
2. Read the canonical Instagram publishing documentation in `Eirepolitic-data-pipeline`.
3. Inspect current `main` before making changes; this plan may be older than the live repository.
4. Inspect current CloudFormation and runtime configuration.
5. Verify current Meta Graph API documentation and current latest/supported API versions.
6. Verify the production secret name/configuration without retrieving or displaying the secret value.
7. Perform the read-only Insights capability probe.
8. Record the supported metric matrix.

**Stop before infrastructure changes if the existing credential lacks required Insights permission.** Explain exactly what additional permission/re-authorisation is required.

### Stage 2 — confirm architecture

Present the user with the minimum material decisions:

- separate analytics DynamoDB table vs another store;
- separate scheduled Lambda vs another runtime;
- credential reuse/re-authorisation approach;
- initial backfill window.

Do not ask about details that repository/live inspection already answers.

### Stage 3 — implementation PR

After approval:

1. create branch;
2. implement read-only Meta Insights client;
3. implement data models/storage;
4. add tests using fixtures/mocked API responses;
5. add CloudFormation with Retain/PITR/encryption as appropriate;
6. add IAM least privilege;
7. add capability/backfill command or workflow;
8. add collector Lambda/schedule;
9. add operations documentation;
10. open PR;
11. do not deploy automatically unless explicitly approved.

### Stage 4 — controlled deployment

After explicit deployment approval:

1. deploy analytics storage only;
2. verify table/resources;
3. deploy collector with publishing permissions absent;
4. run health/capability check;
5. ingest a small number of known media IDs;
6. validate data against Instagram/Meta Business Suite manually for several posts;
7. run historical backfill;
8. enable recurring collection;
9. verify first scheduled run;
10. document observed API limitations.

### Stage 5 — growth-experiment integration

Only after ingestion is trustworthy:

1. define experiment metadata format;
2. label upcoming content experiments;
3. generate 72-hour and 7-day comparison reports;
4. feed results into the other audience-growth workstreams;
5. add dashboarding only if it materially reduces analysis effort.

---

## Validation requirements

Before the analytics data is treated as trustworthy, compare at least several records against the Instagram Professional Dashboard or Meta Business Suite.

Validate:

- media ID / permalink;
- published timestamp;
- reach;
- views;
- shares;
- saves;
- follower/account totals;
- any media-attributed follow/profile-visit metric used in KPIs.

Record expected differences caused by Meta's latency or estimated metrics.

A successful API response alone is not sufficient validation.

---

## Cost and workload expectations

### Setup effort

**Medium.** Most work is one-time API/IAM/storage implementation and validation.

### Recurring manual effort

**Very low** once stable. The intended steady state is automatic ingestion plus a short weekly review.

### Monetary cost

Expected to be **very low** at EirePolitic's current scale if implemented with a small Lambda, on-demand DynamoDB, and bounded API polling. Confirm projected AWS cost before deployment, but this should not require a paid analytics SaaS product.

### Automation potential

**Very high.** This is one of the strongest candidates for complete automation in the growth programme.

---

## Risks and safeguards

### Production publishing risk

Analytics must not become part of the critical publish path. A broken Insights API call must never stop a scheduled Instagram publication.

### Credential risk

Do not expose, rotate, or replace working publishing credentials without a demonstrated requirement.

### API drift

Meta metrics and permissions change. Store API version with observations and maintain a capability matrix.

### False attribution

Do not infer that account-level follower growth came from a specific post when the API does not provide media-level attribution.

### Metric revisions

Meta can revise or delay recent values. Use repeated snapshots and fixed post-age checkpoints.

### Data-model overengineering

Start with the minimum fields necessary for the growth programme. Raw metric observations plus stable publication metadata are more valuable than a large dashboard schema.

---

## Success criteria for this workstream

This workstream is complete when EirePolitic can answer, with reproducible data:

1. What was the account's follower and non-follower discovery trend over the last week/month?
2. Which content families generate the most reach outside the existing audience?
3. Which publications produce the highest follow conversion where measurable?
4. Which publications produce the highest share and save rates?
5. How did experiment variant A compare with variant B at the same post-age checkpoint?
6. Do Reels create incremental discovery compared with carousels once tested?
7. Are topical posts outperforming procedural or evergreen posts after controlling for post age?
8. Which posting times/content categories deserve further testing?

The collection and reporting process should require little or no manual data entry.

---

## Information that may still require the user

Most implementation questions should be answered from GitHub, AWS state, and Meta's API.

Ask the user only if needed for one of these unresolved items:

- whether historical Instagram Insights exports exist outside connected systems and should be imported;
- whether there is a strong preference for Power BI or another reporting surface after the core ingestion layer works.

Neither question blocks the technical baseline plan.

---

## Current recommendation

Proceed in this order:

1. perform the live read-only Meta Insights capability audit;
2. confirm whether the existing credential already has Insights permission;
3. obtain explicit approval for a separate analytics table and separate collector Lambda;
4. backfill the available recent account/media history;
5. automate daily account collection and age-based media snapshots;
6. validate the data against Meta's UI;
7. begin labelling growth experiments;
8. use 72-hour, 7-day, and 30-day checkpoints to drive the remaining growth workstreams.

This provides the measurement foundation without redesigning or risking the working publishing system.
