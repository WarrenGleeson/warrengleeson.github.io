---
layout: case-study
title: Automating Instagram Publishing Without Giving Up Control
permalink: /portfolio/eirepolitic/automated-publishing/
presentation: editorial
kicker: Eirepolitic deep dive
summary: A controlled publishing pipeline that separates human approval from automated execution, binds approval to exact content, and uses AWS to schedule and publish safely.
tags:
  - AWS
  - Automation
  - Publishing
---

<section class="case-study-section case-study-two-column">
  <div>
    <p class="editorial-kicker">The problem</p>
    <h2>Scheduling a post is easy. Publishing the right approved post exactly once is harder.</h2>
  </div>
  <div>
    <p>The publishing system had to automate a real Instagram account without letting automation silently change content, publish the wrong render, duplicate a post after a retry, or depend on an LLM staying alive until a future time.</p>
    <p>I designed the system so human approval controls intent, while deterministic AWS services handle the actual future execution.</p>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">The architecture</p>
  <h2>Approval, storage, scheduling and execution are separate responsibilities.</h2>
  <div class="publishing-stack">
    <div><strong>Reviewed factory artifact</strong><span>the exact slides and caption already approved for use</span></div>
    <b>↓</b>
    <div><strong>Publishing workflow</strong><span>validates the handoff and creates immutable delivery assets</span></div>
    <b>↓</b>
    <div><strong>S3 + DynamoDB</strong><span>approved assets, publication request, approval and durable state</span></div>
    <b>↓</b>
    <div><strong>EventBridge Scheduler</strong><span>one-time future execution when scheduled</span></div>
    <b>↓</b>
    <div><strong>AWS Lambda</strong><span>reloads approved state and performs deterministic execution</span></div>
    <b>↓</b>
    <div><strong>Meta / Instagram</strong><span>publishes the final image or carousel</span></div>
  </div>
</section>

<section class="case-study-section case-study-two-column">
  <div>
    <p class="editorial-kicker">1 · Exact artifact handoff</p>
    <h2>The publishing step does not redesign or rebuild the post.</h2>
  </div>
  <div>
    <p>The publishing workflow starts from the exact GitHub Actions factory run that was visually reviewed. The artifact includes a publication handoff describing the ordered slides, caption, project, period and QA state.</p>
    <p>The publishing system converts those reviewed images into deterministic delivery JPEGs and stores them as immutable, content-addressed assets. Corrections create a new asset package instead of overwriting the approved one.</p>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">2 · Approval fingerprints</p>
  <h2>Approval belongs to exact content, not to a vague idea of the post.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>The publication approval is tied to a deterministic fingerprint of the material fields: publication version, ordered media and hashes, exact caption, account, tags, alt text and other requested options.</p>
      <p>If the caption changes, media order changes or a different asset is substituted, the fingerprint changes and the old approval no longer authorizes publication. A schedule-only change is handled separately so content does not need to be reapproved when only the confirmed time changes.</p>
    </div>
    <div class="eirepolitic-tech-note"><strong>Core idea</strong><span>Human approval is cryptographically bound to the exact content the worker is allowed to publish.</span></div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">3 · DynamoDB as the control ledger</p>
  <h2>The scheduler is not the source of truth.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>DynamoDB is the authoritative record of publication state. It stores the publication identity, version, schedule, approval references, immutable asset references and execution history.</p>
      <p>EventBridge Scheduler is deliberately only an execution mirror. One-time schedules delete themselves after they run, while the DynamoDB record remains as the durable history of what was approved, scheduled and executed.</p>
    </div>
    <div class="model-stack">
      <div><strong>DynamoDB</strong><span>canonical publication ledger</span></div>
      <div><strong>EventBridge Scheduler</strong><span>temporary one-time execution job</span></div>
      <div><strong>Schedule inventory</strong><span>cross-check ledger and live scheduler before adding another post</span></div>
    </div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">4 · Scheduling without an always-on agent</p>
  <h2>The LLM can choose the intent. AWS owns the future clock.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>When a user chooses a future local time, the system records the local timestamp, IANA timezone and resolved UTC instant. A one-time EventBridge schedule then invokes the publisher Lambda at that time.</p>
      <p>No chat session, agent process or model needs to remain alive. That makes the schedule durable, inspectable and independent of the interface that created it.</p>
    </div>
    <div class="eirepolitic-tech-note"><strong>Tools in context</strong><span>DynamoDB · EventBridge Scheduler · IANA timezones · AWS Lambda</span></div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">5 · Minimal scheduler payload</p>
  <h2>Do not put captions, images or credentials into the schedule.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>A scheduled job carries only publication identity and expected version. When invoked, Lambda reloads the approved publication request, immutable asset package, approval fingerprint, credentials and execution state from AWS.</p>
      <p>That keeps content and secrets out of the scheduler payload and means a scheduled invocation cannot inject arbitrary caption or image data into the worker.</p>
    </div>
    <div class="classifier-record-grid">
      <div><strong>publication_id</strong><span>which approved publication to execute</span></div>
      <div><strong>expected_version</strong><span>guards against executing the wrong revision</span></div>
      <div><strong>No raw content</strong><span>caption, media and token are reloaded from controlled stores</span></div>
    </div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">6 · Idempotency and retry safety</p>
  <h2>A retry must not become a duplicate Instagram post.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>The execution state is durable and keyed to the publication/version. Meta container IDs and permanent media IDs are persisted as the workflow progresses, so a retry can resume or reconcile instead of blindly starting again.</p>
      <p>If the final Meta publish request has an uncertain outcome, the worker checks the existing container state first. Once success is recorded, the publication guard prevents another publish attempt for the same approved version.</p>
    </div>
    <div class="safety-mode-grid">
      <div><strong>Claim</strong><span>atomically acquire the execution</span></div>
      <div><strong>Persist</strong><span>store provider IDs as soon as they exist</span></div>
      <div><strong>Reconcile</strong><span>check existing state after uncertain outcomes</span></div>
      <div><strong>Guard</strong><span>permanent success prevents duplicate publication</span></div>
    </div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">7 · Secrets stay outside the control interface</p>
  <h2>The publisher fetches credentials only at runtime.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>The Meta credential is stored in AWS Secrets Manager and retrieved by the publisher role only when execution requires it. GitHub deployment credentials and the conversational control layer do not need the production token value.</p>
      <p>The Lambda also does not accept raw token material from callers. Its API is intentionally narrow: healthcheck, execute an already-approved publication, or handle a scheduler payload.</p>
    </div>
    <div class="eirepolitic-tech-note"><strong>Security boundary</strong><span>GitHub deploys infrastructure · Secrets Manager stores Meta credential · Lambda retrieves it at execution</span></div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">8 · Production proof</p>
  <h2>The complete path was tested against the real account.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>On September 26, 2026, the system completed both an immediate canary and a scheduled canary against the real Instagram Professional account.</p>
      <p>Those tests exercised the actual Meta publishing route, S3 delivery assets, DynamoDB state, Lambda execution, durable idempotency, EventBridge scheduling role and dead-letter path, and permanent media-ID recording. The test posts were then manually deleted.</p>
    </div>
    <div class="editorial-placeholder screenshot-slot"><strong>Screenshot needed</strong><span>Published Eirepolitic Instagram example or schedule inventory view</span></div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">What this demonstrates</p>
  <h2>Automation is safest when intent and execution are separated.</h2>
  <div class="capability-grid">
    <div><strong>Workflow design</strong><span>reviewed artifacts flow into a separate publication control plane</span></div>
    <div><strong>AWS architecture</strong><span>S3, DynamoDB, EventBridge Scheduler, Lambda, Secrets Manager</span></div>
    <div><strong>State modelling</strong><span>versioned requests, approvals, schedules and execution history</span></div>
    <div><strong>Idempotency</strong><span>durable provider state prevents duplicate side effects</span></div>
    <div><strong>Security</strong><span>minimal payloads and runtime-only secret retrieval</span></div>
    <div><strong>Human control</strong><span>every live publication originates from an explicit approved artifact</span></div>
  </div>
</section>

<section class="case-study-section technical-links-section">
  <p class="editorial-kicker">Go deeper</p>
  <h2>Canonical technical documentation</h2>
  <div class="technical-link-grid">
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/operations/instagram_publishing_standard.md"><strong>Instagram publishing standard</strong><span>Current production workflow, schedule ledger, runtime behaviour and operating procedure</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/implementation/instagram_publishing_implementation_plan.md"><strong>Original implementation design</strong><span>Architecture, state model, fingerprinting, idempotency, security and canary gates</span></a>
    <a href="{{ '/portfolio/eirepolitic/' | relative_url }}"><strong>Back to Eirepolitic</strong><span>Return to the end-to-end project case study</span></a>
  </div>
</section>
