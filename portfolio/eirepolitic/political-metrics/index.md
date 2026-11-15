---
layout: case-study
title: Building Political Metrics Without Inventing Political Meaning
permalink: /portfolio/eirepolitic/political-metrics/
presentation: editorial
kicker: Eirepolitic deep dive
summary: The implementation detail behind historical attribution, certified joins, metric denominators, reliability rules, and additive materialisation.
---

<a class="deep-dive-back" href="{{ '/portfolio/eirepolitic/' | relative_url }}">← Back to the Eirepolitic flagship case study</a>

<section class="deep-dive-intro">
  <p class="editorial-kicker">What this page adds</p>
  <h2>The calculation is usually the easy part. Defining the valid population is harder.</h2>
  <p>The flagship introduces metric contracts, historical attribution and reliability rules. This page goes deeper into how those rules are implemented: event-date joins, certified legislation relationships, denominator construction, and materialised additive components that can be recombined safely.</p>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">1 · Historical joins</p>
    <h2>Political context is resolved on the event date, not from today’s profile.</h2>
  </div>
  <div class="deep-dive-two-column">
    <div>
      <p>Party, constituency and Dáil membership are evaluated against the date of the speech, vote or question. The underlying history uses start-inclusive, end-exclusive ranges so transitions can be represented without assigning two active records to the same instant.</p>
      <p>If the source history contains a genuine overlap, validation fails rather than silently selecting a row. That makes historical ambiguity visible before it can contaminate a metric.</p>
    </div>
    <div class="deep-dive-sequence deep-dive-sequence-vertical">
      <div><span>01</span><strong>Event date</strong><small>Speech, vote or parliamentary question.</small></div>
      <div><span>02</span><strong>Active membership</strong><small>Was this person eligible on that date?</small></div>
      <div><span>03</span><strong>Historical affiliation</strong><small>Which party and constituency were valid then?</small></div>
      <div><span>04</span><strong>Metric population</strong><small>Include only rows satisfying the metric contract.</small></div>
    </div>
  </div>
</section>

<section class="deep-dive-visual-pair" aria-label="Suggested political-metrics visuals">
  <div class="deep-dive-visual-placeholder">
    <span class="deep-dive-visual-number">Visual 01</span>
    <strong>Event-date attribution diagram</strong>
    <p>Show one member moving through historical membership / party ranges with a speech or vote landing on a specific date and resolving to the correct context.</p>
    <small>Best source: purpose-built timeline diagram using the actual start-inclusive, end-exclusive join rule.</small>
  </div>
  <div class="deep-dive-visual-placeholder">
    <span class="deep-dive-visual-number">Visual 02</span>
    <strong>Certified Bill-section bridge</strong>
    <p>Show Bill source evidence resolving to an exact canonical debate section, then safely joining downstream speeches and divisions without row multiplication.</p>
    <small>Best source: purpose-built relationship diagram or a cropped documentation/table view showing accepted and rejected section matches.</small>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">2 · Deterministic parliamentary context</p>
    <h2>Use source structure before semantic inference.</h2>
  </div>
  <div class="deep-dive-two-column">
    <div>
      <p>Speech context is resolved from explicit Oireachtas structure where possible: Oral Questions, Bill or legislation sections, Leaders’ Questions, statements, procedural business, motion proceedings, or an explicit <code>other</code> fallback.</p>
      <p>The remaining <code>other</code> category is not filled with a model merely to increase coverage. The objective is reproducible context rather than maximum labelling.</p>
    </div>
    <div class="deep-dive-emphasis">
      <span>Validated production snapshot</span>
      <strong>66,192 speeches · 53,452 deterministically contextualised · ~80.75% non-other coverage</strong>
    </div>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">3 · Certified legislation joins</p>
    <h2>A debate can mention a Bill without every speech belonging to that Bill.</h2>
  </div>
  <div class="deep-dive-two-column">
    <div>
      <p>The production bridge resolves legislation context at exact debate-section grain. Multiple pieces of source evidence must agree before a Bill-section relationship is emitted.</p>
      <p>Conflicts, multi-Bill sections and unresolved cases are excluded. Duplicate source records are collapsed so they cannot multiply downstream speeches or divisions.</p>
    </div>
    <div class="deep-dive-stat-list">
      <div><strong>168</strong><span>distinct Bills in the certified bridge</span></div>
      <div><strong>371</strong><span>exact canonical sections linked to Bills</span></div>
      <div><strong>7,352</strong><span>speeches linked through exact section membership</span></div>
      <div><strong>168</strong><span>divisions linked through exact section membership</span></div>
    </div>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">4 · Denominator contracts</p>
    <h2>A metric definition includes what is allowed into the denominator.</h2>
  </div>
  <div class="deep-dive-rule-list deep-dive-rule-list-wide">
    <div><strong>Speech activity</strong><span>Can use authoritative debate days rather than only days where speech rows happen to exist.</span></div>
    <div><strong>Voting participation</strong><span>Uses eligible divisions during active Dáil membership; a missing recorded vote is not labelled physical absence.</span></div>
    <div><strong>Issue share</strong><span>Excludes <code>NONE</code> from policy-share denominators.</span></div>
    <div><strong>Monthly results</strong><span>Publishes completed calendar months only rather than comparing partial and complete periods.</span></div>
  </div>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">5 · Reliability</p>
    <h2>The metric can carry a public-use status alongside the value.</h2>
  </div>
  <div class="deep-dive-three-state">
    <div><span>10+ qualifying observations</span><strong>Reliable</strong><p>Enough evidence for normal public comparison.</p></div>
    <div><span>5–9 qualifying observations</span><strong>Caution</strong><p>Usable only with an explicit reliability warning.</p></div>
    <div><span>&lt;5 qualifying observations</span><strong>Insufficient</strong><p>Do not present as a meaningful comparison.</p></div>
  </div>
  <p>This threshold example comes from party voting unity, but the broader rule is consistent: if the source data cannot support a defensible comparison, the output is withheld rather than forced.</p>
</section>

<section class="case-study-section">
  <div class="deep-dive-section-heading">
    <p class="editorial-kicker">6 · Materialisation</p>
    <h2>Store additive foundations, then build consumer metrics from them.</h2>
  </div>
  <div class="deep-dive-two-column">
    <div>
      <p>The metrics layer materialises daily or event-level additive components that can be recombined for different date ranges. This avoids rescanning raw facts and avoids mathematically unsafe operations such as averaging percentages with different denominators.</p>
      <p>Completed-month consumer results are written into the same immutable candidate batch as the canonical data that produced them. They cannot update the production pointer independently.</p>
    </div>
    <div class="deep-dive-sequence deep-dive-sequence-vertical">
      <div><span>01</span><strong>Canonical candidate</strong><small>Validated source for the analytical build.</small></div>
      <div><span>02</span><strong>Additive components</strong><small>Daily or event-level numerator / denominator foundations.</small></div>
      <div><span>03</span><strong>Consumer results</strong><small>Completed-period rows suitable for downstream use.</small></div>
      <div><span>04</span><strong>Candidate validation</strong><small>Required datasets must be present before promotion.</small></div>
    </div>
  </div>
</section>

<section class="case-study-section technical-links-section">
  <p class="editorial-kicker">Implementation detail</p>
  <h2>Canonical technical sources</h2>
  <div class="technical-link-grid">
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/political_metrics_foundation.md"><strong>Political metrics foundation</strong><span>Metric definitions, denominators, historical attribution and materialisation design</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/research/speech_context_implementation.md"><strong>Speech-context implementation</strong><span>Deterministic context rules, production footprint and audit behaviour</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/research/legislation_bridge_implementation.md"><strong>Certified legislation bridge</strong><span>Exact Bill-section relationships and rejected unsafe joins</span></a>
  </div>
  <a class="deep-dive-return" href="{{ '/portfolio/eirepolitic/' | relative_url }}">Return to the Eirepolitic flagship →</a>
</section>
