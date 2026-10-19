# warrengleeson.github.io Director Pack

## System

`warrengleeson.github.io` is the public documentation and presentation layer for WarrenGleeson repositories and projects.

## Existing capabilities

- Public documentation site built from repository content.
- Project and system documentation under `_docs/`.
- Site configuration in `_config.yml`.
- Existing documentation governance and publishing process files.

## Operating model

This site is not the canonical source for repository-owned operational documentation.

Repository documentation is canonical for durable project knowledge. This site should summarize, publish, or link to that material without creating a competing source of truth.

## Authoritative state

- Repository/project documentation: the corresponding source repository.
- Repository Standard V1 and documentation governance: `General_Director`.
- Site layout/navigation/presentation: this repository.
- Published site state: live GitHub Pages deployment.

If site content conflicts with source-repository documentation, update the site to match the source repository rather than editing the source repository solely to fit the site.

## Documentation pointers

- Site overview: `README.md`
- Site process: `PROCESS.md`
- Legacy/local documentation standard: `DOCUMENTATION_STANDARD.md`
- Published content: `_docs/`
- Site config: `_config.yml`

## Do not rebuild

- Do not duplicate repository runbooks or operational docs when a stable source-repository document exists.
- Do not move canonical repository documentation into this site.
- Preserve stable public URLs where practical during cleanup.
- Do not delete legacy documentation in bulk without reviewing whether it still provides historical value.

## Operational warnings

- This is a public repository and public website.
- Do not publish private-repository details unless explicitly approved and sanitized.
- Do not expose secrets, credentials, private infrastructure details, or sensitive operational information.

## Standard deviations

This repository is a documentation aggregation layer, so it may retain generated or presentation-specific copies of source material where needed for GitHub Pages. Those copies are not canonical.

## Continuation

- Outstanding work: reduce duplicated repository documentation and replace stale migration-era references with links to current source repositories.
- Next safe action: update site governance and project pages incrementally while preserving working URLs.
