# Project Intelligence Artifact

This reference defines the expected product shape for the living project
intelligence file:

```text
docs/intel.html
```

This artifact is not a docs index. It is the project's inspectable intelligence
workbench. It should help a new human or agent understand the project, inspect
its structure, see current state, and decide where to act next.

## Product Goal

`docs/intel.html` should answer, without requiring other files first:

- What is this project?
- Who is it for?
- What does it do?
- How is it structured?
- What stack does it use?
- What workflows matter?
- What is currently working or blocked?
- What are the top risks?
- Which docs are authoritative?
- Where is the evidence?

## Required First Screen

The first screen should include:

- project name and one-sentence brief
- primary user or actor
- core product/workflow
- current project stage or release posture
- system shape summary
- tech stack summary
- top risks or next decisions
- drilldown navigation for overview, architecture, stack, docs, risks, tasks, and evidence

If the first screen looks like an index, metrics board, or welcome page, it is
not sufficient.

## Required Views

Use tabs, anchors, segmented controls, clickable cards, or a detail pane. The
artifact should include these views when evidence exists:

### Overview

- project brief
- domain model
- main users or actors
- primary workflows
- current stage
- recent notable changes

### Architecture

- system shape map
- modules/packages/apps
- routes/API handlers
- workers/jobs/queues
- database/schema boundaries
- external integrations
- hot paths and ownership boundaries

### Stack

- frontend
- backend
- runtime
- database/storage
- auth/session
- jobs/queues/cron
- deployment/hosting
- tests/tooling
- external SDKs/APIs

Each stack item should include evidence paths when practical.

### Docs

- source-of-truth map
- authoritative docs
- historical docs
- reports/plans
- raw evidence
- generated artifacts
- stale, duplicate, or contradictory docs

### Risks

- risk name
- severity
- affected surface
- evidence
- mitigation
- owner or next actor
- verification method

### Tasks

- prioritized next actions
- release gates
- cleanup work
- verification tasks
- link to source files or docs

### Evidence

- file paths
- short snippets or summarized proof
- command outputs when available
- docs/code mismatches
- areas not inspected

## Project Evidence Requirements

`docs/intel.html` should be grounded in:

- docs and README
- code tree and module boundaries
- package/config/runtime files
- routes, handlers, workers, services, schemas, and tests
- deployment and environment files
- scripts and smoke commands
- external integration signals
- recent git history when useful and available

If the artifact is generated from docs only, mark it as docs-only and explain
that code/config/runtime evidence was not inspected.

## Interaction Requirements

Include local interaction when useful:

- tabs or anchor navigation for major views
- filters for docs, files, risks, or tasks
- expandable evidence drawers
- clickable architecture nodes or cards
- copyable next-agent brief
- export block with Markdown handoff

Do not require the reader to open many separate files just to understand the
basic project state.

## Maintenance Rules

When project structure, stack, workflows, release state, risks, or
source-of-truth docs change, update `docs/intel.html` in the same work session.

When creating or updating it, register it in `AGENTS.md`, `agents.md`,
`CLAUDE.md`, or `claude.md` when such a file exists.

## Failure Modes

The artifact fails if:

- it is only a docs index
- it lacks project background
- it lacks code/config/runtime evidence when those files exist
- it does not show system structure
- it does not show the stack
- it does not show current state or risks
- it has no useful drilldown
- it has no export or handoff path
