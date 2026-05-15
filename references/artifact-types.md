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
