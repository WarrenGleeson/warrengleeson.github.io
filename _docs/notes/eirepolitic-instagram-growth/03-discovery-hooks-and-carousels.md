---
title: "EirePolitic Instagram Growth: Discovery Hooks and Carousel Packaging"
description: "Detailed plan for improving first-slide hooks, carousel packaging, and non-follower discovery without weakening factual or parliamentary accuracy."
group: "Notes"
order: 63
---

# Discovery Hooks and Carousel Packaging

## Status

**Planning state:** detailed investigation/experiment guide prepared.  
**Production changes:** none.  
**Priority:** highest content-side workstream.  
**Dependencies:** Insights/Measurement should provide the eventual evidence loop; implementation can begin with controlled template experiments before the full analytics layer is complete if results are still recorded manually.

## Objective

Increase the probability that a person who does not already follow EirePolitic will:

1. understand the subject of a post immediately;
2. recognise why the information may be useful or interesting;
3. continue into the carousel;
4. share/save the post where appropriate;
5. visit the profile and potentially follow.

The goal is **not** to make neutral political information sensational. The goal is to remove unnecessary friction between the underlying information and a general audience.

---

## Core diagnosis from the current repository

EirePolitic already contains substantially more accessible information inside many carousels than it exposes on the first slide.

### Bill Tracker

The current Bill Tracker cover renderer is built around:

- `BILLS OF THE`;
- `CURRENT SESSION`;
- parliamentary status such as `ENACTED`;
- an edition label such as `POST 1`;
- a short series introduction;
- three **formal bill titles**.

The same content package already contains much more understandable fields for each bill:

- `what` — what the bill does;
- `effect` — likely practical effect described from the legislation/source material;
- `backed` — arguments made in support;
- `concerns` — concerns raised;
- precise vote semantics;
- result/status context.

Therefore the main acquisition problem is not lack of material. It is **selection and hierarchy on the cover**.

The present cover effectively asks a non-specialist to decide whether to continue based on parliamentary terminology and formal legislation titles. A discovery-oriented cover can instead surface a plain-language subject or consequence while keeping the formal title and legal precision on subsequent slides.

### Party Speech Breakdown

The current party-profile cover emphasises:

- `Party Speech Breakdown`;
- month;
- party logo;
- classified-speech count;
- average speeches per TD.

The analytical slides then contain the information that is more likely to create curiosity:

- the issues most discussed;
- issues discussed more than the cross-party average;
- issues discussed more than average per TD.

Important semantic safeguard already exists in the project glossary:

> speech counts show how often an issue was discussed, **not the party/group's position on it**.

Any acquisition-oriented cover must preserve that distinction.

### Polling

The current polling factory already contains comparatively accessible framing:

- `Latest Polling Percentages`;
- `Who's Up and Who's Down?`;
- `Six Months of Polling`.

Polling therefore needs less conceptual translation than Bills or parliamentary procedure. Its largest packaging opportunity is likely to be **surfacing the most informative change or comparison on the cover**, while maintaining poll source/methodology context and avoiding predictive or winner/loser language.

---

## Current platform context

The following platform observations were verified from Meta material during the October 2026 planning review and should be rechecked before implementation because recommendation systems change.

- Instagram recommendations increasingly favour original material; Meta reported in January 2026 that 75% of Instagram recommendations in the US were original posts.
- Instagram has explicitly changed recommendation systems to give smaller original creators more opportunity to reach non-followers.
- Political/civic content is again being recommended using personalised interest signals rather than being categorically excluded from recommendations.
- Instagram's Professional Dashboard includes a Best Practices area covering creation, engagement, reach, and guidelines.

Implication for EirePolitic:

**Do not assume political subject matter makes discovery futile.** EirePolitic should optimise the clarity, originality, usefulness, and recommendation eligibility of the material it already produces.

This workstream should not attempt to reverse-engineer a single “algorithm.” It should make the content more immediately legible and useful, then measure the outcome.

---

# Design principle: acquisition layer vs evidence layer

A useful mental model is to split each carousel into two functions.

## Acquisition layer

Usually slide 1, sometimes slides 1-2.

Its job is to answer:

- What is this about?
- Why should I continue?
- What will I understand if I swipe?

It should use plain language and strong visual hierarchy.

## Evidence/detail layer

The remaining slides preserve:

- formal titles;
- exact parliamentary stage;
- dates;
- vote propositions;
- party breakdowns;
- source notes;
- methodology;
- caveats;
- glossary material.

**The acquisition layer may simplify wording, but it must never simplify the underlying claim beyond what the evidence layer supports.**

---

# Safe hook-writing standard

Every proposed hook should pass all of these checks before publication.

## 1. Evidence traceability

Every factual phrase in the hook must be traceable to:

- the relevant bill text/status;
- official Oireachtas data;
- the approved polling source;
- the approved classified-speech dataset;
- another explicitly approved source.

If the hook requires an interpretation not present in the source material, either qualify it or reject it.

## 2. No inferred motive

Do not use hooks such as:

- `Why the Government really passed this`;
- `What Party X doesn't want you to know`;
- `The hidden reason behind this vote`.

EirePolitic can describe recorded arguments and actions, not infer hidden motives.

## 3. No false vote meaning

A recorded Tá/Níl must not be described as support/opposition to the entire bill unless the division proposition actually represents that.

For amendments/procedural divisions, the hook must reflect the actual proposition.

Example:

Safe:

`TDs voted 67–79 on adding services to the settlements bill.`

Unsafe:

`79 TDs voted against the settlements bill.`

when the recorded vote was only on an amendment.

## 4. No exaggerated consequence

Avoid unsupported absolutes such as:

- `This law changes everything`;
- `This will transform Irish housing`;
- `The bill that could end...`;
- `Ireland just banned...`

unless the exact proposition genuinely supports that wording.

Prefer concrete descriptions of what the law changes.

## 5. No adversarial curiosity gap

Curiosity is acceptable; concealment is not.

Safe:

`Three laws passed this session — here's what they change.`

Poor fit:

`You won't believe what the Dáil just passed.`

## 6. General-audience terminology first

Where possible, first-slide language should use:

- `law` / `bill` with explanation;
- `Dáil vote` rather than `division`;
- `became law` rather than only `enacted`;
- `what changed` rather than `remaining stages`.

Formal parliamentary terminology should still appear where precision requires it.

## 7. Neutral political framing

Hooks may surface:

- change;
- difference;
- process;
- numbers;
- timing;
- factual disagreement;
- recorded debate;
- practical function;
- unusual procedure.

They should not tell the audience who is right, who “won,” who is competent, or which policy is desirable.

---

# Hook archetypes

The aim is to create a **small reusable vocabulary of hook structures** that the pipeline can eventually generate safely.

## H1 — Plain-language consequence

Structure:

`What this [bill/law/change] actually does`

Best for:

- legislation;
- regulations;
- parliamentary decisions.

Examples:

- `What Ireland's new AI regulation law actually does`
- `What the pharmacy contraception law changes`

Use only when the body contains a defensible plain-language effect summary.

## H2 — Multi-item utility roundup

Structure:

`[N] laws/bills — what each one changes`

Best for:

- Bill Tracker batches;
- monthly/session roundups.

Example:

`3 laws passed this session — what each one changes`

This is the strongest candidate to test against the present Bill Tracker series/status cover.

## H3 — What changed?

Structure:

`What changed in [topic/time period]?`

Best for:

- polling;
- bill-stage progression;
- monthly issue patterns.

Examples:

- `What changed in the latest Irish polling?`
- `What changed when this bill reached the Dáil?`

The subsequent slide must answer the question clearly.

## H4 — Key-number lead

Structure:

`[Number]: [plain-language meaning]`

Best for:

- polling change;
- vote result;
- number of bills;
- speech/topic counts.

Example:

`81–58: the Dáil vote that moved Ireland's AI regulation bill forward`

Only use a vote number when the proposition can be described accurately in the available space.

## H5 — Process explainer

Structure:

`What happens when [parliamentary event]?`

Best for:

- no recorded division;
- bill stages;
- amendments;
- Dáil/Seanad process.

Examples:

- `How can a bill pass without a recorded vote?`
- `What does Second Stage actually mean?`

High evergreen/save potential.

## H6 — Measured pattern

Structure:

`What did [party/group] discuss most in [month]?`

Best for:

- Party Speech Breakdown.

Example:

`What did Fianna Fáil discuss most in September?`

Required accompanying qualifier:

The measurement is frequency of classified speeches, **not position, priority, importance, or support**.

Avoid:

`What Fianna Fáil cared about most`

because speech frequency does not establish subjective importance.

## H7 — Comparison without judgement

Structure:

`How [measured subject] compares with [baseline]`

Best for:

- party speech patterns;
- polling changes;
- cross-period comparisons.

Examples:

- `Which issues did Labour discuss more than the cross-party average?`
- `How the latest poll compares with the previous one`

Avoid winner/loser framing when the data merely shows difference.

## H8 — Specific surprising fact

Structure:

A concrete fact that is genuinely present in the data and understandable without specialist knowledge.

Example:

`This bill became law without a recorded member-by-member Dáil vote.`

Follow with:

`Here's how that can happen.`

This is potentially powerful because the curiosity is inherent in the procedure, not manufactured.

## H9 — Direct utility promise

Structure:

`A quick guide to [topic]`

Examples:

- `A quick guide to how a bill becomes law in Ireland`
- `A quick guide to reading a Dáil vote`

Best for evergreen/saveable material.

---

# Content-family packaging plans

## A. Bill Tracker

### Current architecture

Current cover:

```text
BILLS OF THE
CURRENT SESSION
ENACTED · POST X
[series intro]
IN THIS POST
1. [formal bill title]
2. [formal bill title]
3. [formal bill title]
```

The formal bill titles are accurate but often long and cognitively expensive.

### Recommended test architecture

Do not initially redesign all nine slides.

Test a **cover-only acquisition variant** while preserving the existing eight detail/glossary slides.

Possible cover:

```text
3 LAWS PASSED THIS SESSION

WHAT EACH ONE CHANGES

Energy security
Settlement goods imports
AI regulation

Swipe for the bills, votes and what happened →
```

The subject labels above are illustrative; actual generation rules must be derived from approved plain-language fields and reviewed for accuracy.

### Formal title placement

Keep the full formal title:

- on the first detail slide for the bill;
- in caption/source context where useful;
- in metadata.

It does not need to carry the full discovery burden on the cover.

### Recommended first experiment

**Control:** current `BILLS OF THE CURRENT SESSION` cover.  
**Treatment:** `3 laws passed this session — what each one changes` cover.  
**Everything else:** unchanged as far as practical.

This isolates packaging rather than conflating it with a complete redesign.

### Future Bill Tracker variants

After the first test:

- one-bill deep dive vs three-bill roundup;
- “what it does” lead vs “vote/result” lead;
- process-based hooks for unusual parliamentary events;
- stage-specific cover language for First/Second/Committee/Final stages.

Do not assume enacted bills are always the strongest acquisition posts. Measure stage/topic separately.

---

## B. Party Speech Breakdown

### Current architecture

Each party receives a five-slide carousel with a logo-led cover and summary statistics before the analytical issue slides.

The acquisition opportunity is to surface the **measured topic result** sooner.

### Candidate cover architecture

```text
WHAT DID [PARTY] DISCUSS MOST?

[MONTH YEAR]

Based on classified Dáil speeches
```

Optional cover result after testing:

```text
[TOP ISSUE]
was the party's most-discussed classified issue this month
```

Only use a top-issue result if the underlying metric is stable and clearly explained.

### Required semantic label

Every acquisition-oriented version must preserve wording equivalent to:

`Based on classified Dáil speeches. Frequency does not show the party's position on an issue.`

This can appear on slide 2 or in a compact cover/footer treatment if readable.

### Avoid

- `What mattered most to [party]`;
- `[party]'s priorities this month`;
- `What [party] believes`;
- `What [party] supports`.

The current dataset does not establish those claims.

### Recommended first experiment

**Control:** logo + `Party Speech Breakdown`.  
**Treatment:** `What did [party] discuss most in [month]?`  
**Content:** same party/month and analytical slides.

Because eleven parties/groups are generated per period, this family may eventually provide a useful repeated sample for headline testing, but party identity itself is a major confounder. Do not compare one party's control against another party's treatment and call that a headline test.

A proper test should rotate variants across comparable periods/parties or use repeated observations.

---

## C. Polling

### Current architecture

The current four-slide sequence already has readable analytical titles.

The main question is whether slide 1 should show:

- current percentages;
- change from previous poll;
- a 30-day comparison;
- a six-month trend;
- a concise “what changed?” summary.

### Safe framing

Polling hooks should specify:

- that the figure is a poll/polling result;
- source/date where practical;
- comparison basis;
- that movement is measured rather than predicted.

Avoid:

- `Who's winning Ireland?`;
- `Who will win the election?`;
- `Party X is on course to...`;
- probability/prediction language not contained in the source.

### Recommended first experiment

**Control:** `Latest Polling Percentages`.  
**Treatment:** `What changed in the latest Irish poll?` with the largest measured movements shown visually.

Primary success measure should be acquisition/distribution metrics, not whether the treatment creates more comments.

---

# Carousel architecture principles

## Slide 1 — earn the swipe

Slide 1 should normally contain:

- one main idea;
- a small number of words;
- subject/context;
- EirePolitic visual identity;
- optional evidence cue such as date/source/“3 laws.”

It should not attempt to function as an executive summary of the entire carousel.

## Slide 2 — fulfil the promise quickly

Do not make users swipe through branding, definitions, or methodology before receiving the information promised by the cover.

The first substantive answer should normally appear on slide 2.

## Middle slides — evidence and comparison

Use the middle of the carousel for:

- what happened;
- what it means procedurally;
- charts;
- comparisons;
- recorded arguments;
- vote breakdowns.

## Final slide — utility, caveat, next action

Depending on the series, the final slide can contain:

- glossary/methodology;
- source/caveat;
- “how to read this” reference;
- related EirePolitic series;
- restrained CTA.

Do not automatically add a generic “Follow for more” slide to every carousel if it displaces useful information. Test CTA placement separately.

---

# Carousel depth strategy

There is no reason to assume a universal optimal slide count.

EirePolitic should test **information density and completion behaviour**, not chase a generic social-media rule.

## Existing baselines

- Bill Tracker: 9 slides for a three-bill post.
- Party Speech Breakdown: 5 slides per party/group.
- Polling: 4 slides.

These provide natural experimental baselines.

## Candidate depth experiments

### Bill Tracker

Compare:

- current 9-slide multi-bill format;
- shorter 5-6 slide summary version;
- one-bill 3-5 slide deep dive.

Do not shorten if it forces removal of essential vote semantics or caveats.

### Party profile

The current 5-slide length is already compact. Prioritise cover testing before reducing slide count.

### Polling

The current 4-slide format is also compact. Test slide ordering before changing depth.

---

# Visual hierarchy rules

## Cover text hierarchy

Aim for no more than three conceptual layers:

1. main hook;
2. subject/date/context;
3. small source/series identifier.

Avoid making the EirePolitic series name the largest text unless the series itself is already recognisable to the audience.

## Formal title length

Long formal legislative titles should not automatically determine cover font size/layout.

Use:

- a plain-language subject label on the cover;
- formal title on detail slide;
- full formal title in metadata/caption as appropriate.

## Numbers

Numbers are useful when self-explanatory:

- `3 laws`;
- `81–58`;
- `+4 points`;
- `6 months`.

A number without a clear denominator/comparison is not a hook.

## Branding

Keep EirePolitic branding consistent but subordinate to the informational promise.

The user should recognise the post as EirePolitic without the logo/series title consuming the most valuable visual area.

---

# Automation model

The long-term goal is not manual headline writing for every post.

The pipeline should eventually support a constrained, auditable hook-generation layer.

## Suggested structured fields

Do not implement yet, but future project schemas may support fields similar to:

```yaml
acquisition:
  hook_id: bill_roundup_plain_language_v1
  hook_family: multi_item_utility
  headline: "3 laws passed this session"
  subheadline: "What each one changes"
  audience_level: general
  experiment_id: DH-001
  variant: treatment
  source_fields:
    - series.status
    - posts.post1.bills[*].what
  review_state: approved
```

The rendered image should be deterministic from approved structured text.

## Generation rule

Prefer this sequence:

```text
structured political data
        ↓
approved plain-language factual summary
        ↓
constrained hook template
        ↓
semantic/length checks
        ↓
human review during commissioning
        ↓
reusable approved rule
        ↓
automated production
```

Do not introduce an unconstrained LLM that invents hooks immediately before automated publishing without review/validation.

LLMs can help propose candidate wording during commissioning, but production text should come from deterministic approved inputs/rules unless a separate governed generation system is later approved.

---

# Suggested QA rules for acquisition covers

Future renderers should automatically validate:

- headline present;
- headline within maximum line count;
- no text clipping;
- plain-language subject/context present;
- source/brand footer present where required;
- banned placeholder/debug terms absent;
- experiment metadata present during active tests;
- formal title retained on required detail slide;
- relevant caveat present for speech/poll/vote content;
- slide dimensions correct;
- cover variant recorded in manifest/publication metadata.

For Bill Tracker specifically, QA should ensure that simplifying the cover does **not** remove the formal bill identity from the carousel.

---

# Experiment metadata

Each publication used in this workstream should eventually record:

```text
experiment_id
variant
content_family
hook_family
headline_text
subheadline_text
cover_renderer_version
cover_subject_count
carousel_slide_count
content_topic
parliamentary_stage
topicality
published_at
```

Where possible, use canonical controlled values rather than free text.

Example:

```yaml
experiment_id: DH-001
variant: treatment
content_family: bill_tracker
hook_family: multi_item_utility
cover_renderer_version: bill_tracker_cover_acquisition_v1
carousel_slide_count: 9
parliamentary_stage: enacted
```

This metadata should join to the Insights system by publication ID/version rather than being inferred after publication.

---

# Experiment programme

## DH-001 — Bill Tracker cover translation

### Question

Does plain-language cover framing outperform the current series/formal-title cover?

### Control

Current cover renderer.

### Treatment

Plain-language roundup cover, e.g.:

`3 laws passed this session`  
`What each one changes`

### Keep constant

- bill set;
- carousel detail slides;
- caption as far as practical;
- posting window where practical;
- visual palette/brand.

### Primary metrics

At matched post-age checkpoints:

- non-follower reach;
- follows per 1,000 reached where available;
- shares per 1,000 reached;
- saves per 1,000 reached.

### Secondary

- profile visits per 1,000 reached;
- carousel consumption/completion if Instagram exposes a useful measure.

### Decision rule

Do not declare a winner from a single pair unless the difference is extreme and repeated by supporting indicators. Repeat across multiple comparable publications.

---

## DH-002 — Question vs statement

Examples:

Question:

`What changed in the latest Irish poll?`

Statement:

`Latest Irish poll: the biggest changes`

Keep the underlying chart/data identical.

Measure acquisition/distribution metrics.

---

## DH-003 — Party profile generic vs measured-question cover

Control:

`Party Speech Breakdown`

Treatment:

`What did [party] discuss most in [month]?`

Required caveat remains in carousel.

Do not compare different parties as if they were identical experimental subjects. Use repeated observations/rotation.

---

## DH-004 — Formal title vs plain-language subject label

Suitable for legislation.

Control:

full formal bill title on cover.

Treatment:

plain-language label such as:

`Pharmacy contraception prescribing`

with formal title moved to the next slide.

The label must be reviewed for semantic completeness.

---

## DH-005 — Key number vs non-number cover

Examples:

- vote result prominently displayed vs not displayed;
- poll movement prominently displayed vs generic latest-poll cover.

Only use where the number is meaningful without misleading context.

---

## DH-006 — Carousel depth

Run only after cover packaging improves.

Compare matched formats at different depths.

Primary question:

Does removing lower-value slides improve acquisition/completion without reducing saves/shares or factual completeness?

---

# Test sequencing

Do not test everything simultaneously.

Recommended order:

1. Bill Tracker plain-language cover vs current cover.
2. Polling “what changed?” vs latest-percentages cover.
3. Party speech measured-question cover vs generic series title.
4. Formal-title vs plain-language subject label.
5. Key-number prominence.
6. Slide ordering/depth.
7. CTA interaction with successful cover formats.

This order attacks the highest-likelihood friction first: first-slide comprehension.

---

# Topic selection and confounding

Political topics vary enormously in inherent public interest.

A cover about housing, AI, health, or a highly current international issue may outperform another cover because of subject matter rather than design.

Therefore every experiment record should include:

- topic;
- topical/current-event relevance;
- content family;
- parliamentary stage;
- party where applicable;
- post age;
- format.

Use repeated tests and medians rather than relying solely on raw winner/loser comparisons.

Where sample sizes remain small, treat results as directional rather than statistically conclusive.

---

# What not to optimise for

## Likes alone

A cover that produces likes from existing followers but little non-follower discovery/follow conversion is not necessarily an acquisition improvement.

## Comments alone

Political comments can be high-volume without creating useful audience growth. Do not deliberately create ambiguity or controversy to increase comment counts.

## Clickbait swipe rate

A hook that earns a swipe but disappoints the user is not a sustainable win. Share/save/follow outcomes matter more.

## Maximum information density

The first slide does not need to prove the account's thoroughness. The rest of the carousel does that.

---

# Implementation decision gates

Before modifying a production content family, a future chat should present these decisions to the user.

## Gate A — test family

Which family is being commissioned first?

**Recommended:** Bill Tracker.

Reason: the gap between formal cover language and accessible internal content is clearest, so the expected learning value is high.

## Gate B — cover-only vs full redesign

**Recommended:** cover-only first.

This isolates the acquisition variable and preserves known-good detail slides.

## Gate C — experimental coexistence

Decide how control/treatment are produced without accidentally publishing duplicates.

Preferred commissioning approach:

- renderer supports both variants;
- preview both;
- publication chooses one approved variant per eligible post according to the experiment schedule;
- variant is recorded in publication/growth metadata.

Do **not** publish both near-identical versions to the same Instagram audience merely to create an A/B test unless Instagram provides a supported testing mechanism for that post type.

## Gate D — deterministic vs generated hook text

**Recommended initially:** deterministic approved hook templates populated from structured fields.

This is safer and easier to audit than open-ended production generation.

---

# Suggested implementation path for Bill Tracker

This is a future implementation guide, not authorisation to change the production repository now.

## Stage 1 — commissioning branch

1. Inspect current `main` and Bill Tracker renderer/tests.
2. Create a branch.
3. Preserve `render_cover()` as the control or version it explicitly.
4. Add a separate acquisition-cover renderer.
5. Add structured acquisition fields to a commissioning/test fixture, not silently to production content.
6. Render both covers against the same existing post.
7. Produce a contact sheet showing control/treatment side by side.
8. Verify formal titles remain in the detail slides.
9. Run existing QA plus new acquisition-cover QA.
10. Present previews for approval.

## Stage 2 — experiment metadata

After cover approval:

1. define `DH-001` metadata;
2. ensure publication manifest can retain variant identity without altering substantive source data;
3. ensure Insights can join the publication to the variant;
4. document the test schedule.

## Stage 3 — controlled publication

Only after explicit approval:

1. choose treatment/control according to the documented schedule;
2. publish through the existing pipeline;
3. collect 72h/7d/30d metrics;
4. repeat across enough comparable posts;
5. decide whether to promote the treatment to the default renderer.

Do not replace the current production renderer before the treatment has passed visual/semantic QA and received explicit approval.

---

# Workload / cost assessment

| Action | Expected upside | Setup effort | Recurring manual effort | Cost | Automation potential |
|---|---|---|---|---|---|
| Plain-language Bill Tracker cover | Very high | Low-medium | Near-zero after commissioning | €0 | Very high |
| Polling change-led cover | High | Low | Near-zero | €0 | Very high |
| Party speech question-led cover | High | Low-medium | Near-zero | €0 | Very high |
| Hook archetype library | High | Low | Near-zero | €0 | Very high |
| Formal-title relocation | Medium-high | Low | None | €0 | Very high |
| Key-number cover tests | Medium-high | Low | None | €0 | Very high |
| Carousel-depth tests | Medium | Medium | Low | €0 | High |
| Bespoke manual hooks per post | Variable | Low setup | High recurring | €0 | Low | 

The preferred strategy is to invest once in constrained templates, then let the existing content factory scale the successful packaging.

---

# Risks and safeguards

## Semantic drift

The greatest risk is making a hook more readable by making it less true.

Mitigation:

- source-field lineage;
- controlled hook families;
- commissioning review;
- automated checks;
- formal detail retained in later slides.

## False political inference

Particularly important for:

- speech frequency;
- amendment votes;
- “no recorded vote” cases;
- polling movement.

The hook must describe the measured event, not a broader political conclusion.

## Over-standardisation

One hook formula will become repetitive if applied to every series.

Maintain a small family of safe archetypes and choose based on data type.

## Excessive experimentation

Do not turn every post into a different design. Establish a stable control, test one meaningful change, then standardise winners.

## Production instability

Do not refactor established analytical/detail renderers merely to improve the cover unless necessary.

---

# Success criteria for this workstream

This workstream is successful when EirePolitic has:

1. a documented safe-hook standard;
2. a small reusable library of acquisition hook archetypes;
3. at least one commissioned discovery-oriented cover variant for each major content family;
4. structured experiment metadata tied to publication identity;
5. measured evidence showing which cover styles improve non-follower discovery/follow conversion;
6. deterministic automation for proven formats;
7. no reduction in sourcing, parliamentary precision, or neutrality.

The ideal end state is that the production system automatically creates content that is **as easy to enter as it is rigorous once opened**.

---

# Information that may require the user

No major user input is needed to continue planning this workstream.

During actual visual commissioning, the user should approve only material choices such as:

- whether the first Bill Tracker experiment should be cover-only as recommended;
- the final visual direction if two valid cover designs are materially different;
- promotion of a tested variant to the production default.

The future LLM should not ask the user to manually invent hooks or research topics that can be derived from the structured content.

---

# Handoff instructions for future LLM chats

When implementing this workstream:

1. Read this page and the master growth plan.
2. Read the latest Insights/Measurement status.
3. Inspect the current `Eirepolitic-data-pipeline` `main` branch before relying on examples here.
4. Read the relevant project's `project.yml`, renderer/adapter, content source, glossary/semantic rules, and QA.
5. Inspect actual rendered examples/contact sheets where available.
6. Recheck current Instagram recommendation/creator guidance from Meta.
7. Identify which hook archetypes can be supported directly by existing structured fields.
8. Do not invent political implications to create stronger copy.
9. For votes, inspect the exact proposition before writing the hook.
10. For party speech metrics, preserve the distinction between frequency and position/priority.
11. For polling, describe measurements/comparisons without predicting electoral outcomes.
12. Commission one family at a time; start with Bill Tracker unless current data indicates another stronger opportunity.
13. Prefer a cover-only treatment before changing the rest of a working carousel.
14. Render control/treatment side by side and run QA before asking for approval.
15. Record `experiment_id`, variant, renderer version, topic, and slide count before publication.
16. Do not change production publishing configuration or automatically publish test material without explicit approval.
17. After sufficient observations, update this page with results, promoted defaults, rejected variants, and any revised semantic rules.
