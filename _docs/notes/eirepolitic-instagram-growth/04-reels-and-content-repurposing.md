---
title: "EirePolitic Instagram Growth: Reels and Content Repurposing"
description: "Detailed plan for testing low-manual-work short-form video generated from existing structured EirePolitic content."
group: "Notes"
order: 64
---

# Reels and Content Repurposing

## Status

**Planning state:** detailed investigation/implementation guide prepared.  
**Production changes:** none.  
**Priority:** high, but below Insights/Measurement and first-slide/carousel packaging.  
**Primary dependency:** a working measurement layer is strongly preferred before scaling Reels.  
**Current pipeline capability:** static images/carousels only; no Reel/video rendering or publishing support currently exists in the inspected repository state.

## Objective

Use EirePolitic's existing structured political data and visual assets to create short, vertical, discovery-oriented Instagram Reels **without creating a recurring filming/editing workload**.

The desired operating model is:

```text
existing structured political data
        ↓
existing approved factual summary/chart logic
        ↓
9:16 Reel frame templates
        ↓
deterministic video assembly
        ↓
review/QA during commissioning
        ↓
normal approval/scheduling path once proven
        ↓
Instagram Reel
        ↓
Insights comparison against carousel/static baseline
```

The aim is not to become a personality-led video account. Reels are a **distribution format for information EirePolitic already produces**.

---

# Current repository state already established

The production source of truth is `warrengleeson/Eirepolitic-data-pipeline`.

## Existing publisher supports images and carousels only

`publishing/models.py` currently defines:

```python
post_type: Literal["image", "carousel"]
```

There is no `reel`/`video` publication type.

`publishing/meta_http_client.py` currently provides:

- image container creation;
- carousel parent creation;
- container-status checks;
- container publishing;
- first comments.

There is no Reel/video-container method.

`publishing/publisher.py` assumes every approved media asset is an image and calls `create_image_container()` for each asset.

Therefore Reel support is **not** a configuration toggle. It is a real extension of the publication model, asset model, validation, Meta provider, tests, and infrastructure packaging.

## Existing asset system is image-specific

`publishing/s3_assets.py` currently finalises approved assets to JPEG and records image dimensions/mime types.

The publication runtime generates short-lived S3 pre-signed URLs for Meta to fetch approved assets.

This is useful because Meta's Reel publishing API also requires a remotely fetchable video URL; the existing pre-signed-asset pattern can potentially be extended to video without making the bucket public.

However, the current approved-asset finaliser is image-specific and must not simply be reused blindly for MP4.

## Existing renderer stack is static

The inspected repository includes:

- Pillow;
- Matplotlib;
- CairoSVG;
- Playwright;
- existing static chart/card/layout renderers.

No existing dependency or code was found for:

- FFmpeg;
- MoviePy;
- MP4 generation;
- frame animation;
- video encoding;
- Reel rendering.

This means the video renderer should be introduced as an isolated capability rather than mixed into established static rendering logic.

## Existing visual assets are highly reusable

The repository already contains reusable visual/data elements suitable for Reel frames:

- Bill Tracker plain-language summaries and vote/result data;
- party speech issue rankings and comparisons;
- polling percentages, changes, and trend charts;
- shared EirePolitic palette/layout primitives;
- logos and chart renderers;
- structured publication captions and provenance.

The likely challenge is format conversion, not content creation.

---

# Current Instagram / Meta capability context

These facts were reviewed in October 2026 and must be rechecked before implementation.

## Server-side Reel publishing is supported

Meta's current Instagram API documentation supports Reel publishing from a server using the normal media-container flow.

The documented flow is:

```text
POST /{ig-user-id}/media
  media_type=REELS
  video_url=<remotely fetchable URL>
  caption=<caption>
  share_to_feed=<true|false>
        ↓
GET container status until FINISHED
        ↓
POST /{ig-user-id}/media_publish
        ↓
permanent Instagram media ID
```

The current Meta documentation specifies, among other limits:

- MOV or MP4 container;
- H.264 or HEVC video;
- AAC audio where audio is used;
- 23-60 FPS;
- recommended 9:16 aspect ratio;
- maximum horizontal size 1920 px;
- duration at least 3 seconds and up to 15 minutes;
- maximum file size 1 GB.

EirePolitic should use a much narrower internal specification than Meta's maximums.

## Recommended EirePolitic Reel technical profile

Initial target:

```text
container: MP4
video codec: H.264
canvas: 1080 x 1920
aspect ratio: 9:16
frame rate: 30 FPS
video length: approximately 8-20 seconds for first experiments
video bitrate: conservative web/mobile bitrate below Meta limit
audio: none or silent AAC during first technical tests
```

Do not assume this exact profile forever; validate against Meta at commissioning time.

## Trial Reels

Meta's Trial Reels feature is designed to show a Reel to non-followers first. Meta made Trial Reels broadly available in 2025.

Meta describes a workflow where:

- a creator enables `Trial` in the Instagram app;
- the Reel is initially shown to non-followers;
- initial engagement metrics become visible after roughly 24 hours;
- the creator can later share it to followers;
- Instagram can optionally auto-share a trial to followers if it performs well based on views during the first 72 hours.

### Important automation limitation

The server-side Reel publishing documentation inspected in October 2026 exposes parameters such as `media_type=REELS`, `video_url`, caption, and `share_to_feed`, but **no verified Trial-Reel publishing parameter was identified**.

Therefore:

**Treat Trial Reels as a manual app-based experiment unless a live API capability audit proves a supported programmatic method exists.**

Do not build automation around an undocumented parameter.

### Implication for EirePolitic

Trial Reels are useful for early format discovery, but they conflict somewhat with the low-manual-work objective.

Recommended use:

- only during early commissioning;
- perhaps 1-2 trial posts per format;
- manually upload the already-generated MP4 and toggle Trial;
- record the resulting Instagram media identity and experiment metadata;
- once a format is proven, move it to ordinary API publishing for automation.

Do not make manual Trial Reel posting a permanent operational requirement.

---

# Strategic hypothesis

Reels are worth testing because they provide a distinct discovery surface and can expose EirePolitic to non-followers.

But the correct hypothesis is **not**:

> “Reels always grow faster than carousels.”

The hypothesis is:

> “Some EirePolitic information can be repackaged into a short vertical sequence at near-zero recurring manual cost, and that format may produce additional non-follower reach and follower acquisition beyond the carousel baseline.”

If automated Reels do not produce enough incremental acquisition to justify the added renderer/publisher complexity, the programme should stop or narrow them.

---

# Content principles for EirePolitic Reels

## 1. The Reel must work with sound off

All essential information must be visible as text/graphics.

Do not require:

- voiceover;
- trending audio;
- dialogue;
- music lyrics;
- audio cues to understand the result.

This makes the format accessible and highly automatable.

## 2. Motion should clarify, not decorate

Good uses of motion:

- reveal one fact at a time;
- animate a bar from previous to current polling value;
- move through legislative stages;
- highlight a vote result;
- transition between three bills/topics;
- draw a trend line progressively.

Poor uses:

- constant zooming;
- random spinning text;
- flashy transitions unrelated to meaning;
- motion added merely because it is a Reel.

## 3. One Reel = one clear promise

A short Reel should normally explain one idea.

Examples:

- `3 laws passed this session — what they change`;
- `What changed in the latest Irish poll?`;
- `What did this party discuss most this month?`;
- `How can a bill pass without a recorded division?`.

Do not squeeze an entire nine-slide carousel into 15 seconds.

## 4. Preserve the same semantic safeguards as carousels

Reel brevity does not permit:

- incorrect vote interpretation;
- inferred party positions from speech counts;
- election predictions from polling;
- unsupported policy-effect claims;
- partisan framing.

Where the Reel cannot communicate a necessary caveat clearly, the format is unsuitable for that item.

---

# Recommended first Reel formats

Start with **three constrained formats**. Do not create a general-purpose video engine before these prove useful.

## R1 — Poll movement Reel

### Why first

Polling already has:

- compact numerical data;
- existing chart logic;
- obvious before/after comparison;
- naturally animated values;
- low need for long explanatory text.

### Suggested sequence

Approximate 10-15 seconds:

```text
0-2s
WHAT CHANGED IN THE LATEST IRISH POLL?

2-8s
show party movements one by one
+/- percentage-point changes

8-12s
current percentages / largest movements

12-15s
source + fieldwork/date + EirePolitic mark
```

### Required safeguards

- state source/date;
- use `percentage points`, not percent, where mathematically appropriate;
- do not say who is “winning the election”;
- do not infer future electoral outcome.

### Automation potential

Very high.

---

## R2 — Bill “What it changes” Reel

### Suggested sequence

Approximate 12-20 seconds:

```text
0-2s
WHAT DOES THIS BILL/LAW CHANGE?

2-6s
plain-language subject

6-12s
2-3 concise changes/effects supported by source material

12-16s
current Oireachtas/legal stage + key date

16-20s
formal bill title / source / EirePolitic
```

### Best candidates

Use bills where:

- the practical effect is understandable;
- the structured `what`/`effect` fields are already strong;
- necessary caveats fit in the format.

Do not force procedurally complex bills into this format merely because they are available.

### Automation potential

High once a safe summary-selection rule is commissioned.

---

## R3 — Political-data ranking Reel

Candidate source: party speech breakdown.

### Suggested sequence

Approximate 10-15 seconds:

```text
0-2s
WHAT DID [PARTY] DISCUSS MOST IN [MONTH]?

2-9s
top 3 classified issue categories reveal/rank

9-12s
comparison marker if useful

12-15s
methodology qualifier + EirePolitic
```

### Required qualifier

Wording equivalent to:

`Based on classified Dáil speeches. Frequency does not indicate the party's position or priority.`

If that qualifier cannot remain readable, reject the format rather than omit it.

### Automation potential

Very high.

---

# Formats to defer

Do not begin with these.

## Talking-head explainers

Potentially effective but require substantial recurring personal time and change the character of the account.

## Daily news commentary

High manual research burden and greater neutrality/error risk.

## Trend-audio participation

Requires continuous trend monitoring, licensing/availability checks, and manual creative work.

## AI avatars / synthetic presenters

Unnecessary for the current objective and could reduce trust in a factual political-information project.

## Long narrated explainers

More production complexity than needed to test whether Reels add discovery value.

## Automatically generated political narration using open-ended LLM copy

Too much semantic risk before the deterministic visual formats are proven.

---

# Video-generation architecture

## Recommended initial approach: static frame renderer + FFmpeg

Reuse existing EirePolitic visual/data logic to render a sequence of 9:16 PNG/JPEG frames, then assemble them into an MP4.

Conceptually:

```text
existing project data
      ↓
Reel storyboard adapter
      ↓
1080x1920 deterministic frames
      ↓
FFmpeg
      ↓
H.264 MP4
```

### Why FFmpeg is preferred initially

- mature and deterministic;
- handles MP4/H.264 reliably;
- supports frame timing, fades, pans, overlays, and audio if later required;
- avoids implementing video encoding in Python;
- works well with image sequences produced by the current renderer stack;
- separates “what is shown” from “how the frames become a video.”

### Why not MoviePy first

MoviePy can simplify Python orchestration but adds another application dependency and still relies on video-encoding tooling underneath.

It may be appropriate later, but it is not necessary for the first deterministic templates.

### Why not browser-screen-recording first

The repo already uses browser/static layout tools, but recording browser animation introduces timing/rendering variability and greater runtime complexity.

Use explicit frames unless a later format genuinely requires complex web animation.

---

# Rendering layers

Keep three layers distinct.

## 1. Storyboard/data adapter

Outputs structured scenes, for example:

```yaml
reel_id: poll_change_v1
scenes:
  - type: hook
    duration_ms: 1800
    headline: "What changed in the latest Irish poll?"
  - type: movement_chart
    duration_ms: 6500
    data_ref: latest_poll_changes
  - type: current_snapshot
    duration_ms: 3500
    data_ref: latest_support
  - type: source
    duration_ms: 2200
    source: "..."
```

No raw animation code should be mixed into political data interpretation.

## 2. Frame renderer

Turns approved structured scenes into 1080x1920 images.

Reuse:

- palette;
- typography;
- charts;
- logos;
- attribution/source styling;
- EirePolitic identity.

## 3. Video assembler

Responsible only for:

- timing;
- transitions;
- frame/video encoding;
- optional silent/house audio track;
- output validation.

It should not decide political wording or data values.

---

# Motion model

Keep the first implementation extremely small.

Allowed initial motion primitives:

- hard cut;
- fade/crossfade;
- simple vertical/horizontal reveal;
- chart/bar growth;
- numeric count/change animation;
- progressive line drawing.

Do not build a general animation framework.

A format that cannot be expressed with these primitives should wait until simpler Reels prove worthwhile.

---

# Audio strategy

## Phase 1 — no dependency on music

The first Reels should be understandable without audio.

Technical commissioning should test whether Meta accepts the chosen MP4 profile without an audio stream. If the actual publishing path requires or behaves more reliably with audio, encode a silent AAC track.

Do not infer this from old examples; test the current API.

## Phase 2 — optional house audio only if useful

If performance evidence suggests sound materially helps:

- use audio EirePolitic owns or has explicit reusable rights to;
- store licence/provenance information;
- use one or a small number of reusable tracks;
- keep volume/subtlety appropriate for information content.

## Do not build around trending commercial audio

Reasons:

- rights/availability can differ by account and region;
- automated API use may not expose the same music catalogue as the app;
- manual selection creates recurring workload;
- trends expire quickly;
- the strategy should remain durable.

---

# Cover / thumbnail strategy

A Reel can still fail at discovery/profile conversion if its cover is unclear.

Each Reel template should generate a deterministic cover frame using the same hook rules as the Discovery Hooks workstream.

The cover should:

- remain readable as a profile-grid thumbnail;
- make sense without motion;
- match the Reel's actual promise;
- use the same experiment/hook metadata as the Reel.

Before implementation, recheck the current Instagram API/app support for programmatic cover selection because available parameters may change.

Do not allow an arbitrary mid-animation frame to become the permanent profile thumbnail if it makes the grid incoherent.

---

# Safe-area design

9:16 Reel frames are partially covered by Instagram interface elements.

During commissioning:

- inspect the current app UI on representative devices;
- define a reusable safe-area overlay;
- keep primary headline/data away from top/bottom/right-side controls;
- render QA previews showing the safe-area mask;
- avoid putting source/caveat text in areas hidden by caption/control overlays.

Do not hard-code safe zones from an old internet template without checking the current UI.

---

# Asset/publication model extension

Do not implement until Reel formats prove worthwhile and the user approves production integration.

## Publication model

Likely change:

```python
post_type: Literal["image", "carousel", "reel"]
```

Potential Reel-specific options:

```text
share_to_feed
cover/thumbnail selection if current API supports it
```

Do not add speculative options that Meta does not expose.

## Video asset model

The current `MediaAsset` shape is image-oriented because it requires width/height and the current finalisation pipeline converts everything to JPEG.

A future implementation should decide between:

### Option A — generalise `MediaAsset`

Add media-kind/duration/codec fields and support both image/video finalisers.

### Option B — introduce `VideoAsset`

Keep image contracts unchanged and add an explicit video asset type.

**Recommended initial preference:** explicit video handling or a carefully backwards-compatible generalisation; do not weaken the established image validation path.

This is an architecture decision requiring review during implementation.

---

# Video asset storage

Reuse the current immutable/content-addressed S3 principle.

Candidate key pattern:

```text
instagram/approved/<project>/<period>/<asset-package>/video/<hash>.mp4
```

Requirements:

- private bucket remains private;
- content-addressed immutable key;
- SHA-256 recorded;
- MIME type `video/mp4`;
- file size recorded;
- duration/frame dimensions/frame rate recorded;
- generated pre-signed URL long enough for Meta to fetch/process the video;
- URL expiry tested against actual Meta processing latency.

The current image URL lifetime is 900 seconds. Do not assume 15 minutes is sufficient for Reel ingestion without testing.

---

# Publisher extension plan

The normal publisher should eventually support Reel execution while preserving existing idempotency/reconciliation behaviour.

## Suggested provider operation

Conceptually:

```python
create_reel_container(
    video_url=...,
    caption=...,
    share_to_feed=...,
)
```

The operation should call the current Meta Reel container endpoint with `media_type=REELS`.

## Execution behaviour

Reuse existing principles:

1. create container once;
2. persist provider/container ID before next side effect;
3. poll container status;
4. publish only when finished;
5. persist permanent media ID;
6. treat uncertain publish outcomes as reconciliation problems, never blind retries;
7. first comment remains a post-publish secondary action.

Reel support should not create a parallel unsafe publisher.

## Processing-time difference

Video containers can take longer to process than static images.

The current runtime assumes a container is publishable at the point it checks status.

A Reel implementation must explicitly handle longer `IN_PROGRESS`/processing states safely rather than treating expected video processing as an operator failure.

Possible implementations:

- bounded polling within Lambda if comfortably inside runtime limits;
- delayed retry/reconciliation using the existing execution record;
- a separate continuation mechanism if processing proves too slow.

Choose only after live canary testing.

---

# Trial Reel pilot

Because no verified Trial-Reel API parameter was found, the initial Trial pilot should remain intentionally manual and small.

## Pilot procedure

1. Generate an approved MP4 through the commissioning workflow.
2. Save experiment metadata before upload.
3. Transfer/open the MP4 on the device running Instagram.
4. Create Reel in the Instagram app.
5. Enable `Trial` if the account currently exposes the option.
6. Use the approved caption/cover.
7. Publish the Trial Reel.
8. Record the resulting Instagram media/permalink manually in the experiment ledger.
9. Capture 24-hour Trial metrics from Instagram.
10. Do not automatically share to followers unless that behaviour was explicitly chosen for the experiment.
11. Record 72-hour outcome and whether it was shared more broadly.

### Workload target

The pilot should require minutes per Reel, not daily editing.

If Trial Reel handling becomes an ongoing manual burden, stop using Trials and move proven formats to ordinary automated Reel publishing.

---

# Experiment programme

## RR-001 — Polling carousel vs automated Reel

### Hypothesis

A short animated polling-change Reel produces more non-follower discovery per publication than the equivalent polling carousel without materially reducing follow conversion.

### Control

Existing polling carousel.

### Treatment

R1 Poll Movement Reel using the same polling dataset and source period.

### Primary metrics

- non-follower reach;
- follows per 1,000 reached;
- shares per 1,000 reached.

### Reel diagnostics

- average watch time;
- average watch time / Reel duration;
- early skip rate where available;
- completion/retention where available.

### Important limitation

Do not publish an identical carousel and Reel simultaneously solely to manufacture a clean A/B test if doing so would annoy followers or distort distribution.

Use repeated comparable observations and record timing/topic differences.

---

## RR-002 — Trial Reel discovery test

### Hypothesis

A structured EirePolitic Reel can generate meaningful non-follower engagement before being shown broadly to followers.

### Method

Use one approved R1 or R2 MP4 manually as a Trial Reel.

### Metrics

At approximately 24/72 hours:

- views;
- shares;
- likes/comments as diagnostics;
- Trial comparison metrics shown by Instagram;
- follower/profile actions where available.

### Decision

The question is not whether Instagram labels it “good.” The question is whether the format produces enough discovery signal to justify automated Reel publishing development.

---

## RR-003 — Reel length

After one format works, test a constrained duration difference.

Example:

- 9-12 seconds;
- 15-20 seconds.

Keep information content comparable.

Primary outcome:

- watch-time ratio;
- shares;
- follow acquisition.

Do not optimise for maximum retention by deleting necessary context.

---

## RR-004 — motion vs near-static Reel

Question:

Does simple data motion add enough value to justify animation complexity?

Control-like treatment:

- sequence of static frames/cuts.

Motion treatment:

- animated bars/line/reveal.

If static/cut-based Reels perform similarly, choose them because they are simpler and more reliable.

---

## RR-005 — Reel vs carousel by content family

Run only after the Reel system is stable.

Compare relative format lift for:

- polling;
- Bills;
- party-data summaries.

The likely outcome may differ by data type. Do not force every EirePolitic series into Reels.

---

# Measurement model

The Insights workstream should label Reel publications with:

```text
content_family
format=reel
reel_template_id
reel_template_version
reel_duration_ms
scene_count
motion_level
has_audio
trial_reel
share_to_feed
experiment_id
variant
source_publication_id / source_data_period
```

Where a Reel is a repurposing of an existing carousel dataset, link both to the same source period/content entity without pretending they are the same publication.

## Primary success threshold

Do not choose an arbitrary percentage before baseline data exists.

A Reel format should be promoted when repeated observations indicate:

- materially higher non-follower reach than the comparable static/carousel baseline;
- acceptable or improved follows per 1,000 reached;
- useful share rate;
- manageable watch/skip metrics;
- near-zero recurring manual creation effort.

A Reel that generates many views but few followers/profile actions may be a weak acquisition format for EirePolitic.

---

# Repurposing beyond Instagram Reels

The video renderer should not be Instagram-specific at the storyboard level.

If a vertical MP4 is generated deterministically, it may later be reusable for:

- Facebook Reels;
- YouTube Shorts;
- TikTok, if EirePolitic chooses to operate there;
- Threads/video posts where appropriate;
- embedded website explainers.

However, do not open all channels at once.

The Cross-Platform workstream should decide whether each additional platform justifies its maintenance/moderation burden.

## Repurposing principle

Generate one canonical vertical video asset, then adapt only platform-specific metadata where possible.

Do not maintain separate manual edits for every platform.

---

# Proposed repository structure

Do not create until implementation is approved.

Candidate structure:

```text
instagram/
└── reels/
    ├── README.md
    ├── models.py
    ├── storyboard.py
    ├── frame_renderer.py
    ├── video_assembler.py
    ├── qa.py
    └── templates/
        ├── poll_change_v1.yml
        ├── bill_effect_v1.yml
        └── issue_ranking_v1.yml
```

Alternative placement under the existing project/factory architecture may be preferable after inspecting current `main` at implementation time.

Do not create a parallel content-source system. Reel storyboards should consume the same canonical project outputs as the static formats.

---

# Technical QA

Every Reel must pass deterministic checks before approval.

## File QA

Validate using FFprobe or equivalent:

- MP4 container;
- H.264 codec;
- expected resolution;
- expected frame rate;
- duration within internal and Meta limits;
- file size;
- no corrupt stream;
- audio properties if audio exists.

## Visual QA

Generate:

- first-frame/cover preview;
- contact sheet of representative time points;
- safe-area overlay preview;
- final-frame/source preview.

Check:

- no clipping;
- readable text;
- no excessively fast scene;
- charts remain interpretable;
- required caveat/source visible long enough to read.

## Semantic QA

Reuse the same semantic checks as the originating project.

The conversion to video must not weaken:

- source lineage;
- vote proposition meaning;
- bill status;
- party-speech interpretation;
- polling comparison basis.

---

# Performance/cost considerations

## Rendering cost

FFmpeg video generation is computationally heavier than JPEG rendering but should remain inexpensive at EirePolitic's expected publication volume.

Do not assume the existing publisher Lambda package/runtime is the correct place to run FFmpeg.

Preferred architecture:

- render/encode the MP4 **before** publication approval;
- store the immutable approved MP4 in S3;
- keep the publisher responsible only for delivery to Meta.

This prevents video encoding from increasing scheduled-publication risk.

## Where rendering should run

Evaluate in this order:

1. existing commissioning/CI environment with FFmpeg installed;
2. a dedicated container/job if scheduled automatic generation later requires it;
3. Lambda layer/container only if package/runtime size and encoding duration remain sensible.

Do not redesign AWS until actual rendering benchmarks exist.

## Storage cost

Expected to be low. MP4 assets are larger than JPEGs, but content volume remains modest.

Retain approved publication assets consistently with existing publication asset policy.

---

# Implementation decision gates

These decisions affect architecture/production behaviour and require explicit approval.

## Gate A — proceed after manual prototype?

Before modifying the production publisher, generate 2-3 local/CI Reel prototypes from existing data.

User approves whether the format is visually worthwhile.

## Gate B — first content family

**Recommended:** polling.

Reason:

- compact numerical story;
- existing visual logic;
- low semantic compression risk;
- naturally suited to motion.

Bill Tracker should be second.

## Gate C — video engine

**Recommended:** FFmpeg + deterministic frame sequence.

Confirm before adding binary/runtime dependencies.

## Gate D — production Reel publishing

Only after prototypes and preferably a small Trial/manual pilot show useful discovery signal.

This gate authorises changes to:

- publication models;
- asset validation/storage;
- Meta provider;
- publisher orchestration;
- tests;
- potentially runtime packaging.

## Gate E — automated scheduling

After a real API Reel canary succeeds and reconciliation/idempotency behaviour is proven, permit Reels to use the existing scheduling system.

Do not jump directly from prototype to recurring unattended scheduling.

---

# Future implementation sequence

## Stage 1 — prototype only; no publishing changes

1. Read this document and current project docs.
2. Inspect current polling/Bill/party outputs.
3. Recheck Meta Reel technical requirements.
4. Confirm FFmpeg is available in the chosen development/CI environment.
5. Define one storyboard (`poll_change_v1`).
6. Render 1080x1920 frames using current palette/data.
7. Assemble one MP4.
8. Run FFprobe/visual QA.
9. Produce cover + contact-sheet previews.
10. Ask user to approve/reject the visual format.

## Stage 2 — manual platform pilot

After visual approval:

1. produce 1-2 approved Reel assets;
2. confirm account exposes Trial Reels if Trial is desired;
3. manually publish only the agreed pilot(s);
4. record experiment/media identity;
5. collect 24h/72h/7d metrics;
6. compare against carousel baseline;
7. decide whether API integration is justified.

## Stage 3 — production integration PR

After explicit approval:

1. create implementation branch;
2. add video asset finalisation/model support;
3. add immutable S3 video handling;
4. add Reel publication request support;
5. add Meta `create_reel_container` support;
6. add video-processing/reconciliation handling;
7. add tests/mocks;
8. add operations documentation;
9. add canary path;
10. open PR;
11. do not deploy automatically.

## Stage 4 — Reel publishing canary

After deployment approval:

1. publish one explicitly approved Reel through the API;
2. verify container processing;
3. verify permanent media ID recorded;
4. verify cover/feed behaviour;
5. verify caption/first-comment behaviour;
6. verify Insights mapping;
7. inspect Instagram manually;
8. document any discrepancies.

## Stage 5 — scheduled pilot

Only after canary success:

1. schedule a small number of Reels;
2. confirm unattended execution;
3. confirm no regression in image/carousel publishing;
4. compare performance at 72h/7d/30d;
5. standardise only formats that show useful lift.

---

# Workload / cost assessment

| Activity | Expected upside | Setup effort | Recurring manual effort | Cost | Automation potential |
|---|---|---|---|---|---|
| Poll-change Reel template | High | Medium | Near-zero | €0/very low infra | Very high |
| Bill-effect Reel template | High | Medium | Near-zero | €0/very low infra | High |
| Party issue-ranking Reel | Medium-high | Medium | Near-zero | €0/very low infra | Very high |
| Manual Trial Reels | High learning value | Low | Several minutes per pilot | €0 | Low |
| API Reel publishing | High operational value | Medium-high | Near-zero | Very low | Very high |
| Trend-audio research | Uncertain | Low setup | High recurring | Variable | Low |
| Talking-head video | Potentially high | High | High recurring | €0+ | Low |
| AI/synthetic presenter | Unproven | High | Medium | Variable | Medium | 

**Recommendation:** invest only in deterministic data-led Reels and API automation. Do not create a recurring human video-production obligation.

---

# Stop / continue rules

## Continue developing Reels if

Repeated tests show:

- meaningful incremental non-follower reach;
- follow conversion that is not materially worse than feed/carousel content;
- useful shares;
- acceptable retention;
- low recurring manual cost.

## Narrow Reels if

Only certain data families perform well.

For example, it is entirely acceptable for EirePolitic to use Reels mainly for polling and evergreen explainers while keeping Bill Tracker primarily carousel-based.

## Stop scaling Reels if

- views are high but followers/profile activity remain negligible;
- technical maintenance is disproportionate;
- video encoding/publishing makes production less reliable;
- necessary caveats make the format unreadable;
- manual effort begins creeping upward.

The project does not need Reels for their own sake.

---

# Risks and safeguards

## Production reliability

Do not render video inside the critical scheduled-publishing step.

Approved MP4 should exist before publishing begins.

## Semantic compression

Short video can encourage oversimplification. Reject a Reel candidate if the necessary context cannot fit clearly.

## Copyright/audio

Do not automate commercial/trending music use without clear platform/API rights.

## Accessibility

Essential information must be visible without sound. Use readable text duration and sufficient contrast.

## Platform/API drift

Recheck Meta's Reel publishing parameters, specs, and insights before implementation.

## Trial Reel assumption

Do not claim Trial Reels can be automated unless the current official API explicitly supports it.

## Publisher regression

Image/carousel behaviour is already working. Reel additions require regression tests proving existing publication types remain unchanged.

---

# Information that may require the user

Very little user input is needed during planning.

Material decisions should be requested only at these points:

- approval/rejection of the first visual Reel prototype;
- approval to introduce FFmpeg/video dependencies;
- approval to extend the production publisher to Reels;
- approval of the first live/manual Trial Reel or API canary;
- approval before unattended scheduled Reel publishing is enabled.

The user should not be asked to:

- manually edit each Reel;
- research trends;
- choose music for every post;
- record voiceovers;
- build storyboards by hand.

---

# Handoff instructions for future LLM chats

When implementing this workstream:

1. Read this page and the master growth plan.
2. Read the current Insights and Discovery Hooks workstreams.
3. Inspect the current `Eirepolitic-data-pipeline` `main` branch; do not assume the static-only state documented here is still current.
4. Inspect publication models, asset finalisation, publisher, Meta client, tests, and infrastructure before changing anything.
5. Recheck current Meta official Reel publishing documentation and Trial Reel availability.
6. Verify actual Reel API parameters instead of copying old examples.
7. Prototype video generation **without modifying production publishing first**.
8. Prefer polling as the first prototype unless current performance evidence supports another family.
9. Use deterministic approved data and hook text.
10. Preserve project-specific semantic safeguards.
11. Prefer FFmpeg/static frames unless another approach has a demonstrated operational advantage.
12. Generate QA previews/contact sheets before requesting user approval.
13. Do not introduce music licensing dependencies in the first version.
14. Do not alter the working image/carousel publisher until the user explicitly approves Reel integration.
15. When implementing publishing, preserve existing idempotency/reconciliation guarantees.
16. Use a canary before scheduled automation.
17. Link Reel publications to Insights and experiment metadata.
18. Update this page with measured results, supported Meta behaviour, and promoted/rejected formats.

---

# Completion criteria

This workstream is mature when:

- EirePolitic has at least one proven automated 9:16 Reel format;
- the Reel can be generated from existing structured data with no bespoke editing;
- the approved MP4 passes deterministic technical/semantic QA;
- publishing can occur safely through Meta without weakening image/carousel reliability;
- Reel media IDs join cleanly to the Insights layer;
- performance can be compared against equivalent feed/carousel content;
- only content families showing useful acquisition lift are produced as Reels;
- recurring manual workload remains close to zero.

The target end state is not “post lots of Reels.” It is **automatically deploy proven structured information into an additional discovery surface when the data shows that doing so earns useful new audience**.
