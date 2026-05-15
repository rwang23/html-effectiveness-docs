# Project Intelligence

Use this reference for project-level HTML artifacts such as `docs-dashboard.html`,
`architecture-map.html`, `handoff` artifacts, and `docs-organization-workbench.html`.

The default living artifact path for project intelligence is:

```text
docs/intel.html
```

Use this as the project-level HTML entrypoint unless project-local rules choose a different path.

Project-level artifacts must not rely only on existing documentation unless the
user explicitly asks for a docs-only view. Documentation is one signal. Code,
configuration, runtime files, tests, scripts, generated artifacts, and recent
changes are also first-class evidence.

## Required Output

Create a Project Intelligence Packet before writing the HTML artifact.

The packet is a compact model of the project:

- project brief: what the project is, who it serves, what problem it solves, and current stage
- domain model: core users, business objects, workflows, and lifecycle states
- system shape: apps, packages, modules, workers, services, databases, queues, APIs, and integrations
- tech stack: frontend, backend, runtime, database, auth, jobs, deployment, testing, tooling, and external SDKs
- operational state: what works, what is blocked, current release gates, and recent completed work
- risk surface: fragile modules, stale docs, duplicate source-of-truth, unverified assumptions, and external dependencies
- source-of-truth map: authoritative docs, historical docs, reports, raw evidence, generated artifacts, and handoff docs
- evidence pointers: file paths, code/config snippets, summarized proof, or command outputs that support the claims

## Required Inputs

Inspect the relevant subset of these sources. Use project-local instructions to
scope the scan. Do not read every file blindly when targeted search is enough.

### Documentation Sources

- `AGENTS.md` or `agents.md`
- `README*`
- `docs/`
- `context/`
- plans, reports, changelogs, task lists, memory files, handoff docs, and existing HTML artifacts

### Code Structure Sources

- top-level directories
- app/package/module boundaries
- entry points
- routes
- API handlers
- workers and jobs
- services, libs, hooks, components, and utilities
- tests and fixtures

### Config and Runtime Sources

- package manifests and lockfiles
- framework config
- build config
- deployment config
- environment examples
- database schemas and migrations
- queue, worker, cron, or scheduler config
- CI config
- scripts and smoke commands

### Behavior Evidence

- tests
- scripts
- smoke outputs
- recent git diff or log when available
- generated reports
- existing artifacts

### External Integration Signals

- SDK imports and client wrappers
- webhook handlers
- auth/session code
- API route naming
- env var names
- deployment/runtime adapters

## Extraction Workflow

1. Start with local rules and README to infer stated purpose.
2. Inspect top-level file tree to identify actual structure.
3. Read manifests/config to identify stack and runtime.
4. Search for routes, handlers, workers, jobs, schemas, external SDKs, and tests.
5. Compare code evidence with docs. Mark mismatches instead of smoothing them over.
6. Build the Project Intelligence Packet.
7. Use the packet to design the HTML first screen and drilldown layers.
8. Write or update the living project intelligence artifact at `docs/intel.html`.
9. Register `docs/intel.html` in `AGENTS.md`, `agents.md`, `CLAUDE.md`, or `claude.md` when an instruction file exists.
10. Sync durable conclusions back to Markdown only when they are accepted or useful as project memory.

## First Screen Intelligence Standard

Within the first screen, a new reader should understand:

- what the project is
- who it is for
- the primary workflow or product surface
- the major system parts
- the core tech stack
- current implementation/release state
- the top risks or next decisions
- where to click for architecture, docs, tasks, risks, evidence, and handoff detail

If the first screen only shows a title, metrics, and links, the artifact is too shallow.

## Drilldown Detail Standard

Project-level artifacts should include local drilldowns. Use tabs, anchors,
expandable panels, clickable cards, filters, or detail panes.

Required drilldown categories for non-trivial project artifacts:

- overview: project brief and current state
- architecture: system shape, module map, request/job flow, or service boundaries
- stack: technologies with evidence paths
- docs: source-of-truth map and documentation gaps
- risks: risk surface with impact, evidence, and next action
- tasks: prioritized follow-up work
- evidence: file paths, snippets, command outputs, or summarized proof

Use at least four categories when the project has enough evidence. If a category
is omitted, explain why in the artifact or final report.

## Evidence Rules

- Prefer concrete file paths over generic claims.
- Prefer short excerpts or summarized proof over large copied blocks.
- Mark inferred facts as inferred.
- If docs and code disagree, show the disagreement.
- If the scan is incomplete, say what was not inspected.

## What Not To Do

- Do not produce a docs-only index for a project-level artifact unless the user asked for docs-only.
- Do not infer the stack only from README when package/config files are available.
- Do not present generated docs as source-of-truth without checking whether code agrees.
- Do not hide current state, risks, or uncertainty behind a polished layout.
- Do not leave `docs/intel.html` unreferenced in project agent instructions when an instruction file exists.
