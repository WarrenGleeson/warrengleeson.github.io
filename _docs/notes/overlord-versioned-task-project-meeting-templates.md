---
title: Overlord Legacy Versioned Task, Project, and Meeting Templates
summary: Historical 2026-08-07 reference for the pre-Phase-0 Overlord v1 Markdown templates; later documentation records describe a replacement application while retaining these fixtures as legacy material.
section: notes
doc_type: reference
status: active
owner: High Director
created: 2026-08-07
updated: 2026-11-17
repository: Overlord
---

# Overlord Legacy Versioned Task, Project, and Meeting Templates

> **Historical snapshot:** This page records the repository state inspected on 2026-08-07. It is not evidence that these files remain the current Overlord implementation. The current site checkout does not contain the Overlord source tree needed to verify their present status. See [Overlord Evidence Gaps and Blind Spots](overlord-blind-spots.md).

## Purpose

The 2026-08-07 Overlord snapshot contained three versioned Markdown skeletons intended to represent task, project, and meeting record types.

Files in that snapshot:

- `templates/tasks/task_v1.md`;
- `templates/tasks/project_v1.md`;
- `templates/tasks/meeting_v1.md`.

All three files had the same Git blob SHA and the same content. Their filenames distinguished intended template type; their body structure did not.

## Snapshot template content

Each v1 template contains exactly these headings:

```text
## Overview

## Notes

## Next Actions

## Open Questions

## Changelog
```

No front matter, placeholder values, instructions, comments, or type-specific sections are present in the template files themselves.

## Snapshot naming convention

Observed filenames use:

`{template_type}_v{version}.md`

Current examples:

- `task_v1.md`;
- `project_v1.md`;
- `meeting_v1.md`.

This indicated a versioned-template naming convention with snapshot version `v1`.

No source code defines filename parsing, semantic-version rules, upgrade behavior, or the next permitted version. Treat the naming convention as observed repository structure rather than an enforced specification.

## Snapshot template equivalence

The three v1 template files are byte-equivalent in the inspected repository and share the same Git blob SHA:

`84736e15c54ee52c00964b58e054255f02e59cc2`

Therefore, within that snapshot:

- task records do not receive task-specific body sections from the template;
- project records do not receive project-specific body sections;
- meeting records do not receive meeting-specific body sections.

The only type distinction is the selected filename and any manually supplied record metadata.

## Snapshot relationship to record front matter

Observed snapshot fixture records under `tasks/work/` included fields such as:

- `template_type: "task"`;
- `template_version: "v1"`.

This metadata can describe which logical template/version a record is associated with.

However, the snapshot template Markdown files did not provide or generate that front matter. There was no verified script in the snapshot that:

- chooses a template;
- injects metadata;
- creates a record;
- validates `template_type` against the template filename;
- validates `template_version` against an existing version;
- upgrades old records when a template changes.

The relationship is manual/conventional.

## Snapshot intended record sections

### Overview

General summary of the record's subject. Repository source does not define required content or format.

### Notes

Free-form notes. No schema or formatting rules are enforced.

### Next Actions

Free-form next-step content. No task-list syntax, ownership, due date, or completion semantics are enforced by the template.

### Open Questions

Free-form unresolved questions. No automatic resolution/lifecycle behavior exists.

### Changelog

Free-form change history. Fixtures demonstrate manually written timestamped creation entries, but the template itself does not specify a changelog line format.

## Snapshot version convention

Current evidence supports only these statements:

- filenames include `_v1`;
- fixture metadata includes `template_version: "v1"`;
- there are no `v2` or other versions in the tree.

It does **not** establish backward compatibility guarantees, migration rules, deprecation policy, immutability, or whether records should be changed when a new template version appears.

## Snapshot manual-record convention

Based on the snapshot repository structure, a manual record could follow this convention:

1. choose the intended context directory, such as `tasks/work/` or `tasks/personal/`;
2. choose a template type/version filename from `templates/tasks/`;
3. copy the five-section Markdown skeleton;
4. add record front matter consistent with observed fixtures;
5. set `template_type` and `template_version` to describe the chosen template;
6. populate the body sections;
7. maintain status/timestamps/changelog manually.

These steps described the snapshot convention, not an automated workflow.

## Snapshot type-specific behavior

There is currently no verified type-specific behavior for `task`, `project`, or `meeting` templates. No source defines project milestones, project child tasks, meeting attendees, meeting agenda/minutes fields, task due dates/priorities, or different lifecycle rules by template type.

Do not infer those features from the template names.

## Change-control implications

Because records store `template_version`, maintainers can theoretically preserve which version a record used. But without generators, validators, or migrations, changing a template does not automatically update existing records.

If a future `v2` is introduced, its behavior should be documented from the new source files and any explicit repository standard rather than inferred from the current v1 convention.

## Failure/data-quality modes

- `template_type` does not correspond to an existing template file;
- `template_version` does not correspond to an existing version;
- copied record body drifts from the template sections;
- type/version metadata is omitted or mistyped;
- template files diverge without documentation of the semantic difference;
- an existing version changes in a way that makes historical metadata ambiguous;
- future type-specific expectations exist only as human convention.

No automated validator currently detects these conditions in `Overlord`.

## Snapshot limitations

- three logical types but currently identical body templates;
- no front matter in template files;
- no generator or scaffold command;
- no schema validation;
- no version migration mechanism;
- no type-specific required fields or sections;
- no changelog format specification;
- no compatibility/deprecation policy;
- no automation linking fixture metadata to template files.

## Related documentation

- [Overlord Repository and Markdown Task-Record System](../repositories/overlord.md)
- [Overlord Evidence Gaps and Blind Spots](overlord-blind-spots.md)
- [Overlord Documentation Workstream Plan](../high-director/overlord-documentation-workstream-plan.md)
- [Repository Scan: Overlord](../high-director/repository-scan-overlord.md)

## Continuation

If new template versions or type-specific structures are added, document the exact new files and semantic differences. Do not describe version migration, generation, or type-specific lifecycle behavior until it is implemented or explicitly standardized in the repository.
