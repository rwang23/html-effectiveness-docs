# Markdown Sync

Markdown is the durable source of truth. HTML is the working surface.

## Sync Matrix

| Content | Default target |
| --- | --- |
| Accepted implementation plans | `docs/plan/*-YYYY-MM-DD-HH.md` |
| Architecture and mental models | `docs/FORYOU.md` |
| Tasks and follow-up actions | `docs/TODO.md` |
| Long-running task state | `docs/active-tasks.md` |
| Meaningful completed changes | `docs/CHANGELOG.md` |
| User preferences, pitfalls, learned constraints | `docs/memory.md` |
| Analysis reports and audits | `docs/report/*-YYYY-MM-DD-HH.md` |
| Final HTML artifacts | `docs/effectiveness-artifact/` |
| Temporary explorations | `context/raw/` |

## Sync Rules

- Sync conclusions, not entire HTML pages.
- Link to final HTML artifacts when useful.
- Preserve project-local documentation rules.
- Create `docs/effectiveness-artifact/` only when producing a final HTML artifact.
- Do not rewrite unrelated docs.
- Do not erase user-authored content.

## Extraction Checklist

Before final response, check whether the artifact contains:

- selected option
- decision rationale
- task or follow-up action
- risk or mitigation
- architecture fact
- user preference
- verification result
- open question

If yes, sync the durable part to Markdown.
