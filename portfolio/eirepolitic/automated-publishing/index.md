---
layout: case-study
title: Automating Instagram Publishing Without Giving Up Control
permalink: /portfolio/eirepolitic/automated-publishing/
presentation: editorial
kicker: Eirepolitic deep dive
summary: The control-plane mechanics behind immutable handoff, approval fingerprints, durable publication state, scheduling, idempotency, and runtime credentials.
---

<a class="deep-dive-back" href="{{ '/portfolio/eirepolitic/' | relative_url }}">← Back to the Eirepolitic flagship case study</a>

<section class="deep-dive-intro">
  <p class="editorial-kicker">What this page adds</p>
  <h2>The difficult part is not calling the Instagram API. It is proving what is allowed to be published, when, and exactly once.</h2>
  <p>The flagship shows the high-level Approved → Scheduled / executed → Published flow. This page focuses on the control plane behind that flow: how an approved render becomes an immutable publication request, how approval is bound to exact content, why DynamoDB is authoritative, what the scheduler is allowed to carry, and how retries avoid duplicate posts.</p>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">1 · Exact artifact handoff</p>
    <h2>Publishing starts from the reviewed factory artifact; it does not rebuild the post.</h2>
  </div>
  <div class="deep-dive-two-column">
    <div>
      <p>The publishing workflow identifies the exact factory run that was reviewed. Its handoff describes the ordered slides, caption, project, period and QA state.</p>
      <p>Those reviewed images are converted into deterministic delivery JPEGs and stored as immutable, content-addressed assets. Corrections create a new package rather than overwriting the approved one.</p>
    </div>
    <div class="deep-dive-rule-list">
      <div><strong>Reviewed run</strong><span>Exact candidate already inspected by a human.</span></div>
      <div><strong>Publication handoff</strong><span>Ordered media, caption and project identity.</span></div>
      <div><strong>Immutable delivery package</strong><span>Content-addressed assets ready for execution.</span></div>
    </div>
  </div>
</section>

<section class="deep-dive-visual-pair" aria-label="Suggested automated-publishing visuals">
  <div class="deep-dive-visual-placeholder">
    <span class="deep-dive-visual-number">Visual 01</span>
    <strong>Approval fingerprint diagram</strong>
    <p>Show reviewed media + exact caption + account/options being reduced to one deterministic approval fingerprint, with a changed caption or media order producing a different fingerprint.</p>
    <small>Best source: purpose-built diagram based on the real fingerprint fields. Keep scheduling time outside the content fingerprint to show the separation clearly.</small>
  </div>
  <div class="deep-dive-visual-placeholder">
    <span class="deep-dive-visual-number">Visual 02</span>
    <strong>Publication ledger + scheduler screenshot</strong>
    <p>Show one real publication record in the durable ledger beside its one-time EventBridge schedule / inventory entry.</p>
    <small>Best source: redacted DynamoDB item plus EventBridge schedule inventory, or a purpose-built diagram using the actual state fields.</small>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">2 · Approval fingerprint</p>
    <h2>Approval authorises exact content, not a vague concept of the post.</h2>
  </div>
  <div class="deep-dive-two-column">
    <div>
      <p>The approval fingerprint covers the material publication fields: publication version, ordered media and hashes, exact caption, account, tags, alt text and other content options.</p>
      <p>If the caption changes, media order changes or a different image is substituted, the fingerprint changes and the old approval no longer authorises execution. Changing only the confirmed schedule time is handled separately.</p>
    </div>
    <div class="deep-dive-emphasis">
      <span>Control principle</span>
      <strong>The worker may execute only the exact content a human approved.</strong>
    </div>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">3 · Durable state</p>
    <h2>DynamoDB is the ledger; EventBridge Scheduler is only the future clock.</h2>
  </div>
  <div class="deep-dive-two-column">
    <div>
      <p>The publication record persists identity, version, approval references, immutable asset references, schedule and execution history. That record remains after a one-time schedule has fired and deleted itself.</p>
      <p>The schedule inventory can therefore reconcile the durable ledger against live scheduler jobs before a new post is added. The scheduler is an execution mirror, not the source of truth.</p>
    </div>
    <div class="deep-dive-sequence deep-dive-sequence-vertical">
      <div><span>01</span><strong>DynamoDB record</strong><small>Canonical publication state and history.</small></div>
      <div><span>02</span><strong>EventBridge schedule</strong><small>Temporary one-time execution trigger.</small></div>
      <div><span>03</span><strong>Lambda worker</strong><small>Reloads approved state and executes deterministically.</small></div>
      <div><span>04</span><strong>Provider state</strong><small>Container / permanent media IDs persisted back to the ledger.</small></div>
    </div>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">4 · Minimal scheduler payload</p>
    <h2>The future job carries identity and version—not the post itself.</h2>
  </div>
  <div class="deep-dive-field-list deep-dive-field-list-compact">
    <div><strong>publication_id</strong><span>Which approved publication should execute.</span></div>
    <div><strong>expected_version</strong><span>Guard against executing a superseded revision.</span></div>
    <div><strong>No raw caption/media</strong><span>Content is reloaded from controlled stores.</span></div>
    <div><strong>No credentials</strong><span>Secrets are retrieved by the worker at runtime.</span></div>
  </div>
  <p>This prevents the scheduler invocation itself from injecting arbitrary content and removes any requirement for the chat or agent that created the schedule to remain alive.</p>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">5 · Idempotency</p>
    <h2>A retry should reconcile state, not start another Instagram post.</h2>
  </div>
  <div class="deep-dive-feedback-flow">
    <div><span>01</span><strong>Claim</strong><p>Atomically acquire execution for the publication/version.</p></div>
    <div><span>02</span><strong>Persist</strong><p>Store Meta container IDs and permanent media IDs as soon as they exist.</p></div>
    <div><span>03</span><strong>Reconcile</strong><p>After an uncertain response, inspect existing provider state before retrying.</p></div>
    <div><span>04</span><strong>Guard</strong><p>Recorded success blocks another publish attempt for the same approved version.</p></div>
  </div>
</section>

<section class="deep-dive-visual-single">
  <div class="deep-dive-visual-placeholder">
    <span class="deep-dive-visual-number">Visual 03</span>
    <strong>Idempotent execution state machine</strong>
    <p>Diagram the publication moving through claimed → container created → provider IDs persisted → publish confirmed, including the reconciliation path after an uncertain outcome.</p>
    <small>Best source: purpose-built state diagram grounded in the Lambda execution states and persisted provider identifiers.</small>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">6 · Runtime-only secrets</p>
    <h2>The publishing interface never needs the production Meta token.</h2>
  </div>
  <div class="deep-dive-two-column">
    <div>
      <p>The Meta credential is stored in AWS Secrets Manager and retrieved by the publisher role only when execution requires it. GitHub deployment credentials and the conversational control layer do not need the production token value.</p>
      <p>The Lambda API also does not accept raw token material from callers. Its surface is intentionally narrow: healthcheck, execute an already-approved publication, or handle a scheduler payload.</p>
    </div>
    <div class="deep-dive-emphasis">
      <span>Security boundary</span>
      <strong>GitHub deploys · Secrets Manager stores · Lambda retrieves at execution.</strong>
    </div>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">Production proof</p>
    <h2>The complete path was exercised against the real account.</h2>
  </div>
  <p>On September 26, 2026, the system completed both an immediate canary and a scheduled canary against the real Instagram Professional account. Those tests exercised the Meta route, S3 delivery assets, DynamoDB state, Lambda execution, durable idempotency, EventBridge scheduling role and dead-letter path, plus permanent media-ID recording. The test posts were then manually deleted.</p>
</section>

<section class="case-study-section technical-links-section">
  <p class="editorial-kicker">Implementation detail</p>
  <h2>Canonical technical sources</h2>
  <div class="technical-link-grid">
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/operations/instagram_publishing_standard.md"><strong>Instagram publishing standard</strong><span>Production workflow, schedule ledger, runtime behaviour and operating procedure</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/implementation/instagram_publishing_implementation_plan.md"><strong>Original implementation design</strong><span>Architecture, state model, fingerprinting, idempotency, security and canary gates</span></a>
  </div>
  <a class="deep-dive-return" href="{{ '/portfolio/eirepolitic/' | relative_url }}">Return to the Eirepolitic flagship →</a>
</section>
