# Artifact Types

Final HTML artifacts default to `docs/effectiveness-artifact/`.

Temporary explorations default to `context/raw/` when the project uses `context/`.

## exploration-matrix.html

Use for comparing approaches.

Required sections:

- problem statement
- options side by side
- tradeoffs
- cost and complexity
- risk
- recommendation
- decision summary for export

## implementation-plan.html

Use for implementer handoff.

Required sections:

- goal and non-goals
- milestones
- data flow
- affected files or packages
- key code snippets or APIs
- risks and mitigations
- open questions
- verification plan

## architecture-map.html

Use for system understanding.

Required sections:

- module map
- entry points
- data flow
- hot paths
- ownership or boundaries
- common modification points
- durable architecture summary

## design-reference.html

Use for design systems and component reviews.

Required sections:

- tokens
- colors
- typography
- spacing
- components
- variants
- states
- copyable references

## docs-dashboard.html

Use for documentation audits.

Required sections:

- source-of-truth map that shows which docs are authoritative, historical, raw evidence, or generated output
- document relationship view, not just a flat list; show how README, plans, reports, memory, architecture docs, and artifacts connect
- coverage map with gaps, stale areas, contradictions, and duplicated responsibilities
- prioritized cleanup board with impact, owner or next actor, target file, and verification method
- drill-down views for important document groups, using tabs, filters, collapsible sections, or clickable cards
- evidence excerpts for major findings, including short quoted snippets or summarized proof with file paths
- before/after or desired-state model when the audit recommends a reorganization
- recommended task-list updates
- export block with Markdown follow-up tasks and source-of-truth decisions

Minimum interaction:

- filter or focus control for document groups
- clickable anchors or tabs for at least the major categories
- expandable evidence or detail sections for important findings

Avoid:

- a dashboard that is only a metrics strip plus link index
- a table that lists files without explaining relationships, conflicts, or next actions
- links that replace analysis; the artifact should make the structure observable before the reader opens another file

## docs-organization-workbench.html

Use for organizing messy documentation sets.

This artifact is allowed to propose file moves, renames, archive actions, and delete candidates. It must not execute them by default.

Required sections:

- current document topology, grouped by source-of-truth, active plans, reports, generated artifacts, raw evidence, historical docs, and duplicates
- desired document topology with proposed target paths
- action board grouped by keep, merge, move, rename, archive, and delete candidate
- reference impact analysis for every move, rename, archive, or delete candidate
- link rewrite plan that lists every file that references the old path and the exact new target or mitigation
- risk table for broken links, lost context, duplicated source-of-truth, and historical traceability
- approval checklist separating safe metadata edits from risky filesystem changes
- verification plan for link checks, path searches, docs index updates, and source-of-truth consistency
- export block with a Markdown migration plan

Hard safety rules:

- Never delete by default. Prefer archive or historical marking unless the user explicitly asks to delete.
- Before move, rename, archive, or delete: search the whole project for references to the path, filename, title, and known aliases.
- Include references from Markdown links, HTML links, code comments, config, README files, plans, reports, and generated artifacts.
- If references exist, the plan must include link rewrites or a compatibility note before execution.
- If references cannot be updated confidently, do not execute; mark the action as blocked.
- Execution requires explicit user approval after showing the impact analysis.

## interactive-editor.html

Use when decisions are easier through interaction than prose.

Required sections:

- editable state
- controls for sorting, selecting, tuning, or filtering
- visible current state
- export Markdown, JSON, or prompt payload

## annotated-review.html

Use for PR, architecture, design, or documentation reviews.

Required sections:

- findings ordered by severity
- specific file or region references when available
- explanation of impact
- suggested fix
- remaining risk

## status-or-incident-report.html

Use for weekly updates, project reports, and incident reviews.

Required sections:

- timeline
- status or impact
- key metrics
- shipped or slipped work
- action items
- owners
