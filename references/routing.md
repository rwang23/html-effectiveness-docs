# Routing

Classify every request before producing documentation.

## Routing Pipeline

```text
User request
  -> Context Scan
  -> Intent Classification
  -> Artifact Decision
  -> Markdown Sync Decision
  -> Verification
```

## Intents

| Intent | Use when the user asks for | Default output |
| --- | --- | --- |
| `exploration` | Solution comparison, design directions, technical choices | HTML comparison artifact plus decision summary |
| `implementation-plan` | Implementation plan, work breakdown, developer handoff | HTML implementation plan plus Markdown plan |
| `architecture-map` | Project structure, modules, data flow, system understanding | HTML architecture map plus durable architecture summary |
| `project-intelligence` | Project overview, background, stack, structure, state, risks, and evidence from docs plus code/config/runtime sources | HTML project intelligence dashboard plus optional handoff summary |
| `design-system` | Design tokens, components, visual states, component variants | HTML design reference sheet |
| `docs-audit` | Documentation gaps, staleness, duplication, contradictions | HTML docs dashboard plus task-list updates |
| `docs-organization` | Organize messy docs, propose archive/move/rename/delete candidates, clarify source-of-truth layout | HTML organization workbench plus Markdown migration plan; execution requires explicit approval |
| `handoff` | Context for another agent or developer | Markdown handoff plus optional HTML map |
| `review` | PR, architecture, design, or documentation review | Annotated HTML review or Markdown findings |
| `report` | Weekly report, incident report, project status | HTML report plus Markdown action items |
| `interactive-editor` | Sorting, selecting, tuning, filtering, or decision capture | HTML editor with export payload |

## Format Decision

Use Markdown when the output is a durable fact, small update, or direct source-of-truth document.

Use HTML when the output benefits from:

- side-by-side comparison
- spatial structure
- visual state
- interaction
- quick scanning
- handoff clarity
- copy or export affordances

Use both when an HTML artifact produces conclusions that should survive beyond the current session.

Use project intelligence when the user wants to understand a project, inspect a repo, orient a new agent, audit docs in context, organize docs, or generate a project-level HTML artifact. Docs alone are not enough for this route unless the user explicitly asks for docs-only.

## Priority Rules

1. Project-local rules override this skill.
2. Markdown is the source of truth.
3. HTML is the working interface.
4. Do not generate HTML only because it looks nicer.
5. Do not skip Markdown sync for durable decisions.
6. Do not move, rename, archive, or delete documents without explicit approval after reference impact analysis.
7. Do not build project-level HTML artifacts from docs alone when code/config/runtime evidence is available.
