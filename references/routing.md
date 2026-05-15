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
| `design-system` | Design tokens, components, visual states, component variants | HTML design reference sheet |
| `docs-audit` | Documentation gaps, staleness, duplication, contradictions | HTML docs dashboard plus task-list updates |
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

## Priority Rules

1. Project-local rules override this skill.
2. Markdown is the source of truth.
3. HTML is the working interface.
4. Do not generate HTML only because it looks nicer.
5. Do not skip Markdown sync for durable decisions.
