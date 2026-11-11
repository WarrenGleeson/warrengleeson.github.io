---
title: "EirePolitic Instagram Growth: Cross-Platform and External Traffic"
description: "Detailed plan for using the public site and low-maintenance external channels to create additional discovery paths into EirePolitic content and Instagram."
group: "Notes"
order: 69
---

# Cross-Platform and External Traffic

## Status

**Planning state:** detailed investigation/implementation guide prepared.  
**Production changes:** none.  
**Priority:** medium; begin with the public-site opportunity, then test only one external social channel at a time.  
**Dependencies:** Reels/Repurposing determines whether vertical video can be syndicated; Insights/Measurement should measure Instagram outcomes; Profile Conversion determines whether Instagram is the desired destination for external traffic.

## Objective

Create additional discovery paths into EirePolitic without multiplying the operator's workload.

The preferred model is:

```text
one validated EirePolitic content package
        ↓
canonical public asset / source identity
        ↓
platform-specific lightweight adapter
        ↓
Instagram + selected external channels + public website
        ↓
measured referral / follower / engagement outcomes
```

The strategy should favour:

- first-party public pages;
- automated or near-automated syndication;
- reuse of existing images, charts, captions, and future Reel MP4s;
- channels with official publishing APIs;
- channels that can operate without daily manual community management;
- measurable traffic back to EirePolitic's public outputs and/or Instagram.

The strategy should **not** assume that EirePolitic must operate actively on every social platform.

---

# Current repository state already established

## No cross-platform publishing layer was found

The October 2026 repository review did not identify an established publishing integration for:

- Threads;
- Bluesky;
- LinkedIn;
- YouTube;
- TikTok;
- Facebook;
- another external social network.

The current automated social publishing system is Instagram-specific.

This is useful because a future cross-platform layer can be added deliberately instead of inheriting an undocumented multi-platform system.

## The documentation/public site already has a public-content surface

`warrengleeson.github.io/content.md` currently publishes `/content/` and contains:

- an embedded public Power BI report;
- an embedded Instagram post.

At the time of review, the Instagram embed is a **hard-coded specific post**, not a dynamically maintained “latest post” integration.

The site homepage already links to `/content/` under **Public outputs → Content**.

This means EirePolitic does not need to build a new public website from zero.

## The site homepage remains intentionally technical

The root homepage currently presents the site as:

> Eire Politic Knowledge Base

and describes technical documentation, repositories, systems, architecture, and development continuity.

That remains appropriate for the documentation site's existing role.

Therefore:

**do not rewrite the technical homepage merely to create an Instagram landing page.**

The growth strategy should instead evolve an existing public-output route or add a dedicated public-facing route.

## No public-site analytics integration was found

The inspected repository did not show an obvious Google Analytics, Plausible, Umami, Matomo, or similar tracking integration.

Therefore referral/link experiments should not assume website conversion tracking already exists.

Any analytics choice is a separate privacy/cost/architecture decision and should be approved before implementation.

---

# Strategic principle: syndicate assets, not workload

Cross-platform growth is useful only when additional channels consume content the pipeline already produced.

Bad model:

```text
Instagram post
+ bespoke Threads post
+ bespoke Bluesky post
+ bespoke LinkedIn article
+ bespoke YouTube edit
+ manual website entry
```

Preferred model:

```text
canonical structured content
        ↓
Instagram carousel
        ↓
short text/image social variant
        ↓
vertical video variant when available
        ↓
public website reference page
```

The source facts and editorial interpretation should remain canonical.

Platform adapters may change:

- length;
- image aspect ratio;
- number of images;
- CTA;
- link placement;
- hashtags/topic labels.

They should not introduce new unsupported political claims.

---

# Recommended channel priority

This is an operational priority, not a claim that one platform is universally “better.”

## Priority 1 — first-party public web surface

Why first:

- already exists;
- no algorithm dependency;
- useful as Instagram bio/link destination;
- supports external search/referrals;
- can host methodology/sources that do not fit social captions;
- can become the canonical destination shared across platforms;
- low recurring manual effort once automated.

## Priority 2 — Threads pilot

Why investigate early:

- official Meta Threads API supports programmatic publication;
- current API supports text, image, video, and carousel content;
- many Instagram assets can potentially be adapted with limited transformation;
- the pipeline already uses Meta infrastructure, although Threads requires its own authentication/app setup.

Do **not** assume the Instagram credential can simply be reused.

## Priority 3 — Bluesky pilot

Why investigate:

- official AT Protocol/Bluesky APIs allow programmatic posting;
- simple text/link/image-oriented content can be generated cheaply;
- low technical barrier to a small experiment.

Audience fit must be measured rather than assumed.

## Priority 4 — LinkedIn selective syndication

Best suited to:

- political-data methodology;
- public-policy data visualisations;
- civic-tech/project updates;
- evergreen explainers;
- research-oriented output.

Do not automatically syndicate every routine Instagram publication.

The current LinkedIn Posts API supports organic text, images, video, documents, and multi-image posts, but ordinary organic “carousel” content is not exposed as the same carousel post type used for sponsored content.

## Priority 5 — YouTube Shorts after Reel capability exists

Do not create a separate video-production workflow for YouTube.

Once Workstream 04 produces a canonical vertical MP4, YouTube becomes a low-incremental-cost distribution experiment because the YouTube Data API supports programmatic video uploads.

## Defer initially

### Facebook

Investigate only after confirming whether EirePolitic already has/needs a Facebook Page and whether current Meta account linking offers a genuinely low-maintenance route.

Do not create an additional page solely because cross-posting is technically possible.

### TikTok

Potentially relevant once vertical video exists, but defer until:

- Reel format is proven;
- current TikTok API/account requirements are audited;
- moderation/maintenance burden is understood.

### Additional niche networks

Do not add platforms unless an identifiable audience/distribution opportunity exists.

---

# Workstream A — public website / external landing surface

## Goal

Create a general-audience destination that can receive traffic from:

- Instagram profile link;
- Threads/Bluesky/LinkedIn;
- search engines;
- journalists/researchers;
- collaborators;
- shared links.

## Do not send general users to the technical homepage by default

The technical knowledge base serves a different audience.

The growth destination should answer:

1. What is EirePolitic?
2. What can I explore here?
3. Where is the latest useful content?
4. Where do the data/sources come from?
5. How do I follow EirePolitic?

## Architecture options

### Option A — evolve `/content/`

**Recommended simplest first option.**

The route already exists and is linked from the homepage.

Potential structure:

```text
EirePolitic public content

[short project explanation]

Latest / featured political information
- latest Bill Tracker
- latest polling
- latest explainers

Explore data
- Power BI / public datasets where appropriate

Follow
- Instagram
- future external channels

Sources / methodology
- public methodology link
```

Advantages:

- low setup;
- avoids adding another ambiguous site section;
- existing inbound link from homepage.

### Option B — create a dedicated `/eirepolitic/` or `/public/` landing page

Use only if `/content/` needs to remain a narrow embedded-content page.

This is cleaner for audience separation but adds another route/navigation concept.

### Decision gate

Before implementation, inspect current site usage and choose **one** public entry point.

Do not create both a new landing page and a redesigned `/content/` page unless they have clearly different purposes.

---

# Public-page content rules

The public landing/content surface should be written for a person who knows nothing about the pipeline.

Avoid:

- repository architecture;
- Lambda names;
- DynamoDB details;
- internal workflow states;
- “factory” terminology;
- development-agent references.

Use:

- Irish politics;
- legislation;
- Oireachtas;
- representatives;
- polling/data;
- public records;
- clear source/methodology links.

The technical docs can remain linked for people who want implementation detail.

---

# Replace hard-coded “latest Instagram post” behaviour

The current `/content/` page labels one embedded post as “Latest Instagram Post” while the permalink is fixed in source.

That creates maintenance risk as soon as new posts are published.

Future implementation should choose one of these approaches.

## Option 1 — generated latest-post metadata

A small build/deploy step receives the latest approved/published Instagram permalink and generates a data file such as:

```yaml
latest_instagram:
  publication_id: "..."
  permalink: "https://www.instagram.com/p/.../"
  published_at: "..."
```

The Jekyll page renders from that data.

Recommended if the site should continue embedding the actual latest post.

## Option 2 — remove the “latest” promise

Rename the section to:

`Featured Instagram Post`

and update it manually only when useful.

This is operationally simpler if a live latest-post feed offers little growth value.

## Option 3 — render a recent-content index

Instead of embedding Instagram itself, generate lightweight cards from EirePolitic publication metadata:

```text
headline
content family
date
thumbnail
Instagram link
source/methodology link
```

This is the strongest long-term first-party option because the site retains useful content even when Instagram's embed behaviour changes.

Do not implement the most complex option until it solves a demonstrated need.

---

# Public website search/SEO basics

The objective is not to become a large editorial website.

For public-facing pages, use basic discoverability hygiene:

- descriptive page titles;
- plain-language headings;
- concise descriptions;
- stable URLs;
- canonical topic wording;
- image alt text;
- useful internal links;
- public source/methodology links;
- social/Open Graph preview metadata where supported by the current Jekyll/theme setup.

The current `_config.yml` site description is explicitly technical.

Do not replace it globally without checking whether doing so would weaken the knowledge-base identity.

Prefer page-specific metadata or a dedicated public layout if needed.

---

# Public evergreen pages

Workstream 06 will create reusable evergreen explainers.

Do not immediately turn every Instagram carousel into a web article.

First test a small number of high-search/high-reference concepts.

Candidate public pages:

- `How a Bill becomes law in Ireland`;
- `What does Second Stage mean?`;
- `How to read a Dáil division`;
- `Percentage points vs percent change in polling`;
- `What EirePolitic speech-frequency data measures`.

A public page can contain:

- concise explanation;
- embedded/linked Instagram carousel;
- sources;
- related EirePolitic data;
- follow link.

This creates a durable resource that can be shared from multiple platforms.

---

# Website-to-Instagram strategy

External traffic does not automatically need to be sent away from the website.

Use an Instagram CTA where following provides recurring value.

Examples:

- `Follow EirePolitic on Instagram for new Bill Tracker posts and political-data explainers.`

Do not place aggressive social CTAs on technical documentation pages.

## Trackable links

Where privacy/analytics architecture permits, use consistent campaign parameters for outbound links from controlled channels.

Example logical campaign fields:

```text
source=website
medium=public_content
campaign=instagram_growth
content=second_stage_explainer
```

Do not expose internal IDs/secrets in URLs.

Because the current site has no established analytics layer, choose the web-analytics method before relying on these metrics.

---

# Workstream B — Threads

## Current technical capability

Meta's Threads API currently supports programmatic content creation/publishing with Threads-specific authentication.

Current documented media types include:

- text;
- image;
- video;
- carousel.

Current Meta API examples also expose features such as links/topic tags and reply controls.

This makes Threads one of the most technically compatible external channels for EirePolitic.

## Authentication boundary

Do not bolt Threads credentials into the Instagram publishing secret by default.

Threads uses its own app/authentication flow and permissions.

A future implementation should:

1. inspect whether a suitable Meta app already exists;
2. determine required Threads permissions/app-review status;
3. create a separate secret/config boundary if needed;
4. avoid changing working Instagram credentials.

## Content adaptation

### Bill Tracker

Possible Threads output:

```text
Three laws passed this session — what each one changes.

1. [plain-language subject]
2. [plain-language subject]
3. [plain-language subject]

Full sourced breakdown: [public/Instagram link]
```

Optional image/carousel attached.

### Polling

Suitable for:

- one chart;
- concise “what changed?” text;
- source/date;
- public link.

### Evergreen explainers

Strong candidate for a short multi-post thread only if that format is generated automatically.

Do not manually write long Threads threads as routine work.

## Threads pilot

Start with 6-10 automatically prepared posts across several weeks.

Do not change Instagram publication cadence.

Measure:

- Threads impressions/views/reach where API provides them;
- interactions;
- link clicks where measurable;
- Instagram profile/follower movement where attributable;
- manual moderation time.

Stop if the channel requires substantial ongoing conversational engagement to create value.

---

# Workstream C — Bluesky

## Current technical capability

Bluesky/AT Protocol provides an official API for creating `app.bsky.feed.post` records.

A basic post requires text and creation time; the protocol also supports richer embeds/media through its record/blob model.

This creates a technically straightforward automation opportunity.

## Best EirePolitic use

Start with:

- plain-language headline;
- one strong image/chart;
- source/public-page link;
- restrained tags/labels as appropriate to current Bluesky conventions.

Do not mirror long Instagram captions verbatim if the text format is unsuitable.

## Bluesky pilot

Use the same source content as the Threads pilot where practical.

Measure:

- post views/interactions where available;
- link referrals;
- profile/follower growth on Bluesky;
- downstream Instagram/public-site traffic;
- manual moderation time.

No assumption should be made in advance that Bluesky's political audience will convert to Instagram followers.

The experiment should answer that question.

---

# Workstream D — LinkedIn

## Why selective rather than comprehensive

LinkedIn is likely to be a better fit for some EirePolitic content than others.

Potentially suitable:

- methodology/data engineering outcomes presented publicly;
- civic-tech explainers;
- policy-data visualisations;
- evergreen institutional explainers;
- public Power BI/data outputs;
- major project/data releases.

Less suitable as a default:

- every Bill stage update;
- every party profile;
- routine feed-frequency content.

## Current technical capability

LinkedIn's current Posts API supports organic:

- text;
- images;
- video;
- documents;
- multi-image posts.

Publishing on behalf of an organisation requires appropriate organisation-page roles and API permission.

Do not assume such a page/account/API permission already exists.

## Document-post opportunity

If useful, a multi-slide EirePolitic explainer could eventually be converted to PDF and uploaded as a LinkedIn document post.

This is distinct from the Instagram carousel and should only be commissioned if test results justify it.

## LinkedIn pilot

Select 3-5 high-fit posts rather than syndicating everything.

Candidate types:

- public-data release;
- methodology explainer;
- legislative-process reference;
- Power BI/report update.

Measure:

- impressions;
- clicks/referrals;
- follows;
- meaningful professional/research engagement;
- manual time.

---

# Workstream E — YouTube Shorts

## Dependency

Do nothing until Workstream 04 produces a proven vertical MP4.

## Current technical capability

The YouTube Data API supports programmatic video uploads using OAuth and resumable upload flows.

Therefore the same canonical EirePolitic Reel MP4 can potentially be syndicated without a second video-editing workflow.

## Adaptation rules

Platform-specific fields may require:

- title;
- description;
- source links;
- thumbnail/cover handling;
- visibility settings;
- tags/metadata.

The underlying video must remain the same approved factual asset where possible.

## Pilot

Once Reels are proven:

- select 5-10 existing vertical videos;
- upload on a controlled schedule;
- do not create YouTube-only edits;
- record views, retention, subscribers, link traffic, and moderation burden.

Only continue if incremental reach justifies maintenance.

---

# Cross-platform content classes

Not every Instagram publication should leave Instagram.

Classify each content package.

## X1 — Instagram-only

Use when:

- format depends heavily on Instagram carousel behaviour;
- subject has little external reuse value;
- syndication would create clutter.

## X2 — image syndication

Suitable for:

- polling charts;
- single Bill summary;
- public-data card;
- evergreen reference card.

Potential channels:

- Threads;
- Bluesky;
- LinkedIn selectively.

## X3 — text/link syndication

Suitable for:

- current Bill status;
- short factual data update;
- new evergreen public page.

Potential channels:

- Threads;
- Bluesky;
- LinkedIn selectively.

## X4 — video syndication

Suitable after Reel pipeline exists.

Potential channels:

- Instagram Reels;
- YouTube Shorts;
- Threads video;
- other approved vertical-video channels later.

## X5 — public web reference

Suitable for:

- evergreen explainers;
- methodology;
- data dashboards;
- stable source/reference pages.

---

# Canonical content identity

Cross-platform automation should preserve one source identity across derived publications.

Do not create unrelated copies with no lineage.

Suggested logical fields:

```text
content_id
source_project_id
source_period
source_publication_id          nullable
content_family
canonical_headline
canonical_public_url           nullable
asset_package_id
```

Then record each distribution target separately:

```text
distribution_id
content_id
platform
platform_post_id
platform_url
variant_id
published_at_utc
status
external_caption_version
tracking_campaign
experiment_id
```

This enables questions such as:

- Which source asset produced the most total external discovery?
- Does Threads create referrals to Instagram?
- Do YouTube videos create subscribers but no Instagram traffic?
- Which platform is consuming manual time without producing useful audience?

---

# Architectural boundary

Do not generalise the working Instagram publisher prematurely.

## Recommended initial architecture

Use a separate **syndication/distribution adapter** around approved immutable content packages.

Conceptually:

```text
approved EirePolitic asset package
        ↓
Instagram publisher (existing)

        ↓ separate read-only handoff
external syndication adapters
  ├── Threads
  ├── Bluesky
  ├── LinkedIn
  └── YouTube
```

Reasons:

- Instagram publishing is already production-critical;
- external platforms have different auth/idempotency/rate-limit models;
- a Threads outage should not block Instagram;
- channels can be retired without destabilising core publishing.

If multiple channels later become permanent, consider a broader publication abstraction only after actual requirements are known.

This is an architecture decision requiring approval before code implementation.

---

# Syndication should be optional per publication

A content package should carry an explicit distribution policy such as:

```yaml
distribution:
  instagram: true
  public_web: true
  threads: auto
  bluesky: auto
  linkedin: false
  youtube: false
```

Do not infer that every new platform automatically receives every post.

Policies should be tied to content classes and proven channel fit.

---

# Platform-specific copy

Do not simply truncate Instagram captions.

Use a deterministic platform adapter.

Example conceptual model:

```yaml
platform_copy:
  threads:
    template_id: bill_summary_threads_v1
  bluesky:
    template_id: bill_summary_bluesky_v1
  linkedin:
    template_id: policy_data_linkedin_v1
```

All templates should draw from the same approved factual fields.

LLMs may assist commissioning templates, but routine publication should use deterministic/approved rules unless a separately governed generation layer is approved.

---

# Link strategy

Decide the destination according to the user task.

## Link to Instagram when

- the carousel/Reel is the primary experience;
- the goal is follower growth;
- the external post is a teaser/summary.

## Link to the public website when

- the user benefits from sources/methodology;
- the content is evergreen;
- data/dashboard exploration matters;
- the external platform's audience is likely to want a durable reference.

## No external link when

- the external post is already complete;
- links materially reduce readability and are not needed;
- the platform/channel performs better as self-contained content.

Do not force every external post into an Instagram traffic funnel.

The ultimate objective is EirePolitic audience growth across useful owned/controlled surfaces, not artificially maximising link clicks.

---

# Website analytics / referral measurement

Before external-link experiments are interpreted, choose a minimal website measurement method.

Required capabilities:

- page views for public content pages;
- referrer/source where privacy-appropriate;
- outbound click to Instagram/social profiles;
- campaign-parameter reporting;
- low maintenance.

Candidate technologies should be evaluated later for:

- cost;
- privacy;
- GitHub Pages compatibility;
- cookie/consent implications;
- data ownership;
- operational burden.

Do not install an analytics service as part of this documentation workstream.

---

# Experiment programme

## XT-001 — public content landing page

### Hypothesis

A general-audience public content page creates a more useful external destination than the technical homepage.

### Treatment

Evolve `/content/` or create the chosen public route with:

- clear EirePolitic proposition;
- featured/latest content;
- public data/source links;
- Instagram follow CTA.

### Metrics

Once analytics exists:

- visits by source;
- outbound Instagram clicks;
- content-page engagement;
- profile/follower movement around external campaigns.

### Manual effort

Near-zero after commissioning.

---

## XT-002 — Threads pilot

### Hypothesis

Automatically adapted EirePolitic posts can generate additional discovery/referrals without meaningful manual workload.

### Sample

6-10 posts.

### Metrics

- Threads reach/views;
- interactions;
- link clicks/referrals;
- follows on Threads;
- Instagram/public-site downstream activity;
- moderation minutes.

### Stop rule

Pause if the channel requires high conversational effort for negligible acquisition/referrals.

---

## XT-003 — Bluesky pilot

Use comparable content classes to XT-002.

Question:

Does Bluesky produce useful discovery/referral at low effort?

Track the same operational metrics.

Do not compare raw views across platforms as though platform metrics are defined identically.

---

## XT-004 — selective LinkedIn pilot

Publish only 3-5 high-fit public-policy/data/methodology items.

Question:

Does professional/research distribution produce meaningful site/Instagram referrals or useful network effects?

Track:

- impressions;
- clicks;
- follows;
- referral traffic;
- manual time.

---

## XT-005 — YouTube Shorts syndication

Only after Reel pipeline exists.

Reuse existing approved MP4s.

Question:

Does syndicating the same vertical video produce useful incremental audience at near-zero creative cost?

Metrics:

- views;
- retention;
- subscribers;
- referral traffic;
- moderation minutes.

---

## XT-006 — destination test

For a suitable external channel, compare two types of posts over repeated observations:

- link to Instagram;
- link to a public EirePolitic explainer/data page.

Measure:

- click-through;
- downstream engagement;
- Instagram profile/follow movement;
- website interaction.

Do not run duplicate spam posts solely to create a perfect A/B test.

---

# Metrics

Cross-platform activity needs platform-local metrics and EirePolitic outcome metrics.

## Platform-local

Where available:

- impressions/views/reach;
- engagements;
- shares/reposts;
- saves/bookmarks where relevant;
- link clicks;
- follower/subscriber growth;
- video retention.

Do not assume identically named metrics mean the same thing on every platform.

## Cross-platform outcome

- visits to public EirePolitic pages;
- Instagram profile clicks/referrals where measurable;
- Instagram follower trend;
- public-data/dashboard visits;
- email/newsletter signups if a future opt-in product exists;
- manual moderation/maintenance minutes.

## Efficiency

Track:

```text
useful external reach / recurring manual minute
```

and, where attribution is credible:

```text
new followers or meaningful referrals / recurring manual minute
```

This workstream should aggressively retire channels that consume time without producing useful audience.

---

# Cross-platform metadata

Record at minimum:

```text
content_id
platform
publication_mode              auto | manual_pilot
platform_variant_id
platform_post_id
platform_url
published_at
link_destination
campaign_id
asset_type                    image | multi_image | video | text | document
manual_minutes
experiment_id
```

For external social APIs, also retain provider execution/status data needed for safe retry/reconciliation, but do not store access tokens in publication records.

---

# Moderation burden

Automation can publish more easily than a human can moderate.

Every new platform pilot must record:

- notification volume;
- spam volume;
- factual correction requests;
- abuse/partisan argument volume;
- time required to respond/hide/report where necessary.

EirePolitic does **not** need to participate in every political debate under its posts.

A channel that produces high reach but creates substantial moderation burden may be strategically poor under the user's time constraints.

---

# External responses / replies

Do not automate political debate responses.

Safe candidates for future templated assistance:

- source requests;
- methodology questions;
- factual corrections;
- “where can I find this data?” questions.

Do not deploy autonomous argumentative/rebuttal bots.

If reply assistance is later implemented, keep human approval for substantive political responses.

---

# Newsletter / RSS opportunity

This is lower priority than the website/social pilots but may become useful.

## RSS

A static site can potentially expose a feed of:

- evergreen explainers;
- articles;
- public content releases.

Low recurring effort once generated.

Do not create an RSS feed of internal technical docs as the public audience product.

## Newsletter

Only investigate if there is evidence that users want recurring off-platform updates.

Do not start a newsletter merely because creator strategies often recommend one; it creates a recurring editorial obligation unless it is generated from the existing content pipeline.

A future newsletter should be opt-in and largely assembled from existing public content.

---

# GitHub role

GitHub is valuable for:

- technical transparency;
- canonical code/documentation;
- source methodology;
- collaboration with technical users.

It is not the primary consumer-audience growth channel.

The public website should **summarise and link to** repository documentation rather than send ordinary Instagram users directly into operational source files.

This remains aligned with the documentation-site standard that repository-owned operational docs are canonical.

---

# Implementation decision gates

## Gate A — public route

Choose:

- evolve `/content/`; or
- create a dedicated public landing route.

**Recommended first choice:** evolve `/content/` unless current site requirements argue otherwise.

## Gate B — website analytics

Select a privacy/cost-appropriate analytics method before interpreting referral experiments.

This changes public-site behaviour and requires approval.

## Gate C — first external social platform

**Recommended:** Threads.

Reason:

- official current API;
- compatible image/video/carousel concepts;
- natural reuse of existing Meta-oriented assets.

Do not implement before account/app/auth requirements are verified.

## Gate D — second external platform

Choose based on first pilot results.

**Likely candidate:** Bluesky.

Do not build Threads and Bluesky integrations simultaneously unless the implementation is genuinely trivial and the user approves the broader scope.

## Gate E — publisher architecture

Confirm whether external syndication remains a separate service/module rather than refactoring the Instagram publisher.

**Recommended:** separate initially.

## Gate F — unattended publishing

Each platform starts as a canary/pilot.

Enable unattended recurring syndication only after:

- auth is stable;
- idempotency/retries are understood;
- content renders correctly;
- metrics justify continuation.

---

# Suggested future repository structure

Do not create until implementation is approved.

Possible pipeline structure:

```text
distribution/
├── models.py
├── registry.py
├── adapters/
│   ├── threads.py
│   ├── bluesky.py
│   ├── linkedin.py
│   └── youtube.py
├── copy/
│   ├── threads.py
│   ├── bluesky.py
│   └── linkedin.py
└── metrics.py
```

Public-site data could be generated separately, for example:

```text
_data/
└── public_content.yml
```

or generated JSON consumed by the site.

Final paths must follow the live repositories' conventions.

Do not redesign the working Instagram package merely to match this proposed tree.

---

# Future implementation sequence

## Stage 1 — website first

1. Read this workstream and Profile Conversion.
2. Inspect current `warrengleeson.github.io` main branch.
3. Inspect `/content/`, homepage, layouts, and mobile behaviour.
4. Decide whether `/content/` or a new route becomes the general-audience entry point.
5. Prototype the public page on a branch.
6. Keep the technical homepage intact.
7. Define how latest/featured content is updated.
8. Define privacy-conscious analytics requirement.
9. Preview on mobile/desktop.
10. Open PR; do not merge without approval.

## Stage 2 — Threads capability audit

11. Verify current official Threads API documentation.
12. Determine whether an EirePolitic Threads account exists; if not, this becomes a user decision before account creation.
13. Inspect Meta app/auth possibilities without changing Instagram production credentials.
14. Verify required permissions/app review.
15. Prepare one API test post in a controlled environment.
16. Do not connect recurring automation yet.

## Stage 3 — Threads pilot

17. Define a small platform adapter.
18. Select 6-10 existing/future source content packages.
19. Generate platform-specific text/assets automatically.
20. Publish canaries.
21. Record IDs/URLs/metrics/manual moderation time.
22. Decide continue/stop.

## Stage 4 — second platform

23. Only after Threads learning, audit Bluesky.
24. Reuse the same canonical-content/distribution record model.
25. Run a small pilot.
26. Retire it if outcomes are weak.

## Stage 5 — video syndication

27. Wait for the Reel workstream.
28. Reuse proven MP4 assets for YouTube Shorts and possibly Threads video.
29. Do not create platform-specific video edits unless performance justifies them.

## Stage 6 — selective LinkedIn

30. Confirm whether EirePolitic has an appropriate LinkedIn identity/page and API access.
31. Test only high-fit data/methodology/public-policy items.
32. Evaluate referral value and professional audience effects.

---

# Workload / cost assessment

| Activity | Expected upside | Setup effort | Recurring manual effort | Cost | Automation potential |
|---|---|---|---|---|---|
| Improve public `/content/` surface | High foundational value | Low-medium | Near-zero | €0 on current hosting | High |
| Auto-update featured/latest public content | Medium-high | Medium | None | €0/very low | Very high |
| Website analytics | High measurement value | Low-medium | Near-zero | €0/low depending tool | Very high |
| Threads pilot | Medium-high | Medium | Very low after setup | €0/very low infra | Very high |
| Bluesky pilot | Medium | Low-medium | Very low | €0/very low infra | Very high |
| Selective LinkedIn | Medium | Medium | Low | €0/very low | High |
| YouTube Shorts syndication | Potentially high after Reel work | Low incremental | Very low | €0/very low | Very high |
| Facebook expansion | Unknown | Medium | Unknown | €0/low | High technically, defer |
| TikTok expansion | Unknown | Medium-high | Potential moderation burden | €0/low | Medium-high, defer |
| Bespoke content per platform | Variable | Low setup | High recurring | €0 | Low — avoid |
| Manually maintaining “latest post” embeds | Low | Very low | Recurring | €0 | Poor fit |

---

# Risks and safeguards

## Platform sprawl

The largest risk is creating five small accounts that all require attention.

Mitigation:

- one platform at a time;
- explicit stop rules;
- automated publishing;
- moderation-time measurement.

## Duplicate-content fatigue

Do not dump every Instagram publication unchanged onto every network.

Use content-class rules.

## Source drift

External platform copy must derive from the same approved source content.

Do not manually “improve” political claims per platform.

## Credential proliferation

Each new platform creates authentication/security obligations.

Use separate secrets and least privilege; do not combine unrelated credentials for convenience.

## Instagram regression

External publishing must not block/delay Instagram.

Keep integrations failure-isolated.

## Public-site audience confusion

Do not mix general political explainers with internal infrastructure documentation without clear navigation/positioning.

## Analytics/privacy creep

Do not add invasive website tracking merely to obtain perfect attribution.

Choose proportionate measurement.

## Moderation burden

Political platforms can create argumentative responses.

The channel must justify the time required to manage it.

## Political neutrality

Cross-platform copy remains factual and non-partisan.

Do not modify framing to fit a platform's ideological subculture or chase conflict-driven engagement.

---

# Current external capability references

Revalidate these before implementation:

- Meta Threads API/Postman reference: `https://www.postman.com/meta/threads/collection/dht3nzz/threads-api`
- Bluesky post creation documentation: `https://docs.bsky.app/docs/tutorials/creating-a-post`
- LinkedIn Posts API: `https://learn.microsoft.com/en-us/linkedin/marketing/community-management/shares/posts-api`
- LinkedIn API access overview: `https://learn.microsoft.com/en-us/linkedin/shared/authentication/getting-access`
- YouTube Data API upload guide: `https://developers.google.com/youtube/data/guides/uploading_a_video`
- YouTube resumable uploads: `https://developers.google.com/youtube/data/guides/using_resumable_upload_protocol`

These references establish technical feasibility, not strategic proof that the platform will produce audience growth.

---

# Information that may require the user

Most planning/repository work can proceed without user input.

Ask the user only for material decisions such as:

- whether to evolve `/content/` or create a new public route;
- approval of a website analytics tool if tracking is introduced;
- whether EirePolitic already has or should create an account on a proposed external platform;
- approval before creating new OAuth apps/credentials/secrets;
- approval before unattended cross-platform publication is enabled;
- whether a channel's moderation burden remains acceptable after a pilot.

Do not ask the user to manually copy posts between platforms.

---

# Handoff instructions for future LLM chats

When implementing this workstream:

1. Read this page and the master growth plan.
2. Read Profile Conversion, Reels/Repurposing, Captions, and Insights workstream status.
3. Inspect current `warrengleeson.github.io` and `Eirepolitic-data-pipeline` main branches.
4. Treat `/content/` as an existing public-output opportunity, not an empty site.
5. Preserve the technical homepage unless a separate explicit redesign is approved.
6. Search current official platform API documentation before designing integrations.
7. Do not assume platform permissions/API support documented here are unchanged.
8. Prefer official APIs over browser automation.
9. Keep platform credentials separate and secret.
10. Keep external publishing failure-isolated from Instagram.
11. Reuse approved factual assets/copy fields.
12. Do not create bespoke daily content for external platforms.
13. Start with the public-site improvement and one external channel.
14. Recommended first external API pilot: Threads.
15. Measure platform-local outcomes, referrals, and manual moderation minutes.
16. Do not compare differently defined platform metrics as though they are identical.
17. Stop weak channels quickly.
18. Wait for proven Reel MP4 generation before YouTube Shorts/video expansion.
19. Do not create new social accounts, apps, secrets, or unattended publishing without explicit user approval.
20. Update this page with actual account state, API permissions, pilot results, retired channels, and promoted syndication rules.

---

# Completion criteria

This workstream is mature when:

- EirePolitic has a clear general-audience public web destination;
- public featured/latest content does not require fragile manual maintenance;
- referral/outbound behaviour can be measured proportionately;
- at least one external social channel has been tested with reused assets;
- channels that fail to justify effort have been explicitly retired;
- successful channels can publish from canonical EirePolitic content with near-zero additional creative work;
- video syndication reuses the Reel asset rather than creating a second video workflow;
- external platform failures cannot block Instagram;
- moderation/maintenance workload remains small;
- technical documentation remains separate from consumer-facing political information;
- all cross-platform output preserves EirePolitic's sourcing, neutrality, and semantic standards.

The target end state is **a small number of durable external discovery paths feeding EirePolitic's owned/public content and Instagram, without turning every additional platform into another job**.
