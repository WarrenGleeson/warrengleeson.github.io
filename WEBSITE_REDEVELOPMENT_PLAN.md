# Website Redevelopment Plan

Status: Planning approved; implementation not yet approved

Repository: `warrengleeson.github.io`

## Purpose

Redevelop the site into a combined personal/project portfolio, technical documentation website, and public presentation layer for selected repository documentation.

Repository documentation remains canonical. The website is an aggregation and presentation layer and should not become a competing source of truth.

## Agreed Site Direction

### Identity and audience

- Primary identity: Warren Gleeson.
- Professional title: **Data Engineer & Analyst**.
- Primary audience: potential employers and technical peers.
- Homepage emphasis: portfolio-first.
- Eirepolitic is presented as a project/brand, not as the site's primary identity.

### Top-level navigation

- Home
- Portfolio
- Documentation
- CV

No separate About page is required; personal/professional introduction belongs on the homepage.

### Visual direction

- Main Warren Gleeson site: light, editorial, modern, restrained.
- Portfolio pages: spacious, visual, narrative-led, with large screenshots/diagrams and short text sections.
- Technical documentation: denser, classic documentation layout with persistent left navigation and documentation-only search.
- Eirepolitic branding must remain contained within Eirepolitic portfolio pages and must not define the general site visual identity.

## Homepage

The homepage should contain:

1. Professional photo.
2. Warren Gleeson name and **Data Engineer & Analyst** title.
3. Short builder-focused introduction.
4. Featured Eirepolitic Data Pipeline case study.
5. Smaller selected-work cards.
6. CV and contact links.

Do not add a generic skills/tooling strip. Skills should be demonstrated through project work and the CV.

Contact presentation should be minimal: GitHub, LinkedIn, email, and CV.

## Portfolio

### Landing page

Use a portfolio grid with:

- Eirepolitic Data Pipeline as the prominent featured project.
- Smaller cards for additional projects, technical case studies, and selected articles.
- Lightweight category tags such as Data Engineering, Automation, Analytics, and Case Study.
- No filtering or complex taxonomy initially.

Only projects with substantial completed work should appear publicly. Overlord is excluded from the portfolio for now and may be added later when there is a finished framework plus meaningful completed work to discuss.

### Content types

Portfolio content may include:

- Flagship projects with full overview pages and multiple deep dives.
- Technical case studies such as AutoDoc.
- Custom articles about completed work that is not represented fully in a repository.

## Eirepolitic Data Pipeline Flagship Case Study

Positioning:

> Eirepolitic — an end-to-end political data, analysis and automated publishing platform.

The page should primarily demonstrate engineering capability. It should explain the complete system before drilling into technical details.

### End-to-end narrative

The flagship flow should cover:

1. Source systems and data providers.
2. Ingestion and processing.
3. Canonical stored data model.
4. Classification and enrichment.
5. Analysis and political metrics.
6. Visual/content generation and review.
7. Scheduling and automated Instagram publishing.

Known source examples should be named where they are genuinely used, including Oireachtas data/API and Irish Polling Indicator data.

The canonical stored data model should be treated as its own important stage because downstream processing depends on it.

### Infrastructure and tooling presentation

Show major technology choices in context rather than as a generic badge wall.

High-level diagrams may label tools/services such as:

- Python
- APIs
- AWS S3
- AWS Lambda
- DynamoDB
- EventBridge Scheduler
- LLM-based classification components
- rendering/content-generation tooling
- Meta/Instagram publishing

Use clean text labels primarily. Logos should be used sparingly.

### Deep-dive pages

Portfolio deep dives remain presentation content, not operational documentation. They should be understandable to less-technical readers while retaining enough substance for technical peers.

Preferred narrative structure:

1. Problem
2. Approach
3. Key design choices
4. Result
5. Visual examples
6. Links to canonical technical documentation

Initial candidate deep dives:

- LLM issue classification
- Parliamentary data / political metrics
- Instagram content factory
- Automated publishing system

The flagship page should use only a light first-person voice. Deep dives may use a stronger first-person case-study voice.

## Documentation

### Structure

Organize public documentation primarily by repository/project rather than by broad cross-project topics.

Repository documentation remains the source of truth. The website should render approved documentation as a public representation and clearly associate pages with their source repository.

A short synchronization lag between repository changes and the public site is acceptable.

### Navigation

Use a classic technical documentation layout:

- persistent left sidebar
- dense information hierarchy
- main content area
- documentation-only search

Do not make portfolio content part of technical search.

### Publication model

Initial publishing may be manual/controlled. Future automation may use metadata such as `project.yaml`, including separate publication controls for technical documentation and portfolio content.

Do not build automated enforcement/publishing until separately approved.

## CV

Create:

- a web CV page;
- a downloadable PDF CV.

The existing CV should be used as the initial factual/template source when supplied, then updated with current experience and selected project/repository references.

The web CV may be richer than the PDF. The PDF should remain concise enough for job applications.

## Images, Screenshots and Diagrams

Portfolio pages should use real screenshots/output examples wherever practical.

During initial development:

- use purpose-built screenshot placeholders with fixed aspect ratios;
- assign each required screenshot a stable filename;
- design layouts around the intended final image rather than generic grey boxes.

Create a temporary, unlisted screenshot-capture article containing a simple table with:

- screenshot filename;
- description of exactly what should be captured.

The page should be accessible by direct URL but excluded from normal navigation. It can be removed once all final screenshots have been supplied and installed.

Diagrams should be decided case by case. Architecture/data-flow diagrams should preferably be manually rendered or generated from structured markup/SVG when that improves clarity and maintainability.

## Preservation and Safety Rules

- Preserve existing working systems and URLs where practical.
- Do not redesign repositories, pipelines, AWS resources, deployments, integrations, or working infrastructure merely to support the website.
- Existing AWS/resource names containing `eirepolitic` remain intentionally unchanged.
- Private repositories remain private unless sanitized publication is explicitly approved.
- Portfolio publication and documentation publication are separate decisions.
- Do not expose secrets or private operational information.
- Do not duplicate operational runbooks into the public portfolio.
- Repository-owned documentation remains canonical.

## Proposed Implementation Stages

No implementation stage begins without approval of this plan.

### Stage 1 — Foundation and information architecture

- Establish the new top-level navigation and page structure.
- Preserve existing documentation behavior while separating portfolio and documentation presentation modes.
- Create base layout/style primitives for light editorial portfolio pages and dense technical documentation pages.
- Add placeholder routes/pages only; avoid major public content rewrites.
- Run existing repository/site checks.

Approval gate: confirm navigation, homepage wireframe, portfolio grid, and documentation layout before proceeding.

### Stage 2 — Homepage and portfolio framework

- Build the new homepage shell.
- Build portfolio landing-page grid.
- Add Eirepolitic featured-project shell.
- Add reusable case-study/deep-dive layout.
- Add screenshot placeholders and begin the screenshot-capture checklist.

Approval gate: confirm visual direction and portfolio presentation before adding substantial project content.

### Stage 3 — Eirepolitic flagship case study

- Build the end-to-end Eirepolitic narrative.
- Create high-level system/data-flow diagrams.
- Add source, canonical data-model, classification, metrics, content-generation, review, scheduling, and publishing sections.
- Add technology labels in context.
- Add links to relevant canonical documentation.

Approval gate: confirm public wording, architecture visuals, and technical depth.

### Stage 4 — Eirepolitic deep dives

Create the first set of non-technical-friendly case studies, starting with the strongest available implemented components. Candidate order:

1. LLM issue classification
2. Parliamentary data / political metrics
3. Instagram content factory
4. Automated publishing

Each deep dive should be reviewed for public-safety/privacy concerns before publication.

### Stage 5 — Documentation reorganization

- Reorganize the public documentation experience around repository/project ownership.
- Preserve canonical repository ownership and source links.
- Keep the dense left-sidebar layout.
- Keep search limited to documentation.
- Avoid duplicating runbooks or maintaining rewritten competing copies.

Approval gate: confirm the public documentation hierarchy before broad migration/relinking.

### Stage 6 — CV

- Add web CV page.
- Update content from the supplied existing CV.
- Add project links where useful.
- Produce a concise downloadable PDF version.

Approval gate: confirm CV content before publication.

### Stage 7 — Additional portfolio content

Add items individually when they have sufficient material, for example:

- AutoDoc case study
- custom technical articles
- later Overlord work once sufficiently complete

Each new portfolio item requires a separate publication/content decision.

### Stage 8 — Screenshot replacement and polish

- Use the temporary capture checklist for a dedicated screenshot session.
- Replace placeholders with supplied images.
- Verify responsive crops and captions.
- Final accessibility, link, and navigation pass.
- Remove the temporary screenshot-capture article when no longer needed.

### Stage 9 — Future automation (separate project)

Potential later work may include:

- using `project.yaml` to discover public projects;
- controlled repository-document synchronization;
- publication metadata enforcement;
- automated portfolio/documentation indexes.

This is explicitly out of scope for the initial redevelopment unless separately approved.

## Change Process

Implementation should use branches and pull requests. Changes should be incremental and reversible. Existing checks should run before merge. Material changes to site structure, visual direction, public content, portfolio positioning, or publication of private-project information require explicit approval before merge.
