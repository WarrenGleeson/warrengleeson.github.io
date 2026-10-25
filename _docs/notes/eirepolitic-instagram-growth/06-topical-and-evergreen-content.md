---
title: "EirePolitic Instagram Growth: Topical and Evergreen Content"
description: "Detailed plan for combining timely political-information posts with durable evergreen explainers using EirePolitic's existing structured data."
group: "Notes"
order: 66
---

# Topical and Evergreen Content

## Status

**Planning state:** detailed investigation/implementation guide prepared.  
**Production changes:** none.  
**Priority:** high.  
**Dependencies:** Discovery Hooks determines packaging; Insights/Measurement determines which topical/evergreen formats actually acquire followers; existing data contracts determine what can safely be inferred.

## Objective

Create a low-manual-work content system that combines:

1. **recurring structured series** already produced by the factory;
2. **topical posts** triggered by fresh political/public-record events;
3. **evergreen explainers** that remain useful beyond a single news cycle.

The goal is to make EirePolitic more discoverable and useful without turning it into a manually operated breaking-news account.

The preferred model is:

```text
validated structured data
        ↓
deterministic event/change detection
        ↓
content candidate queue
        ↓
semantic/source checks
        ↓
existing approved visual/content templates
        ↓
review + publication
```

For externally driven current events:

```text
current public event/news signal
        ↓
match to EirePolitic structured data
        ↓
source verification
        ↓
neutral factual explainer candidate
        ↓
review + publication
```

External news should normally **trigger investigation**, not become the factual source of record when EirePolitic already has an official/structured source available.

---

# Current repository capability already established

The production source of truth is `warrengleeson/Eirepolitic-data-pipeline`.

## Existing Instagram families

The Director catalogue currently exposes three reusable Instagram projects:

### Bill Tracker

`bill_tracker_factory_v1`

Current strengths:

- formal bill identity;
- stage/status context;
- exact recorded-division semantics;
- plain-language `what` / `effect` content;
- arguments/concerns where sourced;
- glossary/procedure support.

This is a strong basis for both **topical bill events** and **evergreen legislative explainers**.

### Party Speech Breakdown

`party_issue_monthly_profile_v2`

Current strengths:

- classified Dáil speech issue data;
- party-level issue frequency;
- comparison with cross-party averages;
- per-TD comparisons;
- explicit semantic protection against interpreting frequency as political position or subjective priority.

This is useful for recurring monthly content and selected topical context, but should not be converted into claims such as “what the party cares about most.”

### Polling

`ipi_polling_factory_v1`

Current strengths:

- latest polling percentages;
- change since previous poll;
- six-month trend;
- methodology slide.

Polling is naturally time-sensitive and is one of the easiest existing products to make topical with very low incremental work.

---

# Additional structured topical capability already present

The repository's political-metrics layer is significantly broader than the current Instagram project catalogue.

The downstream contracts currently expose logical datasets including:

- `daily_activity_components`;
- `daily_context_vote_components`;
- `daily_issue_activity`;
- `division_party_vote_components`;
- `context_division_party_vote_components`;
- `daily_question_dimensions`;
- `oral_question_sections`;
- `oral_question_exchange_participants`;
- `speech_question_context`;
- `bill_debate_sections`;
- `speech_context`;
- `division_context`;
- completed-month political metrics.

The codebase also contains dedicated contextualisation logic for:

- Bills and debate sections;
- divisions;
- speeches;
- oral parliamentary questions;
- written parliamentary questions;
- issue classifications;
- voting components.

This creates future content opportunities without requiring an entirely new data architecture.

However, these datasets have strict semantic contracts. Content work must consume those contracts rather than reinterpret raw numbers casually.

---

# Critical semantic boundaries from the data contracts

The topical system must preserve these rules.

## Bill context

A speech or division is Bill-linked only through the certified exact `debate_section_id` relationship.

Do **not** infer that an event relates to a Bill merely because it occurred:

- on the same date;
- in the same debate;
- near a Bill discussion;
- under a similar heading.

## Bill stage

Do not infer a Bill stage from Bill ID + division date coincidence.

Stage attribution requires its own certified relationship/source.

## Motions

`motion_proceeding` describes parliamentary form.

It does not establish:

- political importance;
- policy significance;
- effectiveness;
- public controversy.

## Voting

Recorded-vote participation/agreement metrics are descriptive.

Do not present them as:

- political effectiveness;
- attendance generally;
- quality/performance;
- discipline without the precise metric definition.

Independent-group agreement is recorded-vote agreement among Independents, not party discipline.

## Parliamentary questions

A parliamentary-question record and an oral-question debate exchange are different units.

Do not multiply speech activity by question count or infer who formally took a question from observed transcript participation.

## Speech issue classification

Frequency shows how often classified speech content appeared.

It does not establish:

- support/opposition;
- subjective importance;
- party priority;
- policy quality.

These constraints are growth safeguards, not obstacles. They help EirePolitic distinguish itself through unusually careful political-data presentation.

---

# Content model

Use three content lanes rather than treating every post as either “news” or “evergreen.”

## Lane A — recurring structured content

Examples:

- Bill Tracker;
- monthly Party Speech Breakdown;
- latest polling carousel;
- future representative/profile series.

Purpose:

- predictable baseline output;
- systematic coverage;
- reliable data feed for experiments.

These posts should continue even when no major topical event occurs.

## Lane B — data-triggered topical content

Triggered by an objective change/event inside EirePolitic's data.

Examples:

- a Bill moves to a new certified stage;
- a Bill is enacted;
- a recorded division occurs in a certified Bill debate section;
- a new poll enters the polling dataset;
- a large measured polling change occurs relative to the previous poll;
- a new oral-question exchange appears;
- a notable descriptive change appears in daily issue activity;
- a newly available written-question/answer dataset produces an explainable public-record fact.

These are the strongest candidates for automation because the trigger comes from structured data rather than continuous manual news monitoring.

## Lane C — evergreen educational/reference content

Examples:

- how a Bill becomes law;
- what First Stage means;
- what Second Stage means;
- what Committee Stage means;
- what Report Stage means;
- what “enacted” means;
- how a Dáil division works;
- why some parliamentary decisions have no recorded member-by-member vote;
- what an amendment vote does and does not mean;
- how oral parliamentary questions work;
- the difference between a question record and a debate exchange;
- how EirePolitic classifies speech issues;
- what polling percentage-point change means;
- how to read EirePolitic political-data charts;
- how party attribution is handled historically;
- how constituency/representative records should be interpreted.

Purpose:

- search/discovery;
- saves;
- repeat usefulness;
- educational credibility;
- contextual support when a topic becomes current.

---

# Topical trigger taxonomy

Not every change in the database should become a post.

Define specific trigger classes.

## T1 — new official state change

Examples:

- Bill stage/status change;
- enactment;
- new certified parliamentary event.

Characteristics:

- high factual clarity;
- low subjective interpretation;
- potentially strong timeliness.

Recommended automation level:

**High for candidate generation; human review before publication until the format is proven.**

## T2 — new data release

Examples:

- new opinion poll;
- new completed monthly political-metrics period;
- new validated data batch exposing a recurring series.

Recommended automation level:

**Very high.** Existing factory patterns already suit this model.

## T3 — deterministic threshold/change trigger

Examples:

- largest change since previous poll exceeds a configured threshold;
- issue activity changes materially compared with a defined historical baseline;
- a measurable count/rank crosses a predefined threshold.

Important:

A threshold says the measurement changed. It does **not** mean the event is politically important.

Recommended wording:

`This was the largest measured change in [defined comparison window].`

Avoid:

`This was the most important political development.`

Recommended automation level:

**Medium.** Candidate generation can be automatic; commissioning must validate statistical and semantic rules first.

## T4 — unusual parliamentary process

Examples:

- Bill progression without a recorded division;
- amendment vote whose meaning is commonly misunderstood;
- grouped oral questions;
- procedural event that lends itself to an explainer.

These can create strong curiosity while remaining educational.

Recommended automation level:

**Medium.** Detect deterministically where possible, then map to an approved explainer template.

## T5 — external current-event match

A current story outside the pipeline makes one of EirePolitic's datasets newly relevant.

Example pattern:

```text
news/public discussion about topic X
        ↓
EirePolitic already holds certified Bill / speech / question / representative / polling data relevant to X
        ↓
create neutral “what the record shows” explainer
```

Recommended automation level:

**Low for publication; medium for candidate detection.**

External news can be monitored/researched by an LLM or future automation, but current-event posts should require source verification and review.

Do not create a fully autonomous news-commentary bot.

---

# Topical candidate eligibility rules

A candidate should normally satisfy all of these before entering production.

## 1. Freshness

The event/data change is recent enough that timing adds value.

Freshness windows should be configured per trigger rather than universally.

Examples:

- poll: usually shortly after ingestion/publication;
- Bill stage: shortly after official status confirmation;
- monthly metrics: when the completed period becomes available;
- evergreen tie-in: can be resurfaced whenever relevant.

## 2. Source confidence

The underlying data must be:

- validated;
- contract-compliant;
- attributable;
- sufficiently current for the claim.

Do not trade validation for speed.

## 3. Plain-language explainability

There must be an honest, understandable answer to:

> “Why might an ordinary person find this useful?”

This does not mean the item must be dramatic.

It means the post should have a useful explanatory angle.

## 4. Semantic safety

The available data must support the intended wording without speculative political interpretation.

## 5. Template fit

Prefer candidates that fit an existing approved visual/content template.

Do not create a new bespoke design for every topical event.

## 6. Duplication control

Do not generate a topical post that merely repeats an already scheduled recurring post unless the different format serves a distinct purpose.

---

# Do not create an “importance algorithm”

The system should not assign a black-box political-importance score to Bills, parties, politicians, or issues.

That creates editorial and neutrality problems.

Instead, a content-candidate ranker may use **operational signals** such as:

- freshness;
- data completeness;
- existence of a proven template;
- whether the topic has already been posted recently;
- historical audience response to the content family/topic;
- whether the event is a meaningful state change by an explicit rule;
- expected manual effort.

Keep these signals inspectable.

A high candidate rank means “good publication candidate under the growth system,” not “politically more important.”

---

# Suggested topical-candidate record

Do not implement yet. This is a proposed logical model.

```yaml
candidate_id: "..."
created_at_utc: "..."
trigger_type: bill_stage_change
source_product: bill_tracker
event_date: "..."
entity_type: bill
entity_id: "..."
plain_language_subject: "..."
source_refs:
  - "..."
freshness_hours: 6
template_id: bill_stage_update_v1
semantic_rule_ids:
  - bill_context_exact_section_only
review_required: true
status: candidate
experiment_tags:
  topicality: topical
```

Candidate generation should never equal automatic publication approval.

---

# Recommended topical formats

## TP-1 — “What changed?”

Best for:

- polling;
- Bill state changes;
- data updates.

Structure:

1. What changed?
2. Previous state/value.
3. Current state/value.
4. Necessary context/source.

This should be a reusable carousel/Reel archetype.

## TP-2 — “What this means procedurally”

Best for:

- Bill stages;
- Dáil/Seanad procedure;
- divisions;
- amendments.

Important:

Explain what the procedural event means, not its political desirability.

## TP-3 — “What the record shows”

Best for external-current-event tie-ins.

Structure:

```text
Current public question/topic
        ↓
Relevant official EirePolitic record
        ↓
Measured/descriptive result
        ↓
Limitations
```

This could become a distinctive EirePolitic format because it responds to topical interest without becoming commentary.

## TP-4 — “Three things in the record”

Best when multiple structured facts can be stated cleanly.

Examples:

- three Bills on a current topic;
- three recent parliamentary events;
- three descriptive data points.

Avoid cherry-picking facts to construct a political argument.

## TP-5 — “How we got here” timeline

Best for:

- legislation progression;
- repeated parliamentary events;
- polling history.

Timeline entries must come from certified dates/events.

## TP-6 — topical explainer bridge

A fresh event points users to an evergreen concept.

Example pattern:

```text
A Bill has just reached Second Stage.

What does Second Stage actually mean?
```

This is particularly efficient because one evergreen asset can support many future topical events.

---

# Evergreen library

The most scalable evergreen strategy is to build a **small reusable library**, not continually invent one-off educational posts.

## E1 — legislation basics

Priority candidates:

- `How a Bill becomes law in Ireland`;
- `What First Stage means`;
- `What Second Stage means`;
- `What Committee Stage means`;
- `What Report Stage means`;
- `What Final Stage means`;
- `What “enacted” means`;
- `What happens after enactment?` where source material supports a general explanation.

## E2 — voting/procedure

- `What is a Dáil division?`;
- `What does Tá / Níl mean?`;
- `Why a vote on an amendment is not always a vote on the whole Bill`;
- `How can something progress without a recorded division?`;
- `What is the difference between a voice decision and a recorded division?` where accurately sourced.

## E3 — parliamentary questions

The repository's question-context models create strong educational possibilities:

- `What is a parliamentary question?`;
- `Written vs oral parliamentary questions`;
- `Why several oral questions can share one debate exchange`;
- `Who appears in an oral-question exchange?`;
- `What EirePolitic can and cannot infer from question records`.

## E4 — political-data literacy

- `Percentage points vs percent change`;
- `How to read a polling trend chart`;
- `What one poll can and cannot tell you`;
- `What speech-frequency data measures`;
- `Why speech frequency does not equal party position`;
- `What recorded-vote participation measures`;
- `Why recorded-vote data is not the same as attendance`.

These posts can improve both audience understanding and EirePolitic's credibility.

## E5 — representatives and institutions

As relevant data products become available:

- `What is a TD?`;
- `What is a constituency?`;
- `Dáil vs Seanad`;
- `Government office vs party membership`;
- `Why historical party attribution matters when analysing old votes`.

Do not build explainers ahead of available source capability if they cannot be maintained accurately.

## E6 — “How EirePolitic measures this”

Methodology posts can themselves be useful content.

Examples:

- `How EirePolitic links a debate to a Bill`;
- `How speech issues are classified`;
- `How party-at-the-time attribution works`;
- `Why some records are excluded instead of guessed`.

These are likely lower-reach but high-trust/save content and useful pinned/profile references.

---

# Evergreen asset model

Evergreen content should be versioned and reusable.

Suggested metadata:

```yaml
evergreen_id: second_stage_explainer_v1
subject: second_stage
created_at: "..."
last_verified_at: "..."
source_refs:
  - "..."
template_id: parliamentary_explainer_v1
refresh_triggers:
  - source_semantics_changed
  - visual_template_changed
reuse_allowed: true
```

Do not duplicate the same explainer every time it becomes topical.

Use one of these patterns:

- reshare/repost the existing evergreen item where appropriate;
- create a topical wrapper pointing to it;
- regenerate from the same approved structured content if the visual template materially improves.

---

# Evergreen freshness policy

“Evergreen” does not mean never revalidated.

Each evergreen item should have one of these verification classes.

## Stable concept

Examples:

- glossary definitions tied to established procedure.

Review:

- annually;
- or when source/procedure changes.

## System-dependent explainer

Examples:

- how EirePolitic calculates/classifies a metric.

Review when:

- code/contract version changes;
- methodology changes;
- data source changes.

## Current-structure explainer

Examples:

- number/structure of representatives/institutions.

Review on:

- new Dáil/session;
- constituency/institutional changes;
- known source update.

The asset metadata should tell the future system when an explainer needs revalidation.

---

# Topical discovery without daily manual news research

The project should avoid requiring the user to scan Irish political news continuously.

Use this hierarchy.

## Level 1 — structured-data triggers

Highest priority.

The pipeline detects the event itself.

Examples:

- new poll;
- Bill change;
- completed monthly dataset;
- new relevant division/question event.

Manual effort:

near-zero after commissioning.

## Level 2 — scheduled LLM/current-events scan

Potential future capability:

A periodic research task reviews current Irish political/public-policy stories and asks:

> “Does EirePolitic already have structured data that can neutrally explain any of these?”

Output:

candidate list only.

It should record:

- event/source;
- relevant EirePolitic dataset;
- possible factual angle;
- freshness;
- confidence;
- why the connection is supported.

It should **not** publish automatically.

This could eventually be handled by an agent/automation if the return justifies it.

## Level 3 — user/manual observation

If the user sees a current issue worth explaining, a future LLM should inspect EirePolitic's data first and reuse existing templates.

Do not make manual observation the primary topical engine.

---

# Candidate queue rather than automatic publishing

Topical triggers should create a queue such as:

```text
candidate
→ source_validated
→ content_eligible
→ rendered
→ pending_review
→ approved/rejected
→ publication request
```

The current Director workflow already has human visual/content gates for new content.

Reuse that pattern.

Do not create a second approval system solely for topical posts.

Once a topical format becomes a proven recurring series, it can graduate into the mechanical recurring-series workflow with its own declared QA.

---

# Topic recurrence / anti-spam rules

Automation can easily overproduce.

Add explicit suppression rules.

## Duplicate entity cooldown

Avoid repeatedly posting the same Bill/topic unless a meaningful new state change occurs.

## Same-day clustering

Do not publish several near-identical political-data posts merely because multiple triggers fire in one batch.

Use scheduling/priority logic to spread lower-urgency items.

## Recurring-series collision

If a topical candidate will be covered by an imminent recurring post, decide whether to:

- suppress the topical item;
- accelerate the recurring item;
- use an evergreen explainer instead.

Do not publish both automatically.

## Topic diversity

Track recent subjects so the account does not unintentionally appear to focus disproportionately on one issue merely because that dataset generates more triggers.

This is a presentation/diversity safeguard, not an attempt to force artificial political balance.

---

# Content mix strategy

Do not set a rigid topical/evergreen percentage before baseline data and actual publication volume are known.

Instead classify every post as:

```text
recurring
topical
evergreen
```

Then use Insights to compare:

- non-follower reach;
- follows per 1,000 reached;
- shares per 1,000 reached;
- saves per 1,000 reached;
- 30-day long-tail reach.

After 4-8 weeks of classified data, decide whether a publication-slot policy is useful.

Possible later model:

- recurring content consumes its required slots;
- topical candidates compete for a limited weekly capacity;
- evergreen posts fill gaps and support topical moments.

Do not increase total volume merely to satisfy a ratio.

---

# Experiment programme

## TE-001 — topical vs procedural packaging

### Question

Does framing the same legislative event around the plain-language current change produce more non-follower discovery than a procedural series framing?

Example:

Control:

`Bill Tracker — Second Stage`

Treatment:

`This bill has reached Second Stage — what that means and what it does`

### Metrics

- non-follower reach;
- follows per 1,000 reached;
- shares;
- saves.

---

## TE-002 — topical polling vs routine polling

Classify polling posts by whether there is a clear measured change relative to the prior observation.

Question:

Do change-led polling posts acquire more non-followers than routine latest-percentages posts?

Do not create an arbitrary “dramatic poll” label.

Use explicit numerical rules.

---

## TE-003 — evergreen process explainer

Test one foundational explainer, recommended:

`What does Second Stage actually mean?`

Compare its:

- 7-day reach;
- 30-day reach;
- saves;
- shares;
- follow conversion;

against ordinary procedural Bill Tracker posts.

Primary learning:

Does evergreen reference content have stronger long-tail/save behaviour?

---

## TE-004 — topical + evergreen bridge

When a real Bill reaches a defined stage:

- publish/use the topical update;
- point to or resurface the relevant stage explainer.

Measure whether the pair generates:

- additional saves/profile visits;
- longer-tail engagement;
- follows.

Do not post two redundant carousels.

---

## TE-005 — “what the record shows” current-event format

Select a real current event only when EirePolitic has relevant certified structured data.

Produce a neutral factual post grounded in the record.

Success criteria:

- materially stronger non-follower reach than baseline;
- normal or better follow conversion;
- no corrections/semantic problems;
- acceptable manual research time.

Track human time required. If each post requires extensive research, this format should remain occasional.

---

## TE-006 — evergreen resurfacing

Compare:

- creation of a new explainer;
- resurfacing/reposting an existing validated evergreen explainer when it becomes topical again.

Question:

Can EirePolitic capture renewed interest without generating duplicate creative work?

---

# Experiment metadata

Record:

```text
content_lane                recurring | topical | evergreen
trigger_type
topic_id
entity_type
entity_id
source_product
freshness_hours
external_event_match        true/false
evergreen_id                nullable
evergreen_version           nullable
reuse_type                  new | repost | topical_wrapper
experiment_id
variant
manual_research_minutes
```

The `manual_research_minutes` field is important because this growth programme explicitly optimises for the user's limited time.

A format that performs slightly better but consumes large amounts of manual work may be inferior overall.

---

# Success metrics

## Topical content

Primary:

- non-follower reach;
- follows per 1,000 reached;
- shares per 1,000 reached.

Secondary:

- profile visits;
- speed from validated event to publish-ready candidate;
- manual research minutes.

## Evergreen content

Primary:

- saves per 1,000 reached;
- shares per 1,000 reached;
- follows per 1,000 reached;
- 30-day reach relative to 7-day reach.

Secondary:

- reuse count;
- search-originated discovery where available;
- profile/navigation usefulness.

## System-level metric

Measure **growth return per manual minute** for formats requiring human intervention.

Conceptually:

```text
incremental follows or non-follower reach
-----------------------------------------
manual operator minutes
```

Do not over-formalise the formula before baseline data exists; the principle is that human time is a scarce resource.

---

# Candidate automation architecture

Do not implement until specific trigger classes are commissioned.

Possible structure:

```text
instagram/
└── growth/
    ├── topical_candidates.py
    ├── trigger_rules.py
    ├── suppression.py
    └── evergreen_registry.yml
```

or equivalent placement under the existing Director/project architecture.

Prefer extending existing project/workflow patterns over building a parallel content engine.

## Trigger engine responsibilities

Only:

- read validated products;
- detect explicit configured conditions;
- write candidate metadata;
- attach source lineage;
- suppress duplicates;
- route candidate to an existing/new commissioned project.

It should **not**:

- invent political significance;
- autonomously write unsupported commentary;
- approve publication;
- bypass existing review/ready gates.

---

# Recommended initial implementation order

## Step 1 — build evergreen library first

This is low risk and reusable.

Recommended first three:

1. `How a Bill becomes law in Ireland`;
2. `What does Second Stage mean?`;
3. `How to read a Dáil division / why an amendment vote is not always a vote on the whole Bill`.

These directly support Bill Tracker and reduce the knowledge barrier for general audiences.

## Step 2 — polling trigger

The polling factory already uses a latest-data model.

Add/commission a clear “new poll/change” candidate rule before inventing more complex topical detection.

## Step 3 — Bill state-change candidate

Use certified official status/stage data only.

Create candidate, not auto-publish.

## Step 4 — topical-explainer bridge

When a Bill-stage trigger fires, associate the relevant evergreen stage explainer.

## Step 5 — political-metrics candidate prototypes

Investigate one at a time:

- oral-question exchange;
- daily issue activity;
- contextual division;
- written-question answer.

For each, first create a **single representative post** using the Director's “new post” workflow and validate semantics/visual utility.

Only after successful commissioning should it become a reusable trigger/template.

## Step 6 — external-current-event matching

Add only after the structured-data topical engine is useful.

This is the most manual/error-prone lane and should not be the foundation of the strategy.

---

# Future implementation workflow for a new topical trigger

A future LLM chat should follow this sequence.

1. Read this document and the relevant data contract.
2. Inspect current `main` and determine whether the needed data product already exists.
3. If the product exists, use it; do not rebuild its extraction/transformation.
4. Define the trigger in plain language.
5. Define exactly what the trigger **does and does not mean**.
6. Define minimum source/validation state.
7. Test the rule against historical data.
8. Count how often it would have fired.
9. Inspect false positives/repetitive candidates.
10. Define suppression/cooldown.
11. Select an existing visual format if possible.
12. If a new format is required, follow Director workflow 6.1: content gate → one representative slide → visual-direction gate → full render → approval.
13. Store experiment/trigger metadata.
14. Do not enable unattended publication.
15. Measure candidate usefulness and manual review burden.
16. Promote to recurring automation only after repeated acceptable results.

---

# Future workflow for an evergreen explainer

1. Select one high-value recurring concept.
2. Identify the canonical source/contract.
3. Write the plain-language explanation with explicit semantic limits.
4. Reuse current visual primitives.
5. Prototype one representative slide first.
6. Get visual/content approval.
7. Render the complete explainer.
8. Assign an `evergreen_id` and version.
9. Record `last_verified_at` and refresh triggers.
10. Publish/measure.
11. Reuse instead of recreating when the topic becomes relevant again.

---

# Workload / cost assessment

| Activity | Expected upside | Setup effort | Recurring manual effort | Cost | Automation potential |
|---|---|---|---|---|---|
| Bill-stage/state trigger | High | Medium | Very low | €0/very low infra | Very high |
| New-poll trigger | High | Low | Near-zero | €0 | Very high |
| Evergreen Bill-stage explainers | High | Medium once | Very low | €0 | High |
| Dáil-vote/process explainers | High | Medium once | Very low | €0 | High |
| Political-metrics event triggers | Medium-high | Medium | Low | €0/very low infra | High after commissioning |
| Evergreen data-literacy posts | Medium | Medium once | Very low | €0 | High |
| External current-event matching | Potentially high | Medium | Low-medium | €0 | Medium |
| Daily manual news research | Uncertain | Low setup | High | €0 | Low |
| Bespoke topical graphics | Variable | Low setup | High recurring | €0 | Low |

The strongest strategy is **structured-data triggers + reusable evergreen explainers**, not becoming a manually operated news desk.

---

# Risks and safeguards

## Speed vs accuracy

Do not weaken batch validation or source certification merely to publish sooner.

## Political significance inference

A spike/change/event is not automatically “important,” “historic,” or “a major issue.”

Use descriptive statistical/procedural language.

## News-source contamination

When external news triggers a post, distinguish:

- what the news outlet/public statement says;
- what EirePolitic's official/structured record independently shows.

Do not merge claims without attribution.

## Topic overrepresentation

Automated triggers may favour data-rich topics. Track recent topic mix and avoid accidental monotony.

## Evergreen staleness

Version and revalidate explainers.

## Volume inflation

More candidate triggers should not automatically mean more published posts.

The content queue needs suppression/prioritisation.

## Duplicate inference

Never derive meaning from loose date/debate proximity when the repository contracts require exact certified joins.

---

# Information that may require the user

No major user input is required to continue planning.

Material decisions should be requested only when:

- choosing which new topical trigger to commission first after polling/Bills;
- approving a genuinely new visual format;
- deciding whether an external-current-event workflow is worth its manual cost;
- authorising any new automated scheduling/publication behaviour.

The user should not be asked to manually monitor news or select routine topical candidates.

---

# Handoff instructions for future LLM chats

When implementing this workstream:

1. Read this page and the master growth plan.
2. Read current Discovery Hooks, Insights, and Caption workstreams.
3. Inspect current `Eirepolitic-data-pipeline` `main`.
4. Read `director/projects.yml`, `director/data_products.yml`, `director/workflows_v1.md`, and the relevant downstream contract before designing a trigger.
5. Prefer existing validated data products over new scraping/extraction.
6. Treat repository data contracts as semantic guardrails.
7. For current external political events, search current reliable sources and date them explicitly.
8. Distinguish external-event claims from what EirePolitic's own structured record supports.
9. Do not infer Bill context/stage from loose temporal proximity.
10. Do not infer party position/priority from speech frequency.
11. Do not infer general attendance/effectiveness from recorded-vote metrics.
12. Define trigger, semantic meaning, suppression rule, and source lineage before building visuals.
13. Generate candidates before considering auto-publication.
14. Reuse the existing Director content/visual approval workflow.
15. Prototype one representative item before scaling.
16. Add structured topicality/trigger/evergreen metadata for Insights.
17. Track manual research minutes.
18. Promote only low-work, high-performing formats to recurring automation.
19. Do not modify production schedules/publishing configuration without explicit approval.
20. Update this page with successful triggers, false positives, retired rules, evergreen assets, and measured performance.

---

# Completion criteria

This workstream is mature when:

- recurring, topical, and evergreen posts are explicitly classified;
- at least one data-triggered topical format runs with very low manual effort;
- a small evergreen explainer library supports recurring/current content;
- topical candidates are generated from explicit deterministic rules rather than subjective “importance” guesses;
- external-current-event matching, if used, produces candidate suggestions rather than autonomous political commentary;
- semantic contracts are preserved;
- duplicate/volume suppression exists;
- Insights can compare topical vs recurring vs evergreen performance;
- the system can reuse evergreen work when topics become current again;
- growth return is evaluated against manual time as well as reach/follows.

The target end state is **an account that feels timely without requiring the operator to behave like a full-time social-media editor**.
