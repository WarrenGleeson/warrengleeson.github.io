---
title: warrengleeson.github.io
summary: Active GitHub Pages repository for WarrenGleeson public technical documentation and project presentation.
section: repositories
doc_type: repository
status: active
created: 2026-10-19
updated: 2026-10-19
last_verified: 2026-10-19
owner: Warren Gleeson
repository: warrengleeson.github.io
order: 10
permalink: /projects/repositories/warrengleeson-github-io/
technologies:
  - GitHub Pages
  - Jekyll
  - Markdown
  - GitHub Actions
related:
  - /projects/repositories/eirepolitic-github-io/
---

# warrengleeson.github.io

## Summary

`warrengleeson.github.io` is the active public documentation and presentation repository.

It publishes GitHub Pages content, but repository-owned documentation remains canonical for project architecture, operations, and development guidance.

## Source of truth

- Site implementation, navigation, layouts, and publishing: this repository.
- Repository/project documentation: the corresponding source repository.
- Repository Standard V1 and documentation governance: `General_Director`.
- Live publishing state: GitHub Pages.

## Key files

- `DIRECTOR.md` — AI-agent operating guidance
- `project.yaml` — V1 project metadata
- `_config.yml` — site configuration
- `_docs/` — published documentation collection
- `DOCUMENTATION_STANDARD.md` — site-specific publication rules and pointer to the canonical standard
- `scripts/validate_docs.py` — documentation validation

## Publishing model

The site should summarize, render, or link to repository-owned documentation without becoming a competing source of truth.

Private-repository details must not be published unless explicitly approved and sanitized.

## Migration state

The former `eirepolitic.github.io` repository is retained as legacy/reference material. New site work belongs here.
