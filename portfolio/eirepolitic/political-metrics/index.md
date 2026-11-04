---
layout: case-study
title: Building Political Metrics Without Inventing Political Meaning
permalink: /portfolio/eirepolitic/political-metrics/
presentation: editorial
kicker: Eirepolitic deep dive
summary: A metrics and context layer designed around historical correctness, conservative joins, explicit denominators, and auditable public claims.
tags:
  - Analytics
  - Data Modelling
  - Validation
---

<section class="case-study-section case-study-two-column">
  <div>
    <p class="editorial-kicker">The problem</p>
    <h2>Political data is easy to count and easy to misinterpret.</h2>
  </div>
  <div>
    <p>A raw count of speeches, votes or questions can look objective while still being wrong in context. A TD may have changed party, moved constituency, entered or left the Dáil, or been ineligible for the event being measured. A debate may mention a Bill without every speech in that debate actually belonging to the Bill discussion.</p>
    <p>I built the political-metrics layer to make those assumptions explicit before they reach a chart, post or dashboard.</p>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">1 · Historical correctness</p>
  <h2>Use the political context that was true on the event date.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>Party and constituency attribution is resolved historically, not from a person's current profile. Every event is evaluated against the membership and affiliation ranges that were valid on that date.</p>
      <p>The model uses start-inclusive, end-exclusive date ranges so same-day transitions can be represented without double-counting. If source history contains a true overlap, validation fails instead of silently choosing one row.</p>
    </div>
    <div class="model-stack">
      <div><strong>Event date</strong><span>speech · vote · question</span></div>
      <div><strong>Active Dáil membership</strong><span>was this person eligible on that date?</span></div>
      <div><strong>Historical affiliation</strong><span>party and constituency valid at that moment</span></div>
      <div><strong>Metric population</strong><span>include only rows that satisfy the metric contract</span></div>
    </div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">2 · Parliamentary context</p>
  <h2>Prefer deterministic source evidence to semantic guessing.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>The broader speech-context layer classifies parliamentary context from explicit Oireachtas structure: Oral Questions, Bill or legislation sections, Leaders' Questions, statements, procedural business, motion proceedings, or an explicit <code>other</code> fallback.</p>
      <p>No model is used to fill the remaining <code>other</code> category. The goal here is not maximum coverage at any cost; it is reliable context that can be explained and reproduced.</p>
    </div>
    <div class="eirepolitic-tech-note"><strong>Production snapshot</strong><span>66,192 speeches · 53,452 deterministically contextualised · ~80.75% non-other coverage</span></div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">3 · Certified legislation joins</p>
  <h2>Link speeches and votes to Bills only when the section evidence agrees.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>A whole debate cannot safely be labelled as Bill-related just because one Bill appears somewhere inside it. The production bridge resolves Bill context at exact debate-section grain and requires multiple source checks to agree before emitting a relationship.</p>
      <p>Conflicts, multi-Bill sections and unresolved cases are excluded rather than guessed. Duplicate source records are collapsed so they cannot multiply downstream speeches or divisions.</p>
    </div>
    <div class="publishing-stack">
      <div><strong>Bill source record</strong><span>source section + heading</span></div>
      <b>↓</b>
      <div><strong>Canonical debate section</strong><span>exact composite section match</span></div>
      <b>↓</b>
      <div><strong>Certified Bill-section bridge</strong><span>one Bill per accepted section</span></div>
      <b>↓</b>
      <div><strong>Safe downstream joins</strong><span>speeches and divisions without row multiplication</span></div>
    </div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">Production footprint</p>
  <h2>Conservative joins still produce useful coverage.</h2>
  <div class="capability-grid">
    <div><strong>168 Bills</strong><span>distinct Bills in the certified production bridge</span></div>
    <div><strong>371 sections</strong><span>exact canonical debate sections linked to Bills</span></div>
    <div><strong>7,352 speeches</strong><span>linked through exact debate-section membership</span></div>
    <div><strong>168 divisions</strong><span>linked through exact debate-section membership</span></div>
    <div><strong>0 guessed conflicts</strong><span>ambiguous and multi-Bill cases are left unresolved</span></div>
    <div><strong>1 row per source speech</strong><span>speech-context output is audited for complete one-to-one coverage</span></div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">4 · Denominators matter</p>
  <h2>The denominator is part of the metric, not a footnote.</h2>
  <div class="cost-control-grid">
    <div><strong>Speech activity</strong><span>can use authoritative debate days rather than only days with speech rows</span></div>
    <div><strong>Voting participation</strong><span>uses eligible divisions during active Dáil membership</span></div>
    <div><strong>Issue share</strong><span>excludes <code>NONE</code> from policy-share denominators</span></div>
    <div><strong>Monthly results</strong><span>publish completed calendar months only, not partial months beside full ones</span></div>
  </div>
  <p>A missing recorded vote is therefore described as a missing recorded vote—not proof that somebody was physically absent. Similarly, an eligible debate day is not treated as attendance evidence.</p>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">5 · Reliability rules</p>
  <h2>Some numbers should not be compared yet.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>Metrics can carry reliability and public-use status alongside the value itself. Party voting unity, for example, is not presented identically regardless of sample size: fewer than five qualifying divisions is insufficient for comparison, five to nine carries caution, and ten or more is considered reliable.</p>
      <p>The same philosophy applies elsewhere. If the source data cannot support a defensible denominator or interpretation, the metric is deferred rather than forced into existence.</p>
    </div>
    <div class="safety-mode-grid">
      <div><strong>Reliable</strong><span>enough qualifying observations for public comparison</span></div>
      <div><strong>Caution</strong><span>usable with an explicit reliability warning</span></div>
      <div><strong>Insufficient</strong><span>do not present as a meaningful comparison</span></div>
    </div>
  </div>
</section>

<section class="case-study-section">
  <p class="editorial-kicker">6 · Materialisation</p>
  <h2>Precompute additive foundations, not fragile final percentages.</h2>
  <div class="case-study-two-column compact-gap">
    <div>
      <p>The metrics layer stores daily or event-level additive components that can be recombined for different date ranges. That avoids rescanning raw source facts for every request and, importantly, avoids averaging percentages that were calculated with different denominators.</p>
      <p>Completed-month consumer results are then materialised into the same immutable candidate batch as the canonical data that produced them. They cannot update the production pointer directly.</p>
    </div>
    <div class="model-stack">
      <div><strong>Canonical batch</strong><span>source of truth for the candidate</span></div>
      <div><strong>Daily/event components</strong><span>additive metric foundations</span></div>
      <div><strong>Completed-month results</strong><span>consumer-friendly metric rows</span></div>
      <div><strong>Candidate validation</strong><span>all required metric datasets present before promotion</span></div>
    </div>
  </div>
</section>

<section class="case-study-section case-study-two-column">
  <div>
    <p class="editorial-kicker">What I learned</p>
    <h2>The most important analytics work often happens before the calculation.</h2>
  </div>
  <div>
    <p>The difficult part was rarely writing a formula. It was deciding which population was valid, which historical relationship applied, what source evidence was strong enough to join, and what the result should explicitly not claim.</p>
    <p>That discipline makes the output less flashy in places—but far more defensible.</p>
  </div>
</section>

<section class="case-study-section technical-links-section">
  <p class="editorial-kicker">Go deeper</p>
  <h2>Canonical technical documentation</h2>
  <div class="technical-link-grid">
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/political_metrics_foundation.md"><strong>Political metrics foundation</strong><span>Metric definitions, denominators, historical attribution and materialisation design</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/research/speech_context_implementation.md"><strong>Speech-context implementation</strong><span>Deterministic context rules, production footprint and audit behaviour</span></a>
    <a href="https://github.com/warrengleeson/eirepolitic-data-pipeline/blob/main/docs/research/legislation_bridge_implementation.md"><strong>Certified legislation bridge</strong><span>Exact Bill-section relationships and rejected unsafe joins</span></a>
    <a href="{{ '/portfolio/eirepolitic/' | relative_url }}"><strong>Back to Eirepolitic</strong><span>Return to the end-to-end project case study</span></a>
  </div>
</section>
