---
title: "EirePolitic Instagram Growth: Experiment Programme and 30/60/90-Day Plan"
description: "Operating framework for prioritising growth experiments, sequencing implementation, and consolidating findings into a practical 30/60/90-day audience-growth programme."
group: "Notes"
order: 70
---

# Experiment Programme and 30/60/90-Day Plan

## Status

**Planning state:** detailed operating plan prepared.  
**Production changes:** none.  
**Role:** consolidation layer for Workstreams 01-09.  
**Primary rule:** do not increase technical or manual complexity until a cheaper experiment demonstrates enough value to justify it.

## Objective

Turn the nine growth workstreams into one controlled optimisation programme that increases:

- non-follower reach;
- profile visits;
- follows;
- shares/reposts;
- saves/reference value;
- repeat engagement;

while keeping:

- political neutrality intact;
- factual/source standards intact;
- production publishing reliable;
- recurring operator workload low;
- monetary cost near zero unless evidence supports spending.

This programme is not a fixed social-media calendar.

It is a **decision system**:

```text
measure current state
      ↓
run cheapest/highest-value experiment
      ↓
collect comparable evidence
      ↓
continue / modify / stop
      ↓
automate only proven behaviour
      ↓
move to the next higher-cost opportunity
```

---

# Programme constraints

## Cost hierarchy

Always prefer, in this order:

1. no-cost changes;
2. very-low-cost infrastructure;
3. low recurring manual work;
4. automation/systematisation;
5. higher-effort work only after evidence justifies it.

Paid advertising remains outside the default 90-day programme.

A paid experiment should be considered only after organic acquisition and conversion metrics are understood well enough to know what content/profile experience would be amplified.

## Operator-time target

Use a default planning target of:

**approximately 30-60 minutes of recurring Instagram-growth administration per week**, excluding one-time implementation/deployment sessions and occasional design approvals.

This is a design target, not a hard user commitment.

Any tactic regularly exceeding this budget must demonstrate unusually strong audience value or be redesigned/automated.

## Production-safety rule

No growth experiment may silently modify:

- production publishing schedules;
- AWS infrastructure;
- Instagram credentials;
- Meta app permissions;
- production renderers;
- unattended external publishing;

without the explicit approval gates defined in the relevant workstream.

## Editorial rule

No experiment may trade factual precision for reach.

A failed growth experiment is acceptable.

A misleading political post is not.

---

# Workstream dependency map

The workstreams should not be executed independently in arbitrary order.

```text
01 Insights / Measurement
        ↓
02 Profile Conversion
03 Discovery Hooks / Carousel Packaging
        ↓
05 Captions / Search / CTA
06 Topical + Evergreen
07 Sharing / Saves / Reposts
        ↓
04 Reels / Repurposing
08 Distribution / Collaborations
09 Cross-platform / External Traffic
        ↓
continuous optimisation / automation
```

This is not a strict waterfall.

Some low-risk preparation can happen in parallel, but measurement + packaging + conversion should lead because they determine whether later distribution efforts are amplifying something that actually converts.

---

# Highest-leverage opportunities identified so far

Use this as the current priority stack until evidence changes it.

| Priority | Opportunity | Expected upside | Setup effort | Recurring effort | Cost | Automation potential |
|---|---|---|---|---|---|---|
| 1 | Instagram Insights measurement layer | Foundational | Medium | Very low | Very low | Very high |
| 2 | Plain-language Bill Tracker / carousel covers | Very high | Low-medium | Near-zero | €0 | Very high |
| 3 | Profile bio + three-pin conversion structure | High | Low | Very low | €0 | Medium/high |
| 4 | Evergreen parliamentary explainers | High | Medium once | Very low | €0 | High |
| 5 | Structured caption/CTA improvements | Medium-high | Low | Near-zero | €0 | Very high |
| 6 | Share/save/repost-oriented packaging | High | Low-medium | Near-zero | €0 | Very high |
| 7 | Data-triggered topical posts | High | Medium | Very low | Very low | Very high |
| 8 | Polling/data-led Reel prototype | Potentially high | Medium | Near-zero once proven | Very low | Very high |
| 9 | Selective low-volume partner distribution | Medium-high | Low | Low | €0 | Medium |
| 10 | Public `/content/` improvement | Medium-high | Low-medium | Near-zero | €0 | High |
| 11 | Threads / external syndication | Unknown-medium/high | Medium | Very low | Very low | Very high |

The order intentionally places **content acquisition and conversion before channel expansion**.

---

# Measurement hierarchy

## Primary acquisition metrics

Where available:

1. non-follower reach;
2. follows per 1,000 accounts reached;
3. profile visits per 1,000 accounts reached;
4. profile-visit-to-follow conversion;
5. shares per 1,000 reached.

## Utility/distribution metrics

- saves per 1,000 reached;
- reposts per 1,000 reached;
- 30-day / 7-day reach ratio for evergreen content;
- Reel watch/retention metrics;
- external referral traffic.

## Diagnostic metrics

- likes;
- comments;
- raw views;
- raw follower count.

These matter, but should not independently determine whether a growth treatment is successful.

## Operational metric

Track **manual minutes** for experiments that require human action.

A useful growth tactic with low manual cost can outperform a somewhat stronger tactic that consumes substantial operator time.

---

# Standard post-age checkpoints

Where the platform exposes cumulative metrics, compare posts at similar ages.

Use these standard checkpoints from Workstream 01:

- approximately 72 hours;
- approximately 7 days;
- approximately 30 days;
- optionally 90 days for evergreen content.

Do not compare lifetime totals from an old post against a two-day-old treatment.

---

# Experiment governance

## Experiment states

Each experiment should move through:

```text
proposed
→ ready
→ active
→ collecting
→ evaluated
→ promoted / modified / stopped
→ archived
```

Only one state should be authoritative.

## Standard experiment record

Each experiment must document:

```yaml
experiment_id: "DH-001"
title: "Bill Tracker plain-language cover"
workstream: discovery_hooks
hypothesis: "..."
content_family: bill_tracker
control: "..."
treatment: "..."
primary_metric: "..."
secondary_metrics:
  - "..."
start_date: null
end_date: null
sample_target: "repeated comparable observations"
status: proposed
manual_effort_target_minutes: 0
confounders:
  - topic
  - current_event_relevance
result: null
decision: null
notes: "..."
```

Do not require every field to live in YAML specifically; the important requirement is structured, inspectable experiment identity.

## Pre-registration rule

Where practical, record:

- hypothesis;
- control/treatment;
- primary metric;

**before** reviewing the results.

This reduces post-hoc interpretation.

## One major variable at a time

Do not simultaneously change:

- cover;
- caption;
- carousel depth;
- CTA;
- posting time;

and then claim to know which change helped.

Some real-world confounding is unavoidable, but deliberately isolate variables where cheap to do so.

---

# Evidence levels

EirePolitic will initially have small samples.

Do not pretend every result is statistically conclusive.

Use three evidence levels.

## Level 1 — directional

Evidence:

- one or two observations;
- clear qualitative/metric signal;
- insufficient repetition.

Decision:

- keep testing;
- do not promote globally unless operational risk is negligible and the improvement is obvious.

## Level 2 — repeatable

Evidence:

- repeated observations across multiple publications/periods;
- treatment generally moves the primary metric in the same direction;
- no obvious semantic/operational downside.

Decision:

- promote to wider pilot/default for the relevant content family.

## Level 3 — operationally established

Evidence:

- repeated performance over time;
- stable automation;
- low manual overhead;
- no material production/editorial problems.

Decision:

- make part of the normal factory;
- stop treating it as an experiment unless a later challenger is tested.

---

# Decision rules

## Promote

Promote a treatment when:

- the primary acquisition/utility metric improves repeatedly;
- secondary metrics do not reveal a serious tradeoff;
- factual/neutrality standards remain intact;
- recurring workload is acceptable;
- implementation complexity is proportionate.

## Continue testing

Continue when:

- result is directionally positive but sample is small;
- topic/timing confounding is substantial;
- performance is mixed across content families;
- technical reliability has not yet been established.

## Modify

Modify when:

- the basic hypothesis appears sound but execution is weak;
- users engage but do not convert;
- reach increases but saves/shares/follows collapse;
- manual work is too high.

## Stop

Stop when:

- repeated tests fail to improve the intended metric;
- the tactic creates excessive operator workload;
- it introduces material neutrality/credibility risk;
- it destabilises production;
- the platform/channel does not provide useful audience;
- a cheaper tactic performs equally well.

Record stopped experiments so future chats do not rediscover them.

---

# Experiment ID registry

Use the IDs already defined in Workstreams 02-09.

## Profile Conversion — `PC`

- `PC-01` bio/value proposition;
- `PC-02` pinned Start Here post;
- `PC-03` data-selected demonstration pin;
- `PC-04` display name;
- `PC-05` profile-link destination.

## Discovery Hooks — `DH`

- `DH-001` Bill Tracker plain-language cover;
- `DH-002` question vs statement;
- `DH-003` party speech measured-question cover;
- `DH-004` formal title vs plain-language subject label;
- `DH-005` key-number cover;
- `DH-006` carousel depth.

## Reels / Repurposing — `RR`

- `RR-001` polling carousel vs automated Reel;
- `RR-002` Trial Reel discovery test;
- `RR-003` Reel length;
- `RR-004` motion vs near-static Reel;
- `RR-005` format by content family.

## Caption / Search — `CS`

- `CS-001` short vs contextual caption;
- `CS-002` descriptive first line vs series title;
- `CS-003` CTA vs no CTA;
- `CS-004` generic vs topic-specific hashtag set;
- `CS-005` source/caveat placement;
- `CS-006` save vs share CTA by content type.

## Topical / Evergreen — `TE`

- `TE-001` topical vs procedural packaging;
- `TE-002` topical polling vs routine polling;
- `TE-003` evergreen process explainer;
- `TE-004` topical + evergreen bridge;
- `TE-005` “what the record shows” current-event format;
- `TE-006` evergreen resurfacing.

## Sharing / Reposts — `SR`

- `SR-001` utility CTA vs no CTA;
- `SR-002` standalone summary slide;
- `SR-003` source prominence;
- `SR-004` topical sendability;
- `SR-005` evergreen saveability;
- `SR-006` native-repost candidate.

## Distribution / Ecosystem — `DE`

- `DE-001` targeted repost request pilot;
- `DE-002` student society distribution;
- `DE-003` native Collab pilot;
- `DE-004` repost vs Collab;
- `DE-005` partner-class comparison;
- `DE-006` opt-in recurring distribution list.

## Cross-platform / External Traffic — `XT`

- `XT-001` public content landing page;
- `XT-002` Threads pilot;
- `XT-003` Bluesky pilot;
- `XT-004` selective LinkedIn pilot;
- `XT-005` YouTube Shorts syndication;
- `XT-006` destination test.

Do not run every experiment in this registry.

The registry is a controlled backlog.

---

# Experiment priority classes

## P0 — foundation

Must happen before reliable optimisation.

- Insights capability audit and ingestion baseline;
- profile baseline audit;
- experiment metadata convention.

## P1 — highest expected return / lowest complexity

Run first.

- `DH-001` Bill Tracker plain-language cover;
- `PC-01` profile bio/value proposition;
- `PC-02` pinned Start Here post;
- `CS-002` descriptive caption first line;
- `TE-003` evergreen process explainer.

## P2 — scale useful distribution

After initial acquisition improvements.

- `SR-001` save CTA on evergreen explainer;
- `SR-004` topical sendability;
- `TE-001` topical vs procedural framing;
- polling-change packaging;
- data-triggered topical candidate prototype.

## P3 — new-format expansion

Only after measurement demonstrates that additional reach is worth pursuing.

- Reel prototype;
- `RR-002` small Trial Reel pilot;
- `DE-001` small repost-outreach pilot;
- `XT-001` public landing/content improvement.

## P4 — channel expansion

Only after P0-P3 are producing useful learning.

- Threads pilot;
- Bluesky;
- Collabs;
- LinkedIn;
- YouTube Shorts.

---

# 30/60/90-day programme definition

The timeline should start on the day the user explicitly begins the execution phase.

Do not anchor it to the date this planning document was written.

The “Day 30 / 60 / 90” labels mean programme age.

---

# Days 1-30 — establish the growth feedback loop

## Main goal

Know what currently converts, remove obvious profile/discovery friction, and run the first cheap packaging tests.

## Work package 1 — measurement foundation

### Required

- perform Meta Insights capability audit;
- determine whether existing credential can read required Insights;
- approve analytics architecture;
- implement/backfill only after approval;
- establish baseline for recent posts;
- produce first per-publication performance table.

### Minimum useful output by Day 30

For recent publications, be able to see at least a useful subset of:

- reach;
- non-follower reach where available;
- shares;
- saves;
- follows/profile activity where available;
- content family;
- publication date;
- post-age checkpoint.

If full automation takes longer, use a small manual baseline rather than blocking all experiments.

Do not wait for a perfect dashboard.

## Work package 2 — profile conversion audit

- capture current profile state;
- verify Account Status/recommendation eligibility;
- record bio/name/links/pins;
- establish profile-visit/follow baseline where available.

Run `PC-01` only after baseline capture.

Prepare `PC-02` Start Here carousel in parallel if useful.

## Work package 3 — first acquisition-cover experiment

Commission `DH-001`.

Recommended scope:

**Bill Tracker cover only.**

Do not redesign the entire carousel.

Control:

current cover.

Treatment:

plain-language “what each one changes” style.

Record experiment metadata before publication.

## Work package 4 — caption alignment

Commission `CS-002` alongside the successful/active cover format where possible.

Do not change caption structure during the exact same publications being used to isolate `DH-001` unless clearly documented.

## Work package 5 — first evergreen asset

Create one high-value explainer.

Recommended first:

`How a Bill becomes law in Ireland`

or

`What does Second Stage mean?`

Use it to establish:

- evergreen template;
- save/reference baseline;
- future Start Here/profile utility.

## Day-30 review questions

By the first review, answer:

1. Can we reliably measure post performance?
2. Is the profile eligible for recommendations?
3. What is the baseline profile conversion rate where measurable?
4. Does plain-language cover packaging show a positive directional signal?
5. Does the evergreen explainer produce stronger save/long-tail behaviour?
6. Which implementation task consumed unexpected manual time?

## Day-30 outputs

Expected artifacts:

- working Insights baseline or documented blocker;
- profile audit record;
- at least one active/completed cover experiment;
- one evergreen explainer prototype/publication;
- experiment ledger/report;
- prioritised Day 31-60 backlog.

---

# Days 31-60 — expand the formats that create distribution

## Main goal

Turn the first positive acquisition lessons into reusable templates and test one additional discovery format.

## Work package 1 — promote/iterate cover winners

If `DH-001` reaches at least Level-2 evidence:

- make the treatment the default for the relevant Bill Tracker subset;
- retain renderer/version metadata;
- begin `DH-002`, `DH-004`, or `DH-005` only if there is a clear remaining question.

If `DH-001` fails:

- do not redesign everything;
- inspect whether the problem was topic, wording, or visual hierarchy;
- modify one variable and retest.

## Work package 2 — profile conversion implementation

Based on `PC-01`/`PC-02` evidence:

- retain the strongest bio proposition;
- establish the three-pin structure;
- choose demonstration pin using measured acquisition performance;
- avoid frequent identity changes afterward.

## Work package 3 — evergreen library

Expand from one to approximately **3-5 reusable evergreen assets**.

Recommended topics:

- how a Bill becomes law;
- Second Stage;
- Dáil division/amendment vote;
- polling percentage points;
- what EirePolitic speech-frequency data measures.

Do not create all five if the first assets show weak value.

## Work package 4 — share/save system

Run:

- `SR-001` utility CTA;
- `SR-005` evergreen saveability;
- optionally `SR-002` summary/reference card.

Promote only treatments that increase actual utility/distribution.

## Work package 5 — topical trigger prototype

Commission one low-risk structured trigger.

Recommended sequence:

1. new poll;
2. certified Bill state change.

The trigger should create a **candidate**, not unattended publication.

Measure:

- time from validated event to publish-ready candidate;
- manual review time;
- non-follower reach and shares.

## Work package 6 — first Reel prototype

Only if Days 1-45 show that packaging/content itself is improving.

Prototype polling Reel locally/CI with no publisher changes.

Decision gate:

Is the format visually strong enough and operationally simple enough to justify a manual Trial Reel or API-development pilot?

Do not extend the production publisher merely because Day 60 has arrived.

## Day-60 review questions

1. Which cover/hook rule should become standard?
2. Is profile conversion improving?
3. Which evergreen posts generate saves/shares/follows?
4. Can topical candidates be generated without significant operator work?
5. Is a Reel format worth further investment?
6. Which experiment should be stopped?

## Day-60 outputs

Expected artifacts:

- at least one promoted/retired discovery treatment;
- stable profile conversion configuration;
- small evergreen library;
- one topical-candidate rule;
- first share/save findings;
- Reel prototype decision;
- updated experiment ledger.

---

# Days 61-90 — scale proven acquisition and test external distribution

## Main goal

Automate what worked, stop what did not, and test one or two external distribution paths without creating operational sprawl.

## Work package 1 — automation hardening

Promote only Level-2/Level-3 treatments into routine production.

Candidates may include:

- acquisition cover renderer;
- caption rules;
- CTA selection;
- evergreen renderer;
- topical candidate generation;
- Insights collection/reporting.

Add regression/semantic QA before unattended operation.

## Work package 2 — Reel pilot or stop decision

If Reel prototype passed the Day-60 gate:

- publish 1-2 controlled Trial/manual Reels or API canaries;
- measure non-follower discovery and follows;
- decide whether production Reel publishing support is justified.

If results are weak:

**stop the Reel engineering work.**

Do not continue because Reels are fashionable.

## Work package 3 — low-volume ecosystem distribution

Run `DE-001`.

Use:

- one proven evergreen civic explainer;
- 2-3 low-risk relevant accounts;
- a single repost/share request batch.

Record:

- manual minutes;
- response;
- redistribution;
- downstream acquisition.

Do not move to Collabs unless repost distribution proves useful and a genuine co-production opportunity exists.

## Work package 4 — public content surface

Run `XT-001` if not already completed.

Recommended:

improve `/content/` into a clearer general-audience public-output page while preserving the technical homepage.

Add website measurement only after the tool/privacy decision is approved.

## Work package 5 — first external social pilot

Only if the programme still has available operational capacity.

Recommended first candidate:

**Threads.**

Run a small 6-10 post pilot using reused assets.

Do not simultaneously build Bluesky, LinkedIn, and YouTube integrations.

## Work package 6 — consolidate reporting

Create one recurring weekly/monthly growth review that can answer:

- what reached non-followers;
- what converted to follows;
- what got shared/saved;
- what consumed manual time;
- which experiment is active next;
- which tactics have been retired.

This report should be generated from the analytics/experiment data as much as possible.

## Day-90 review questions

1. Which acquisition changes are now normal production behaviour?
2. Which formats should be permanently retired?
3. Is Reels automation justified?
4. Is external partner outreach worth continuing?
5. Does the public website contribute useful discovery/referrals?
6. Is any external social platform producing useful audience at low effort?
7. Is there enough evidence to consider a small paid-promotion experiment, or should organic optimisation continue?

A “no” to paid promotion is a perfectly valid Day-90 outcome.

---

# 90-day target operating state

A successful first 90 days does **not** require explosive follower growth.

It should produce a functioning optimisation system.

Target state:

```text
structured content factory
        ↓
proven acquisition packaging
        ↓
measured profile conversion
        ↓
Insights feedback loop
        ↓
small evergreen/topical library
        ↓
shareable/repostable formats
        ↓
selective additional distribution
        ↓
continuous experiment backlog
```

Operationally:

- content experiments are labelled;
- post performance is retrievable;
- successful patterns are deterministic;
- failed patterns are documented;
- operator time remains low;
- production reliability is unchanged or improved.

---

# Recommended first experiment queue

Use this as the default sequence when the execution phase begins.

## Queue 0 — foundation

1. Insights capability audit.
2. Profile baseline / recommendation eligibility.
3. Experiment metadata convention.

## Queue 1 — cheap acquisition

4. `DH-001` Bill Tracker plain-language cover.
5. `PC-01` bio/value proposition.
6. `PC-02` Start Here pin.
7. `TE-003` first evergreen explainer.
8. `CS-002` descriptive caption first line.

## Queue 2 — utility/distribution

9. `SR-001` utility CTA.
10. `SR-005` evergreen saveability.
11. new-poll topical trigger.
12. Bill state-change candidate.

## Queue 3 — new format / external reach

13. polling Reel prototype.
14. `DE-001` targeted repost pilot.
15. `XT-001` public landing/content page.
16. `XT-002` Threads pilot if justified.

Everything else stays in backlog until one of these produces evidence that the next experiment is worth running.

---

# Weekly review format

Once measurement exists, use a compact weekly review.

## Section A — account

- follower count start/end;
- net/gross follower change where available;
- total/non-follower reach;
- profile visits;
- profile conversion;
- total shares/saves/reposts.

## Section B — top acquisition posts

Show at matched checkpoint:

- publication;
- content family;
- experiment/variant;
- reach;
- non-follower reach;
- follows per 1,000 reached;
- shares per 1,000;
- saves per 1,000.

## Section C — active experiment

- experiment ID;
- observations collected;
- direction of result;
- confounders;
- next observation/date.

## Section D — manual workload

- minutes spent on growth operations;
- tasks causing unexpected effort.

## Section E — decisions

Only:

- promote;
- continue;
- modify;
- stop;
- start next experiment.

The review should not become a long narrative report every week.

---

# Monthly programme review

Once per month, evaluate the workstreams rather than individual posts.

For each active workstream record:

| Field | Meaning |
|---|---|
| Evidence | What have we actually observed? |
| Upside | Is the opportunity still large? |
| Manual cost | How much recurring time? |
| Technical cost | How much maintenance/infrastructure? |
| Risk | Neutrality/reliability concerns? |
| Decision | expand / hold / stop |

Then update the next 30-day backlog.

---

# Prioritisation framework

Use a simple operational evaluation rather than a false-precision numeric score.

For each proposed initiative, classify:

## Expected upside

- low;
- medium;
- high;
- very high.

## Evidence/confidence

- speculative;
- directional;
- repeatable;
- established.

## Setup effort

- very low;
- low;
- medium;
- high.

## Recurring manual effort

- none;
- minutes/month;
- minutes/week;
- high recurring.

## Monetary cost

- €0;
- very low;
- low;
- material.

## Automation potential

- low;
- medium;
- high;
- very high.

## Neutrality/credibility risk

- low;
- medium;
- high.

## Production risk

- none;
- low;
- medium;
- high.

### Default decision preference

Choose the initiative with:

- higher expected upside;
- stronger evidence;
- lower recurring work;
- lower risk;
- higher automation potential.

Do not create a weighted numerical score unless it genuinely improves decisions.

---

# Posting-time experiments

Posting time is deliberately **not** a first-wave priority.

Reason:

A small account with weak packaging/measurement is unlikely to learn much from micro-optimising publication hours before stronger acquisition variables are addressed.

Run time-window experiments only after:

- baseline Insights exist;
- content family/variant metadata exist;
- enough comparable posts are available.

Then test broad windows, not dozens of times.

Example:

- weekday daytime;
- weekday evening;
- weekend.

Do not manually reschedule posts constantly based on anecdotal advice.

---

# Topic/category experiments

Topic itself can dominate performance.

Therefore do not conclude:

> “Cover A beat Cover B”

when Cover A happened to concern a major live political story and Cover B concerned a low-interest procedural item.

Record at minimum:

- content family;
- topic/category;
- topicality;
- parliamentary stage where relevant;
- party/entity where relevant;
- publication time;
- format.

Use repeated observations and medians.

---

# Experiment collision rules

Several workstreams may want to test the same post.

Avoid uncontrolled collisions.

## Example

A Bill Tracker post could simultaneously be eligible for:

- `DH-001` cover;
- `CS-002` caption;
- `SR-001` CTA;
- `TE-001` topical framing.

Do not activate all four unless the experiment purpose is explicitly a bundled “new package vs old package” test.

Preferred sequence:

1. cover;
2. caption opening;
3. CTA;
4. topical/trigger variation.

Once a treatment becomes standard, it becomes the new baseline for subsequent tests.

---

# Bundled experiments

Sometimes the practical product question is broader than one variable.

Example:

> “Does a full general-audience Bill package outperform the legacy procedural package?”

A bundled treatment may change:

- cover;
- caption;
- CTA.

This is acceptable if labelled clearly as a **package experiment**.

Do not then claim that any single component caused the result.

Use bundled tests after individual components have been explored or when publication volume is too small for many separate tests.

---

# Data quality before decisions

Do not evaluate an experiment until:

- media identity is correctly joined;
- metrics are from comparable post-age checkpoints;
- missing values are distinguished from zeros;
- metric definitions are known;
- API/UI discrepancies have been validated where material.

If Meta changes metric definitions during an experiment, document the version change and avoid false continuity.

---

# Experiment reporting language

Use restrained language.

Prefer:

- `Treatment showed a repeated positive direction across four comparable posts.`
- `Evidence is insufficient; continue testing.`
- `Reach increased but follow conversion fell.`
- `The result is confounded by unusually high topical interest.`

Avoid:

- `This proves the algorithm prefers questions.`
- `This is statistically significant` without actual statistical basis;
- `Instagram penalised the post` without evidence;
- `This topic went viral because of the hashtag.`

---

# Paid-promotion decision after 90 days

Paid advertising/promotion is not part of the default execution programme.

At/after Day 90, evaluate only if:

- the account has at least one format that converts reach into followers efficiently;
- profile conversion is understood;
- the content is recommendation-eligible;
- organic distribution experiments have identified credible acquisition creative;
- analytics can distinguish paid and organic outcomes;
- there is a clear maximum test budget.

If these conditions are absent, continue organic optimisation.

Do not use paid promotion to compensate for unclear positioning or weak conversion.

---

# Programme documentation rules

Future chats should update the growth documentation as the programme runs.

## Update the relevant workstream when

- capability/live-state facts change;
- an experiment is launched;
- an option is rejected;
- a production default changes;
- platform/API behaviour is confirmed;
- a new risk/constraint is discovered.

## Update this page when

- priority order changes;
- experiment queue changes;
- 30/60/90 phase changes;
- a workstream is promoted/retired;
- a major cross-workstream decision is made.

## Do not duplicate operational runbooks

If implementation creates production code/infrastructure, canonical operational documentation belongs in the owning repository.

This site should retain the growth strategy, experiment rationale, decisions, and links to canonical implementation docs.

---

# Handoff instructions for future LLM chats

When a future chat is asked to continue the growth programme:

1. Read the master growth index.
2. Read this page.
3. Read the relevant workstream page.
4. Inspect the current production/documentation repositories before assuming this plan reflects live state.
5. Identify the **current programme phase**: foundation, Days 1-30, 31-60, 61-90, or post-90 optimisation.
6. Read the experiment ledger/results before proposing a new experiment.
7. Do not rerun a failed/rejected tactic without a materially new hypothesis.
8. Choose the highest-priority experiment whose dependencies are satisfied.
9. Prefer the lowest-cost implementation that tests the hypothesis.
10. Ask the user only for material decisions that cannot be resolved from repositories/live systems.
11. Before architecture/cost/security/production changes, explain the choice and obtain confirmation.
12. Preserve working production behaviour.
13. Record experiment metadata before publication where practical.
14. Collect comparable checkpoint metrics.
15. Evaluate using acquisition/utility metrics rather than likes alone.
16. Record manual minutes for human-heavy tactics.
17. Update the relevant workstream and this programme plan with the result.
18. Promote repeatable winners into deterministic automation.
19. Retire weak/high-work tactics.
20. Keep the active experiment backlog deliberately small.

---

# Completion criteria for the first 90-day programme

The first programme cycle is successful when EirePolitic has:

- a functioning Instagram measurement/Insights feedback loop;
- a measured profile-conversion baseline;
- at least one improved acquisition-cover pattern tested and either promoted or rejected;
- a small evergreen explainer library;
- structured caption/CTA rules tested;
- clear evidence about share/save behaviour;
- at least one data-triggered topical-content prototype;
- a documented decision on whether automated Reels deserve further investment;
- at least one small external distribution experiment completed or explicitly deferred;
- a clear public-site strategy;
- a repeatable weekly/monthly review process;
- documented failed experiments as well as winners;
- low recurring manual workload;
- no loss of factual, neutral, or production standards.

The programme should leave EirePolitic with something more valuable than a list of social-media tactics:

**a measurable system that continually learns which factual political-information formats earn useful new audience and then automates the successful ones.**
