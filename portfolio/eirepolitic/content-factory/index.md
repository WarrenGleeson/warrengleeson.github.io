---
layout: case-study
title: Turning Data Into Repeatable Visual Content
permalink: /portfolio/eirepolitic/content-factory/
presentation: editorial
kicker: Eirepolitic deep dive
summary: A deterministic Instagram content factory that turns validated data into reviewable visual assets, supports iterative design feedback, and keeps publication separate from rendering.
tags:
  - Automation
  - Data Visualisation
  - Content Systems
---

<section class="case-study-section case-study-two-column">
  <div>
    <p class="editorial-kicker">The problem</p>
    <h2>Good social graphics should not depend on rebuilding the design by hand every time.</h2>
  </div>
  <div>
    <p>Eirepolitic needed a way to turn structured political data into consistent Instagram carousels without manually recreating every chart, title, label, colour and layout for each post.</p>
    <p>The content factory treats visual production as a reproducible pipeline: data enters through a defined project adapter, a deterministic renderer builds the slides, QA checks the output, and the exact generated assets are presented for human review before anything can become publishable.</p>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">The workflow</p>
  <h2>Separate data, rendering, review and publishing.</h2>
  <div class="classification-flow" role="img" aria-label="Content factory workflow">
    <div><strong>Validated data</strong><span>Oireachtas or polling datasets</span></div>
    <b>→</b>
    <div><strong>Project adapter</strong><span>resolve period and content inputs</span></div>
    <b>→</b>
    <div><strong>Renderer</strong><span>build repeatable slides</span></div>
    <b>→</b>
    <div><strong>QA</strong><span>check content and layout rules</span></div>
    <b>→</b>
    <div><strong>Human review</strong><span>approve or request changes</span></div>
  </div>
</section>

<section class="case-study-section case-study-two-column">
  <div>
    <p class="editorial-kicker">1 · Project-specific adapters</p>
    <h2>Each content series owns its data logic.</h2>
  </div>
  <div>
    <p>The factory does not assume every post has the same data shape. Each recurring series can define its own adapter, manifest and QA rules while still using the same rendering and review infrastructure.</p>
    <p>That keeps domain logic close to the project that needs it. A polling carousel can resolve its latest polling period differently from a monthly parliamentary issue profile without forcing both into one oversized generic schema.</p>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">2 · Deterministic rendering</p>
  <h2>The same input should produce the same visual result.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>The current factory uses repository-controlled Python renderers, layout definitions, palettes and reusable visual primitives. Text, charts, labels and party assets are placed by code rather than by an external design session that cannot be reproduced later.</p>
      <p>This makes design changes versionable. If a label is too small or a chart needs more spacing, the change can be made to a renderer parameter or project configuration, committed, and rerun against the same data.</p>
    </div>
    <div class="eirepolitic-tech-note"><strong>Tools in context</strong><span>Python · project YAML · renderer modules · layout definitions · reusable visual primitives</span></div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">3 · Review artifacts</p>
  <h2>Review the real output, not a description of it.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>Render workflows build a self-contained review page with the generated slides, contact sheets and downloadable assets. The review URL points at the actual output from that run, so design decisions are based on the same images that can later be promoted for publishing.</p>
      <p>Review state is tracked at both item and slide level. A run cannot be marked ready for posting unless every required item and slide is explicitly approved.</p>
    </div>
    <div class="editorial-placeholder screenshot-slot"><strong>Screenshot needed</strong><span>Real browser-based review page showing generated carousel slides</span></div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">4 · Conversational iteration</p>
  <h2>Use natural-language feedback without letting the chat become the production system.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>I can review a render in chat and describe the problem in ordinary language—for example, that a slide feels crowded or that labels need more emphasis. The feedback is translated into a concrete renderer or project-setting change, the repository is updated, and the real render workflow is run again.</p>
      <p>The important boundary is that the chat does not manufacture the final production image. It helps operate and iterate the coded rendering system. The final asset is still produced by the repository workflow and remains reproducible.</p>
    </div>
    <div class="editorial-placeholder screenshot-slot"><strong>Screenshot needed</strong><span>Conversational design iteration showing feedback followed by a rerendered result</span></div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">5 · Design feedback becomes reusable</p>
  <h2>Fix the system, not just one screenshot.</h2>
  <div class="cost-control-grid">
    <div><strong>Feedback</strong><span>“Labels too small” or “slide too crowded.”</span></div>
    <div><strong>Interpretation</strong><span>Map the comment to a known visual control or layout decision.</span></div>
    <div><strong>Technical change</strong><span>Update project configuration or renderer code in a small commit.</span></div>
    <div><strong>Rerender</strong><span>Run the same project and period again for comparison.</span></div>
  </div>
  <p>When a recurring feedback pattern appears more than once, it can be parameterised instead of becoming a collection of one-off fixes.</p>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">6 · QA before review</p>
  <h2>Visual generation still has data-quality rules.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>The factory can check more than whether an image file exists. Project-specific QA can validate required content, data readiness and known layout constraints before a run is presented for approval.</p>
      <p>If QA fails, the workflow reports the failed check rather than silently retrying or loosening the rule. That keeps visual output tied to the same reliability principles as the upstream data pipeline.</p>
    </div>
    <div class="model-stack">
      <div><strong>Input readiness</strong><span>validated source data</span></div>
      <div><strong>Render checks</strong><span>required outputs and project-specific assertions</span></div>
      <div><strong>Review page</strong><span>human inspection of actual assets</span></div>
      <div><strong>Approval state</strong><span>explicit approved / changes requested / rejected state</span></div>
    </div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">7 · Publishing is deliberately separate</p>
  <h2>The factory can finish a post without being allowed to publish it.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>The content factory enforces a hard boundary: rendering and review do not directly publish to Instagram. Factory outputs retain publishing-disabled state even after they are marked ready for posting.</p>
      <p>Only the separate publishing system can take the exact approved artifact, promote immutable assets, record the approval fingerprint, and execute an immediate or scheduled publication.</p>
    </div>
    <div class="eirepolitic-tech-note"><strong>Safety boundary</strong><span>Factory: render + review · Publishing system: approval fingerprint + AWS execution + Meta</span></div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">What this demonstrates</p>
  <h2>A visual workflow can be engineered like a data product.</h2>
  <div class="capability-grid">
    <div><strong>Reproducibility</strong><span>repository-controlled layouts, inputs and render code</span></div>
    <div><strong>Extensibility</strong><span>project adapters and reusable rendering primitives</span></div>
    <div><strong>Human-in-the-loop design</strong><span>real output reviewed before approval</span></div>
    <div><strong>Operational feedback loops</strong><span>natural-language feedback translated into versioned technical changes</span></div>
    <div><strong>Quality control</strong><span>QA and explicit item/slide review state</span></div>
    <div><strong>Separation of concerns</strong><span>rendering cannot bypass publishing approval</span></div>
  </div>
</section>

<section class="case-study-section technical-links-section">
  <p class="editorial-kicker">Go deeper</p>
  <h2>Canonical technical documentation</h2>
  <div class="technical-link-grid">
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/director/README.md"><strong>Eirepolitic Director</strong><span>Current operational entry point for content generation and publishing capabilities</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/director/workflows_v1.md"><strong>Content workflows</strong><span>Existing-series, new-post, feedback-loop and data-capability procedures</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/director/capabilities.yml"><strong>Factory capabilities</strong><span>Rendering, review, preview hosting, data resolution and factory boundaries</span></a>
    <a href="{{ '/portfolio/eirepolitic/' | relative_url }}"><strong>Back to Eirepolitic</strong><span>Return to the end-to-end project case study</span></a>
  </div>
</section>
