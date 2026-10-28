---
title: "EirePolitic Instagram Growth: Captions, Search, Hashtags, and Calls to Action"
description: "Detailed plan for low-effort optimisation of captions, Instagram search visibility, hashtags, alt text, and calls to action."
group: "Notes"
order: 65
---

# Captions, Search, Hashtags, and Calls to Action

## Status

**Planning state:** detailed investigation/experiment guide prepared.  
**Production changes:** none.  
**Priority:** medium, but very low cost and highly automatable.  
**Dependencies:** Discovery Hooks should inform the first caption line; Insights/Measurement should measure acquisition and utility outcomes.

## Objective

Make EirePolitic captions easier for people and Instagram's search/recommendation systems to understand, while using restrained calls to action and a small number of relevant hashtags.

The intended result is not “marketing copy.”

The intended result is:

```text
clear post topic
        ↓
plain-language context
        ↓
useful factual detail
        ↓
necessary source/caveat
        ↓
appropriate next action
        ↓
small set of relevant discovery labels
```

This should be generated systematically from the same structured data that produces the visual post.

---

# Current repository state already established

The production source of truth is `warrengleeson/Eirepolitic-data-pipeline`.

## Exact caption is already a first-class publication field

`publishing/models.py` stores the exact approved public caption in `PublicationRequest.caption`.

The publication request also stores:

- parsed `hashtags`;
- parsed `caption_mentions`;
- first comment where used;
- collaborators and media tags separately.

This is important because caption experiments can be tied to the existing publication ID/version and approval fingerprint rather than introduced as an informal/manual layer.

## Alt text already exists in the media model

`MediaAsset` already has:

```python
alt_text: str = ""
```

and the current Meta HTTP client passes non-empty alt text to image-container creation.

Therefore this workstream should audit whether project factories actually populate useful alt text, but it does **not** need a new publishing mechanism merely to support image alt text.

For carousel children, verify current execution behaviour in live `main` during implementation rather than assuming every project populates the field.

## Existing reusable caption template is limited

The inspected repository currently contains one shared caption template:

`instagram/caption_templates/member_profile.yml`

Its default hashtags are:

```text
#EirePolitic
#IrishPolitics
#DailEireann
#Oireachtas
#DataPolitics
```

The template explicitly states that the exact final caption must be stored in `PublicationRequest` before approval.

This is a good publication-control rule, but the hashtag/caption strategy is not yet a broad structured growth layer across content families.

## Bill Tracker production example

A completed Bill Tracker publication records the approved hashtag set:

```text
#EirePolitic
#Oireachtas
#DáilÉireann
#IrishPolitics
#Legislation
```

This is already within Instagram's current five-hashtag limit, but most tags are broad category labels.

The growth question is therefore not “how do we add more hashtags?” It is whether a **smaller/focused mix of branded, subject, and format-specific terms** improves relevance while the caption itself carries the descriptive search language.

---

# Current Instagram guidance relevant to this workstream

These platform observations were reviewed in October 2026 and must be rechecked before implementation.

## Captions matter for context and search

Instagram's August 2026 creator guidance emphasised that captions:

- add context;
- help spark conversation;
- tell search systems what the content is about;
- should use a strong opening line;
- should provide useful information people may want to save/share;
- can include a clear call to action;
- should include relevant descriptive keywords naturally.

Instagram also noted that only the first portion of a caption is visible before the user expands it, reinforcing the importance of the opening lines.

## Caption length is not a reach strategy by itself

Instagram leadership has stated that long captions do not materially increase reach simply because they are long.

Implication:

**Choose caption length based on usefulness and clarity, not the assumption that more text earns more distribution.**

## Hashtags are now deliberately constrained

Instagram moved to a maximum of **five hashtags per post/Reel** in late 2025 and recommended fewer, targeted tags rather than many generic tags.

Instagram has also repeatedly signalled that hashtags are not the major reach lever they once were.

Implication:

**Hashtags are classification/context metadata, not the growth strategy.**

## Search uses descriptive text

Instagram search historically matches user queries against signals including account/profile text, captions, hashtags, and places. Current 2026 creator guidance continues to emphasise descriptive keywords in captions.

Implication:

Use the terms ordinary people would use to describe the post, but do not keyword-stuff.

## Sharing is more valuable than comment bait

Instagram guidance/leadership has repeatedly highlighted sends/shares as an important signal, especially for reaching people who do not already follow the account.

Implication:

Where a CTA is justified, EirePolitic should usually prefer **utility actions** such as save/share/follow for a recurring information need rather than manufactured debate prompts.

---

# Strategic principles

## 1. Caption should describe the actual subject immediately

Do not start with internal series language when a plain-language subject is available.

Weak discovery opening:

```text
Bills of the Current Session — Enacted · Post 1
```

Stronger pattern:

```text
Three Irish laws passed this session — here's what each one changes.
```

The exact wording must remain supported by the content.

## 2. Caption and cover should agree

The first caption line should normally reinforce the cover hook rather than introduce a different framing.

Example:

Cover:

`What changed in the latest Irish poll?`

Caption first line:

`Here are the biggest percentage-point changes in the latest poll.`

This gives both the viewer and Instagram a consistent topic signal.

## 3. Use plain-language keywords naturally

Prefer phrases people may actually search for:

- Irish politics;
- Irish legislation;
- Oireachtas bills;
- Dáil Éireann;
- how a bill becomes law;
- Irish polling;
- TD / Teachta Dála;
- constituency;
- specific policy subject such as housing, health, transport, energy, AI regulation.

Do not force every keyword into every caption.

## 4. Formal terminology remains available where useful

Search-friendly/plain language does not mean removing technical terms.

Good pattern:

```text
The bill has completed Second Stage in Dáil Éireann.
Second Stage is the point where TDs debate the bill's general principles.
```

This helps both specialist and general-audience interpretation.

## 5. The caption should add value beyond the image

Avoid captions that merely transcribe the cover.

Use the caption for one or more of:

- plain-language summary;
- source context;
- exact parliamentary status;
- methodology;
- key caveat;
- where the viewer should look in the carousel;
- what recurring EirePolitic series they can expect.

## 6. Do not hide essential caveats in a first comment

The publisher supports a first comment, but critical context belongs in the caption or visual itself.

First comments may be useful for optional secondary detail, but should not contain the only copy of:

- vote-proposition caveats;
- polling source/date;
- methodology limitations;
- speech-frequency interpretation;
- corrections.

---

# Caption architecture

Create a small number of reusable caption structures rather than writing each post from scratch.

## C1 — concise informational caption

Best for:

- polling;
- simple charts;
- concise explainers;
- one-bill updates.

Structure:

```text
[Plain-language opening line]

[1-3 sentences of useful context]

[Source / methodology / necessary caveat]

[Optional CTA]

[2-5 targeted hashtags]
```

Target outcome:

A user who never expands beyond the first lines should still understand the topic.

---

## C2 — structured carousel caption

Best for:

- multi-bill Bill Tracker posts;
- roundups;
- complex political-data carousels.

Structure:

```text
[Hook/value statement]

This post covers:
• [plain-language subject 1]
• [plain-language subject 2]
• [plain-language subject 3]

[One short context/caveat paragraph]

[Source statement]

[Optional utility CTA]

[hashtags]
```

Formal titles can appear after the plain-language labels where useful, but do not make three long statutory titles the first information a casual viewer sees.

---

## C3 — measured-data caption

Best for:

- party speech breakdown;
- polling;
- representative activity/count data.

Structure:

```text
[What was measured + period]

[Key measured pattern]

[Methodology/semantic limitation]

[Source]

[CTA if useful]

[hashtags]
```

Example pattern for party speech data:

```text
What did [party] discuss most in [month]?

These figures count classified Dáil speeches by issue category.
They show frequency of discussion — not the party's position on an issue or how important the party considers it.
```

That distinction must remain prominent.

---

## C4 — process explainer caption

Best for evergreen educational posts.

Structure:

```text
[Question ordinary user might ask]

[Direct answer in one or two sentences]

[Short explanation / steps]

[Source or terminology note]

[Save/share CTA where genuinely useful]

[hashtags]
```

Example question:

`What does Second Stage actually mean in the Oireachtas?`

These posts are strong candidates for search, saves, and resurfacing.

---

# First-line rules

The first line should normally contain the primary subject phrase.

## Good properties

- understandable without prior EirePolitic knowledge;
- specific;
- descriptive;
- aligned with the first slide;
- natural, not robotic;
- short enough to remain visible before expansion where practical.

## Avoid

- `New post:`;
- `Post 2 is now live`;
- internal project names;
- unexplained parliamentary abbreviations;
- emoji chains before the actual topic;
- `BREAKING` unless the account has a defined and justified breaking-news role;
- generic engagement openers such as `Thoughts?`.

---

# Keyword taxonomy

The goal is not to “rank for everything.”

Maintain a controlled keyword vocabulary aligned with the actual EirePolitic data products.

## Layer 1 — account/domain keywords

Use naturally where relevant:

- Irish politics;
- politics in Ireland;
- Oireachtas;
- Dáil Éireann;
- Seanad Éireann;
- Irish legislation;
- TDs / Teachtaí Dála;
- Irish political data.

## Layer 2 — content-family keywords

### Bills

- Irish bill;
- legislation;
- bill stage;
- Second Stage;
- Committee Stage;
- enacted / became law;
- Dáil vote;
- Oireachtas vote.

### Polling

- Irish polling;
- opinion poll;
- party support;
- polling change;
- percentage-point change.

### Party speech data

- Dáil speeches;
- political issues;
- issue mentions;
- speech classification.

### Representative profiles

- TD;
- constituency;
- representative;
- Dáil member;
- party affiliation where factually relevant.

## Layer 3 — post-specific subject keywords

Examples:

- housing;
- health;
- transport;
- energy security;
- artificial intelligence regulation;
- pharmacy prescribing;
- defence;
- education.

These should come from approved topic classification/source data where possible.

## Keyword generation rule

Select:

```text
1 account/domain phrase
+ 1 content-family phrase
+ 1-2 post-specific subject phrases
```

Then write them naturally into the caption.

Do not append a keyword list.

---

# Hashtag strategy

## Principle

Use **2-5 relevant hashtags**, never more than the current platform limit.

Five should be a ceiling, not a target.

## Hashtag roles

A useful set can contain:

### 1. Branded

Usually:

`#EirePolitic`

Keep this for internal discoverability/identity even if it contributes little external reach.

### 2. Domain

Examples:

- `#IrishPolitics`;
- `#Oireachtas`;
- `#DáilÉireann`.

Use only those actually relevant to the post.

### 3. Content type

Examples:

- `#IrishLegislation`;
- `#IrishPolling`;
- `#PoliticalData`.

Do not assume an existing hashtag has meaningful traffic; the value can simply be accurate classification.

### 4. Subject

Where useful:

- `#Housing`;
- `#Health`;
- `#Energy`;
- another factual policy/topic label.

Subject tags may help distinguish otherwise broad Irish-politics content.

## Recommended default logic

Instead of one fixed five-tag list for every post:

```text
#EirePolitic
+ 1 broad Irish-politics/domain tag
+ 1 institutional/content-family tag
+ 0-2 subject-specific tags
```

Example Bill post:

```text
#EirePolitic #IrishPolitics #IrishLegislation #Oireachtas #Energy
```

Example polling post:

```text
#EirePolitic #IrishPolitics #IrishPolling
```

Example Dáil speech analysis:

```text
#EirePolitic #IrishPolitics #DáilÉireann #PoliticalData
```

These are strategy examples, not permanent approved sets.

## Avoid

- unrelated popular tags;
- generic viral tags such as `#fyp`;
- five broad tags with no post-specific context every time;
- variant spellings solely to consume all five slots;
- hashtags in the first comment as a workaround for limits;
- party/candidate hashtags where their use could imply campaigning unless the post is specifically and neutrally about that entity and the tag is genuinely useful.

---

# Hashtag registry

Create a small controlled registry rather than allowing every factory to invent tags independently.

Possible planning structure:

```yaml
hashtags:
  brand:
    - "#EirePolitic"
  domain:
    irish_politics: "#IrishPolitics"
    oireachtas: "#Oireachtas"
    dail: "#DáilÉireann"
  content:
    legislation: "#IrishLegislation"
    polling: "#IrishPolling"
    political_data: "#PoliticalData"
  subject:
    housing: "#Housing"
    health: "#Health"
    energy: "#Energy"
```

A caption builder would select only applicable tags and enforce the current maximum.

Do not implement a large hashtag-research system. Hashtags are too low-leverage to justify ongoing manual research.

---

# Alt-text strategy

Alt text should be treated primarily as **accessibility metadata**.

Do not keyword-stuff it.

## Current technical opportunity

The production model and Meta client already support image alt text.

Therefore audit whether generated assets receive meaningful values.

## Alt-text rules

Describe what is necessary to understand the image:

- chart subject;
- key axes/categories;
- headline;
- central values/pattern;
- relevant visual relationships.

Do not repeat every decorative element.

### Example — polling chart

```text
Bar chart showing party support in the latest Irish opinion poll, with percentage support values for each listed party.
```

If the exact values are important and manageable, include them.

### Example — Bill Tracker cover

```text
EirePolitic carousel cover introducing three laws passed during the current Oireachtas session and explaining that the post summarises what each changes.
```

## Carousel alt text

Each slide should have its own description where supported by the API/publisher path.

A future implementation chat must verify that child-container alt text is actually being sent from each asset, not merely present in the dataclass.

---

# Calls to action

A CTA is useful when it asks the viewer to perform an action that naturally follows from the content.

Do not put a CTA in every post by default.

## CTA categories

### CTA-SAVE — utility/reference

Use when the content has lasting reference value.

Examples:

- `Save this as a reference for the bill stages.`
- `Save this guide if you want to refer back to how Dáil divisions work.`

Best for:

- evergreen explainers;
- parliamentary-process guides;
- constituency/reference data.

### CTA-SHARE — useful to another person

Use when the post is self-contained and likely useful to someone else.

Examples:

- `Share this with someone following this bill.`
- `Send this to someone who wants a plain-language explanation of the process.`

Avoid generic `Share this!` with no reason.

### CTA-FOLLOW — recurring value

Use selectively on acquisition-oriented posts.

Examples:

- `Follow EirePolitic for recurring Irish legislation trackers and political-data explainers.`

This is stronger than simply `Follow for more` because it describes the future value.

### CTA-PROFILE — navigation

Use when another pinned post/series offers useful context.

Example:

- `The pinned “Start Here” guide explains how EirePolitic tracks legislation.`

### CTA-LINK — external resource

Use only when the profile link genuinely adds value.

Example:

- `Sources and methodology are linked from the profile.`

Do not push viewers off Instagram unnecessarily.

### CTA-COMMENT — genuine factual question

Use sparingly.

Safe examples:

- `Which parliamentary term would you like explained next?`
- `Is there a bill stage you would like a plain-language guide to?`

Avoid:

- `Do you agree with this law?` as a routine engagement tactic;
- `Which party is right?`;
- polarising prompts designed to farm arguments.

EirePolitic can invite information needs without turning neutral data posts into partisan debate prompts.

---

# CTA-selection rules

Choose CTA from content intent rather than randomly.

```text
Evergreen explainer      → save
Topical useful summary   → share
Strong acquisition post  → follow
Navigation post          → profile
External resource        → link
Research/input need      → factual comment question
No clear action          → no CTA
```

One CTA is usually enough.

Do not stack:

`Like, comment, share, save and follow!`

That creates low-value promotional clutter.

---

# Caption source/caveat policy

EirePolitic's credibility is a growth asset.

Captions should provide enough sourcing context to support trust without becoming a bibliography.

## Bills

Include where relevant:

- full/formal bill name or unambiguous identifier;
- Oireachtas stage/status;
- source basis such as Houses of the Oireachtas;
- vote proposition caveat where a displayed division is not a vote on the bill as a whole.

## Polling

Include:

- polling organisation/source;
- fieldwork/publication date as available;
- comparison basis;
- methodology link/reference where practical.

Do not imply polling is an election forecast.

## Party speech analysis

Include:

- period;
- data source;
- classification basis;
- explicit frequency-not-position caveat.

## Corrections

If a material factual correction is required after publication, use a transparent correction process. Do not silently manipulate caption wording to obscure the original error.

A separate corrections standard may be appropriate later.

---

# Mentions and tagging within captions

Mentions are not a substitute for distribution strategy.

Use them when they improve source/context clarity or are operationally required.

Potentially appropriate:

- a polling organisation whose data is being shown;
- a public institution/source account;
- a collaboration partner.

Do not mention political actors merely to attract their followers.

Do not mass-tag parties, TDs, journalists, or organisations unrelated to the specific post.

The detailed collaboration/tagging strategy belongs in Workstream 08.

---

# First-comment strategy

The production publisher supports a first comment.

Use only where it solves a real content problem.

Possible uses:

- secondary source/reference information;
- a non-essential supplementary link reference where the app experience makes it useful;
- additional methodology detail.

Do not use it for:

- hiding hashtags to bypass platform limits;
- essential caveats;
- core caption text;
- engagement bait;
- unapproved post-publication claims.

Default should remain **no first comment** unless the series specifically benefits from one.

---

# Search-intent content opportunities

Search optimisation is stronger when the post itself answers something people may actually search for.

The captions workstream should therefore feed useful query patterns back into the Topical/Evergreen workstream.

Candidate evergreen queries:

- `How does a bill become law in Ireland?`
- `What is Second Stage in the Dáil?`
- `What is a Dáil division?`
- `How many TDs are in the Dáil?`
- `Who is my TD?` where EirePolitic has suitable constituency data;
- `What does enacted mean?`
- `How do Oireachtas committees work?`

Do not manufacture search content solely around high-volume terms unrelated to EirePolitic's data/source strengths.

---

# Proposed caption-generation architecture

The long-term goal should be deterministic, content-family-aware caption construction.

## Suggested inputs

```yaml
caption_input:
  content_family: bill_tracker
  hook_text: "3 laws passed this session — what each one changes"
  plain_language_subjects:
    - "Energy security"
    - "Settlement goods imports"
    - "AI regulation"
  source_label: "Houses of the Oireachtas"
  caveat_id: null
  cta_id: follow_legislation
  keyword_ids:
    - irish_politics
    - irish_legislation
    - oireachtas
  subject_ids:
    - energy
```

## Suggested output metadata

```yaml
caption:
  template_id: bill_tracker_roundup_v2
  template_version: 2
  experiment_id: CS-001
  variant: concise
  char_count: 642
  keyword_ids:
    - irish_politics
    - irish_legislation
  hashtag_ids:
    - eirepolitic
    - irish_politics
    - irish_legislation
    - oireachtas
    - energy
  cta_id: follow_legislation
```

The exact final public caption must still be frozen in `PublicationRequest.caption` before approval.

---

# Caption QA

Future caption builders should validate at minimum:

- caption not empty;
- no internal review/debug wording;
- hashtag count <= current Instagram limit;
- no duplicate hashtags;
- all selected hashtags relevant to the post metadata;
- required source label present;
- required project-specific caveat present;
- no unresolved placeholders;
- no unapproved mentions;
- no URL assumption where the link will not be usable;
- no misleading vote semantics;
- no speech-frequency-to-position inference;
- no poll-to-election prediction language;
- no unsupported superlative or sensational claim.

Optional stylistic QA:

- first line within a preferred length range;
- avoid more than one CTA;
- avoid excessive emoji;
- line breaks for readability;
- avoid unnecessary duplication of cover text.

---

# Experiment programme

## CS-001 — short vs contextual caption

### Question

Does a concise caption perform as well as or better than a longer contextual caption for acquisition-oriented carousels?

### Control

Existing/longer factual caption.

### Treatment

Short structure:

- hook;
- 2-3 lines of context;
- source/caveat;
- one CTA;
- targeted hashtags.

### Primary metrics

- follows per 1,000 reached;
- shares per 1,000 reached;
- saves per 1,000 reached.

### Secondary

- profile visits;
- comments;
- reach.

Do not expect caption length itself to drive reach; test whether concise utility improves user action.

---

## CS-002 — descriptive first line vs series title

### Control

Series-first opening such as:

`Bills of the Current Session — Enacted · Post 1`

### Treatment

Plain-language descriptive opening.

### Hypothesis

A descriptive first line improves comprehension/search relevance and supports the acquisition cover.

Keep the rest of the caption materially similar.

---

## CS-003 — CTA vs no CTA

Test one utility CTA against no CTA.

Recommended first subject:

- save CTA on an evergreen explainer;
- or follow CTA on a strong acquisition post.

Do not combine several CTAs.

Primary metric should match the CTA:

- save rate for save CTA;
- follow rate for follow CTA.

---

## CS-004 — generic vs topic-specific hashtag set

### Control

Broad fixed set such as existing defaults.

### Treatment

Branded + domain + content + subject-specific selection.

### Metrics

- non-follower reach;
- search-originated discovery if available;
- follows per 1,000 reached.

### Expected priority

Low-medium.

Do not spend many publications on this test if early results show negligible effect. Hashtags are not expected to be a major growth driver.

---

## CS-005 — source/caveat placement

Question:

Can necessary methodology/caveat text remain prominent while keeping the first two lines acquisition-friendly?

Compare:

- caveat/source in first paragraph;
- useful opening first, caveat/source immediately afterward.

The goal is readability without hiding limitations.

Never test removal of a required caveat.

---

## CS-006 — save vs share CTA by content type

Do not ask viewers to save/share indiscriminately.

Test:

- save CTA on evergreen reference material;
- share CTA on topical plain-language summaries.

Measure the requested action per 1,000 reached.

---

# Experiment metadata

Each tested publication should record:

```text
experiment_id
variant
caption_template_id
caption_template_version
caption_char_count
caption_word_count
opening_style
keyword_set_id
hashtag_set_id
hashtag_count
cta_id
cta_type
first_comment_used
alt_text_template_version
```

Join these dimensions to Insights using the existing publication ID/version.

Do not reconstruct variants later by parsing caption text if structured metadata can be recorded before publication.

---

# Implementation sequence

## Stage 1 — caption inventory

1. Read this document and current project docs.
2. Inspect all current caption-generation paths across active Instagram factories.
3. Export or catalogue at least the recent representative captions for each content family.
4. Record:
   - first line;
   - length;
   - source/caveat placement;
   - CTA;
   - hashtags;
   - mentions;
   - first-comment use;
   - alt-text population.
5. Identify duplication/inconsistency.

This is read-only.

## Stage 2 — controlled taxonomy

6. Define shared keyword registry.
7. Define shared hashtag registry.
8. Define CTA registry.
9. Define required caveats per content family.
10. Define 3-4 initial caption templates.
11. Confirm current Instagram hashtag limit/guidance before coding.

## Stage 3 — commissioning

12. Apply the new builder/template to one content family only.
13. **Recommended first family:** Bill Tracker, aligned with the Discovery Hooks experiment.
14. Render/preview exact control and treatment captions against the same approved content.
15. Run semantic/hashtag/placeholder QA.
16. Ask for approval of the template behaviour, not every future routine caption.

## Stage 4 — experiment integration

17. Record caption experiment metadata with the publication.
18. Keep exact final caption frozen in `PublicationRequest` before approval.
19. Publish through the existing publisher.
20. Measure at 72h/7d/30d where appropriate.
21. Repeat before standardising.

## Stage 5 — scale proven rules

22. Add shared caption utilities/registries only after one family proves the design.
23. Migrate additional families incrementally.
24. Preserve project-specific caveats.
25. Add regression tests for hashtag cap, exact caption freezing, alt text, and source/caveat requirements.

---

# Suggested repository destination

Do not create until implementation is approved.

A possible structure is:

```text
instagram/
├── caption_templates/
│   ├── registry.yml
│   ├── bill_tracker.yml
│   ├── polling.yml
│   ├── party_speech.yml
│   └── evergreen_explainer.yml
└── captions/
    ├── builder.py
    ├── hashtags.py
    ├── keywords.py
    ├── ctas.py
    └── qa.py
```

The final structure should follow the live project's conventions. Do not refactor existing factories merely to match this sketch.

---

# Workload / cost assessment

| Activity | Expected upside | Setup effort | Recurring manual effort | Cost | Automation potential |
|---|---|---|---|---|---|
| Descriptive first-line rules | Medium-high | Low | None | €0 | Very high |
| Content-family caption templates | Medium-high | Low-medium | Near-zero | €0 | Very high |
| Keyword taxonomy | Medium | Low | Very low | €0 | Very high |
| Targeted hashtag registry | Low-medium | Very low | Near-zero | €0 | Very high |
| CTA registry/rules | Medium | Very low | None | €0 | Very high |
| Alt-text templates | Medium accessibility value; uncertain growth lift | Low-medium | None | €0 | Very high |
| Manual hashtag research per post | Low expected | High recurring | High | €0 | Low |
| Long bespoke captions | Variable | Low setup | High recurring | €0 | Low |

The disproportionate opportunity is **standardisation**, not spending more time writing captions.

---

# Risks and safeguards

## Keyword stuffing

Do not turn captions into unnatural repetitions of `Irish politics`, `Dáil`, `Oireachtas`, etc.

One clear use is enough when context establishes the rest.

## Hashtag overvaluation

Do not attribute growth to hashtags without evidence. Current platform guidance treats them as a secondary relevance mechanism.

## Misleading search language

Do not use a popular keyword if the post only tangentially relates to it.

## CTA engagement bait

Do not ask inflammatory political questions merely to create comments.

## Accessibility misuse

Alt text is not a hidden SEO field. Write it for users who need image descriptions.

## Source/caveat burial

Acquisition-friendly opening lines are acceptable; hiding a material limitation is not.

## Caption-template rigidity

A single template may not fit every data product. Maintain a small family of templates tied to content semantics.

---

# Information that may require the user

No major user input is required to continue planning.

During implementation, the user should only need to approve material choices such as:

- the preferred initial caption voice/structure if two valid templates differ materially;
- whether a recurring CTA feels too promotional for EirePolitic;
- promotion of tested caption rules to production defaults.

The future LLM should not ask the user to manually research hashtags, write captions, or select keywords for routine posts.

---

# Handoff instructions for future LLM chats

When implementing this workstream:

1. Read this page and the master growth plan.
2. Read current Discovery Hooks and Insights workstream status.
3. Inspect current `Eirepolitic-data-pipeline` `main` before relying on examples here.
4. Catalogue current caption-generation paths and representative recent captions.
5. Inspect `PublicationRequest`, `MediaAsset`, publisher, and Meta client to confirm current caption/alt-text behaviour.
6. Recheck current Instagram hashtag limits and creator guidance from Meta/Instagram.
7. Do not assume hashtag advice from older social-media articles remains current.
8. Build a small controlled keyword/hashtag/CTA registry rather than a large marketing database.
9. Use plain-language subject terms naturally in the first lines.
10. Preserve formal terminology, source context, and project-specific caveats.
11. For Bills, inspect the exact vote proposition before summarising a division.
12. For party speech data, never translate frequency into position/priority.
13. For polling, describe measured polling results without election prediction.
14. Treat alt text as accessibility-first.
15. Prefer one CTA or none.
16. Do not hide essential information in the first comment.
17. Record caption experiment metadata before publication.
18. Keep the final exact caption frozen inside the existing publication approval process.
19. Make no production publishing/infrastructure changes without explicit approval.
20. Update this page with test results and promoted/rejected rules.

---

# Completion criteria

This workstream is mature when:

- every active content family has a clear caption structure;
- captions lead with understandable subject language rather than internal series terminology;
- keyword use is natural and systematic;
- hashtags are limited, relevant, and generated from a controlled registry;
- project-specific caveats are automatically preserved;
- calls to action are selected according to content utility rather than added mechanically;
- meaningful alt text is generated consistently;
- caption variants can be measured through the Insights layer;
- routine caption production requires essentially no manual work;
- no growth tactic weakens EirePolitic's factual/neutral editorial standard.

The target end state is **captions that quietly improve comprehension, search relevance, accessibility, and useful user actions while remaining operationally invisible to the person running EirePolitic**.
