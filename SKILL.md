---
name: html-effectiveness-docs
description: >
  Use when project documentation would benefit from high-signal HTML work interfaces plus Markdown source-of-truth sync.
  Helps create exploration matrices, implementation plans, architecture maps, design references, docs dashboards,
  annotated reviews, reports, handoffs, and interactive editors. Use for project docs, implementation docs,
  design docs, architecture docs, documentation audits, and agent handoff materials.
triggers:
  - docs
  - documentation
  - project docs
  - implementation plan
  - architecture map
  - design system
  - docs audit
  - handoff
  - HTML artifact
  - effectiveness artifact
---

# html-effectiveness-docs

Use this skill to turn project documentation work into a strong dual-track output:

```text
HTML artifact = work interface for exploration, comparison, review, interaction, and handoff
Markdown docs = durable source of truth for decisions, tasks, architecture, memory, and project state
```

## Required First Moves

1. Inspect project-local instructions first: `AGENTS.md`, `agents.md`, README files, `docs/`, and `context/` when present.
2. For project-level artifacts, inspect code, config, runtime, tests, scripts, and external integration signals unless the user explicitly asks for docs-only.
3. Route the request before producing output.
4. Decide whether the task needs Markdown, HTML, or both.
5. If an HTML artifact produces decisions, risks, tasks, architecture facts, preferences, or verification results, sync those conclusions into Markdown.
6. Verify artifacts and docs before claiming completion.

## Routing

Read `references/routing.md` to classify the request into one of these intents:

- `exploration`
- `implementation-plan`
- `architecture-map`
- `design-system`
- `docs-audit`
- `docs-organization`
- `project-intelligence`
- `handoff`
- `review`
- `report`
- `interactive-editor`

## Workflow

Read `references/workflows.md` and follow:

```text
Context Scan -> Route -> Extract Project Intelligence when needed -> Artifact Plan -> Create or Update Work Interface -> Extract Decisions -> Sync Markdown -> Verify -> Report
```

## Artifact Types

Read `references/artifact-types.md` before creating HTML artifacts.

For project-level artifacts, read `references/project-intelligence.md` before writing the HTML.

Project-level intelligence HTML defaults to:

```text
docs/intel.html
```

Temporary explorations default to:

```text
context/raw/
```

Project-local rules override these defaults.

When creating or updating `docs/intel.html`, check `AGENTS.md`, `agents.md`,
`CLAUDE.md`, or `claude.md`. If one exists, add or update a reference telling
future agents to read and maintain `docs/intel.html`. If none exists, report
that the project has no agent instruction file and suggest adding one.

## Markdown Sync

Read `references/markdown-sync.md` before writing durable conclusions.

Do not leave durable project facts only inside HTML.

## Quality Bar

Read `references/quality-bar.md` before final response.

## HTML Patterns

Read `references/html-patterns.md` when creating a self-contained HTML artifact.

Prefer a single directly openable `.html` file with no build step. Use structure, comparison, navigation, copy/export affordances, and responsive layout to make the artifact useful.
