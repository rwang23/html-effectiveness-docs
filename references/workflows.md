# Workflows

Follow this workflow for project documentation work:

```text
1. Context Scan
2. Route
3. Extract Project Intelligence when project-level output is needed
4. Artifact Plan
5. Create or Update Work Interface
6. Extract Decisions
7. Sync Markdown Source of Truth
8. Verify
9. Report
```

## 1. Context Scan

Inspect relevant local context before writing:

- `AGENTS.md` or `agents.md`
- `README*`
- `docs/`
- `context/`
- existing plans, reports, changelogs, task lists, memory files, and handoff docs
- code structure, entry points, routes, API handlers, workers/jobs, services/libs, tests, and fixtures
- package manifests, lockfiles, framework config, deployment config, environment examples, database schemas, migrations, CI config, scripts, and smoke commands
- external integration signals such as SDK imports, API clients, webhook handlers, auth/session code, env var names, and runtime adapters
- recent git diff or log when relevant and available

State material assumptions briefly when local structure is missing.

## 2. Route

Choose one intent from `routing.md`. If multiple intents apply, choose the primary user outcome and mention secondary sync work.

Use `docs-organization` when the user asks to clean up, organize, archive, consolidate, rename, move, or delete documentation.

Use `project-intelligence` for project-level orientation, repo understanding, project dashboards, architecture dashboards, rich docs dashboards, and handoffs that need project background, structure, stack, current state, and evidence.

## 3. Extract Project Intelligence

For project-level artifacts, read `project-intelligence.md` and create a Project Intelligence Packet before writing HTML.

This is required for:

- `project-intelligence`
- `docs-dashboard`
- `architecture-map`
- `handoff`
- `docs-organization`

Skip this only when the user explicitly asks for a docs-only artifact.

The packet must include:

- project brief
- domain model
- system shape
- tech stack
- operational state
- risk surface
- source-of-truth map
- evidence pointers

Use docs as one signal, not the only signal. Compare docs against code/config/runtime evidence and mark mismatches.

## 4. Artifact Plan

Before creating a substantial artifact, identify:

- reader
- decision or action enabled by the artifact
- output format
- output path
- Markdown sync target
- verification method
- richness contract for HTML artifacts: what the reader can compare, click, expand, filter, inspect, or export
- first-screen intelligence contract: how the artifact will show project brief, structure, stack, current state, risks, and next drilldowns
- evidence contract: which code/config/docs/runtime sources support the claims
- registration contract for `docs/intel.html`: which agent instruction file references it, or why no registration was possible

## 5. Create or Update Work Interface

Create the smallest useful artifact that still behaves like a work interface.
For HTML artifacts, do not stop at an index unless the user explicitly asked for an index.

Before writing the HTML, choose at least three of these affordances when the source material supports them:

- side-by-side comparison
- diagram, map, or flow
- timeline or sequence
- drill-down tabs or anchors
- collapsible evidence
- filter or search
- annotated code, file, or document excerpts
- prioritized board or risk table
- export block for the next agent

Keep it structured, readable, and directly useful.

## Project Intelligence Registration

When producing project-level intelligence HTML, default to `docs/intel.html`.

After creating or updating it:

1. Check for `AGENTS.md`, `agents.md`, `CLAUDE.md`, and `claude.md`.
2. If any exist, add or update a short `Project Intelligence` section that references `docs/intel.html`.
3. The instruction should tell future agents to read `docs/intel.html` and update it when project structure, stack, workflows, release state, risks, or source-of-truth docs change.
4. If no instruction file exists, report that `docs/intel.html` could not be registered and suggest adding `AGENTS.md` or `CLAUDE.md`.

Do not silently create a new agent instruction file unless the user asked to initialize project instructions.

## Documentation Organization Safety

When organizing messy docs, split work into two phases:

1. Proposal phase: generate an organization workbench and Markdown migration plan.
2. Execution phase: move, rename, archive, delete, or rewrite links only after explicit user approval.

Before proposing any move, rename, archive, or delete action, perform reference impact analysis:

- search for exact paths
- search for filenames
- search for document titles
- search for common aliases or relative links
- check Markdown links, HTML links, code comments, config, README files, plans, reports, and generated artifacts

The migration plan must include:

- old path
- proposed action
- new path or archive location
- all referencing files found
- link rewrite plan
- blocked references that need manual review
- verification command or method

If references exist and no rewrite plan is available, mark the action as blocked.

Default behavior:

- keep and mark historical instead of deleting
- archive instead of deleting
- move only when references can be updated
- update docs indexes and source-of-truth notes after approved execution

## 6. Extract Decisions

Extract selected options, risks, tasks, architecture facts, preferences, open questions, and verification results.

## 7. Sync Markdown Source of Truth

Use `markdown-sync.md` to choose durable targets. Do not duplicate large HTML content into Markdown; sync conclusions and references.

## 8. Verify

Check file existence, readability, internal consistency, and interactive behavior when present.

## 9. Report

Final response must include:

- created or updated artifact paths
- Markdown files synchronized
- verification performed
- unresolved decisions or residual risk
