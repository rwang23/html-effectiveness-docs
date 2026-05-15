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

## 3. Artifact Plan

Before creating a substantial artifact, identify:

- reader
- decision or action enabled by the artifact
- output format
- output path
- Markdown sync target
- verification method

## 4. Create or Update Work Interface

Create the smallest useful artifact. Keep it structured, readable, and directly useful.

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
