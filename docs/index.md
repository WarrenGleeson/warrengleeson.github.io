---
layout: docs
title: Documentation
summary: Technical documentation organized first by public project, with repository-owned documentation remaining canonical.
permalink: /docs/
---

<section class="docs-projects-section" aria-labelledby="docs-projects-title">
  <h2 id="docs-projects-title">Projects</h2>
  <p>Start with a project to understand its architecture, implementation, and related technical documentation.</p>

  <div class="docs-project-grid">
  {% assign projects = site.data.docs_projects | sort: 'order' %}
  {% for project in projects %}
    <article>
      <h3><a href="{{ project.overview_url | relative_url }}">{{ project.title }}</a></h3>
      <p>{{ project.description }}</p>
      <div class="docs-project-links">
        <a href="{{ project.overview_url | relative_url }}">Project documentation</a>
        <a href="{{ project.source_url }}">Source repository</a>
      </div>
    </article>
  {% endfor %}
  </div>
</section>

<section class="docs-reference-section" aria-labelledby="docs-reference-title">
  <h2 id="docs-reference-title">Reference library</h2>
  <p>The existing topic indexes remain available for cross-project reference and historical material. Existing document URLs are unchanged.</p>

  <div class="docs-section-grid">
  {% assign sections = site.data.docs_sections | sort: 'order' %}
  {% for section in sections %}
    {% assign section_docs = site.docs | where: 'section', section.id %}
    <section>
      <h3><a href="{{ '/docs/' | append: section.id | append: '/' | relative_url }}">{{ section.title }}</a></h3>
      <p>{{ section.description }}</p>
      <small>{{ section_docs.size }} document{% unless section_docs.size == 1 %}s{% endunless %}</small>
    </section>
  {% endfor %}
  </div>
</section>
