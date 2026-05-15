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

- document inventory
- coverage map
- missing documents
- stale or contradictory docs
- duplicate content
- recommended task-list updates

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
