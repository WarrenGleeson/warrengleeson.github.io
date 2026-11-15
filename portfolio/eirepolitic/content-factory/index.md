---
layout: case-study
title: Turning Data Into Repeatable Visual Content
permalink: /portfolio/eirepolitic/content-factory/
presentation: editorial
kicker: Eirepolitic deep dive
summary: The implementation behind project adapters, deterministic rendering, review-state tracking, QA, and reusable design feedback.
---

<a class="deep-dive-back" href="{{ '/portfolio/eirepolitic/' | relative_url }}">← Back to the Eirepolitic flagship case study</a>

<section class="deep-dive-intro">
  <p class="editorial-kicker">What this page adds</p>
  <h2>The content factory is less about “making graphics” than turning design into a repeatable build system.</h2>
  <p>The flagship shows the Render → Review → Iterate workflow and the real outputs. This page focuses on what makes that workflow reusable: project adapters, deterministic render inputs, item/slide review state, QA gates, and the way repeated visual feedback becomes configuration or renderer code rather than one-off manual edits.</p>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">1 · Project adapters</p>
    <h2>Each recurring content series owns its own data logic.</h2>
  </div>
  <div class="deep-dive-two-column">
    <div>
      <p>The factory does not force polling, parliamentary metrics and future content types into one universal input schema. Each series can define how it resolves periods, selects datasets, builds content inputs and applies project-specific QA.</p>
      <p>The shared factory then handles the common mechanics: rendering, artifact packaging, review, approval state and handoff. This keeps domain logic close to the project without duplicating the whole workflow.</p>
    </div>
    <div class="deep-dive-rule-list">
      <div><strong>Project adapter</strong><span>Resolve period, source datasets and content inputs.</span></div>
      <div><strong>Project manifest</strong><span>Declare expected outputs and project-level settings.</span></div>
      <div><strong>Shared factory</strong><span>Render, package, review and track state consistently.</span></div>
    </div>
  </div>
</section>

<section class="deep-dive-visual-pair" aria-label="Suggested content-factory visuals">
  <div class="deep-dive-visual-placeholder">
    <span class="deep-dive-visual-number">Visual 01</span>
    <strong>Project adapter + manifest screenshot</strong>
    <p>Show a real project configuration beside the small adapter entry point that resolves a period and builds render inputs.</p>
    <small>Best source: cropped YAML/config plus the corresponding adapter function. Emphasise separation between project data logic and shared rendering infrastructure.</small>
  </div>
  <div class="deep-dive-visual-placeholder">
    <span class="deep-dive-visual-number">Visual 02</span>
    <strong>Review-state / artifact anatomy diagram</strong>
    <p>Show one factory run containing generated slides, contact sheet, review metadata and explicit item/slide approval state.</p>
    <small>Best source: purpose-built diagram using actual artifact names, or a browser/Actions capture where the review-state files are visible.</small>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">2 · Deterministic rendering</p>
    <h2>Design choices live in versioned inputs and code.</h2>
  </div>
  <div class="deep-dive-two-column">
    <div>
      <p>Repository-controlled Python renderers, layout definitions, palettes and reusable primitives determine the output. Given the same project inputs and renderer version, the workflow can reproduce the same visual rather than depending on a design session that only existed once.</p>
      <p>That also makes visual changes reviewable. A spacing, label-size or chart-layout adjustment can be represented as a small code/configuration change and rerun against the same data.</p>
    </div>
    <div class="deep-dive-emphasis">
      <span>Design as code</span>
      <strong>Python · project YAML · renderer modules · layout definitions · reusable visual primitives</strong>
    </div>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">3 · Review state</p>
    <h2>“Looks good” becomes explicit state, not an informal memory.</h2>
  </div>
  <div class="deep-dive-two-column">
    <div>
      <p>A factory run produces the real slides plus supporting review artifacts. Approval is tracked at item and slide level, so a run cannot become ready for posting simply because someone reviewed one representative image.</p>
      <p>The review URL therefore points to the exact candidate assets, while the associated state records which items were approved, rejected or sent back for changes.</p>
    </div>
    <div class="deep-dive-sequence deep-dive-sequence-vertical">
      <div><span>01</span><strong>Generated candidate</strong><small>Exact slides produced by the repository renderer.</small></div>
      <div><span>02</span><strong>Review artifact</strong><small>Browser page, contact sheet and downloadable outputs.</small></div>
      <div><span>03</span><strong>Explicit decisions</strong><small>Approved / changes requested / rejected at required granularity.</small></div>
      <div><span>04</span><strong>Ready state</strong><small>Available only when all required review conditions pass.</small></div>
    </div>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">4 · Feedback loop</p>
    <h2>The durable result of feedback is a repository change.</h2>
  </div>
  <div class="deep-dive-feedback-flow">
    <div><span>01</span><strong>Observe</strong><p>“Labels are too small” or “this slide is too crowded.”</p></div>
    <div><span>02</span><strong>Map</strong><p>Identify the renderer parameter, project setting or layout rule responsible.</p></div>
    <div><span>03</span><strong>Change</strong><p>Commit a small code/config update rather than editing one image manually.</p></div>
    <div><span>04</span><strong>Rerender</strong><p>Run the same project and period again for a direct comparison.</p></div>
  </div>
  <p>When the same kind of feedback appears repeatedly, it can become a reusable parameter or layout rule. That is the point where design feedback improves the system rather than only the current post.</p>
</section>

<section class="deep-dive-visual-single">
  <div class="deep-dive-visual-placeholder">
    <span class="deep-dive-visual-number">Visual 03</span>
    <strong>Before / after renderer change</strong>
    <p>Pair two real renders from the same project and period with the small config or renderer diff that produced the improvement.</p>
    <small>Best source: one concrete feedback iteration where the data stayed constant and only the visual system changed.</small>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">5 · QA before human review</p>
    <h2>Rendering can fail for data reasons as well as visual ones.</h2>
  </div>
  <div class="deep-dive-rule-list deep-dive-rule-list-wide">
    <div><strong>Input readiness</strong><span>Required validated source data and project inputs must exist.</span></div>
    <div><strong>Output completeness</strong><span>Every expected slide/artifact must be produced.</span></div>
    <div><strong>Project assertions</strong><span>Known content or layout constraints can fail the run before approval.</span></div>
    <div><strong>No silent loosening</strong><span>A failed check is reported rather than retried with weaker rules.</span></div>
  </div>
</section>

<section class="case-study-section technical-links-section">
  <p class="editorial-kicker">Implementation detail</p>
  <h2>Canonical technical sources</h2>
  <div class="technical-link-grid">
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/director/README.md"><strong>Eirepolitic Director</strong><span>Operational entry point for content generation and publishing capabilities</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/director/workflows_v1.md"><strong>Content workflows</strong><span>Existing-series, new-post, feedback-loop and data-capability procedures</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/director/capabilities.yml"><strong>Factory capabilities</strong><span>Rendering, review, preview hosting, data resolution and factory boundaries</span></a>
  </div>
  <a class="deep-dive-return" href="{{ '/portfolio/eirepolitic/' | relative_url }}">Return to the Eirepolitic flagship →</a>
</section>
