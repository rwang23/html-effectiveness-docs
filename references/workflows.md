# Workflows

Follow this workflow for project documentation work:

```text
1. Context Scan
2. Route
3. Artifact Plan
4. Create or Update Work Interface
5. Extract Decisions
6. Sync Markdown Source of Truth
7. Verify
8. Report
```

## 1. Context Scan

Inspect relevant local context before writing:

- `AGENTS.md` or `agents.md`
- `README*`
- `docs/`
- `context/`
- existing plans, reports, changelogs, task lists, memory files, and handoff docs
- code structure, design tokens, or recent diffs when relevant

State material assumptions briefly when local structure is missing.

## 2. Route

Choose one intent from `routing.md`. If multiple intents apply, choose the primary user outcome and mention secondary sync work.

Use `docs-organization` when the user asks to clean up, organize, archive, consolidate, rename, move, or delete documentation.

## 3. Artifact Plan

Before creating a substantial artifact, identify:

- reader
- decision or action enabled by the artifact
- output format
- output path
- Markdown sync target
- verification method
- richness contract for HTML artifacts: what the reader can compare, click, expand, filter, inspect, or export

## 4. Create or Update Work Interface

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

## 5. Extract Decisions

Extract selected options, risks, tasks, architecture facts, preferences, open questions, and verification results.

## 6. Sync Markdown Source of Truth

Use `markdown-sync.md` to choose durable targets. Do not duplicate large HTML content into Markdown; sync conclusions and references.

## 7. Verify

Check file existence, readability, internal consistency, and interactive behavior when present.

## 8. Report

Final response must include:

- created or updated artifact paths
- Markdown files synchronized
- verification performed
- unresolved decisions or residual risk
