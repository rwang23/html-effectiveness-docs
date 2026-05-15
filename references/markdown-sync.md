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
| Project-level intelligence HTML | `docs/intel.html` |
| Temporary explorations | `context/raw/` |

## Sync Rules

- Sync conclusions, not entire HTML pages.
- Link to `docs/intel.html` when useful.
- Preserve project-local documentation rules.
- Create or update `docs/intel.html` for project-level intelligence artifacts.
- Do not rewrite unrelated docs.
- Do not erase user-authored content.
- When docs are moved, renamed, archived, or deleted after approval, update all known references in the same change.
- Record source-of-truth layout changes in durable docs such as `docs/FORYOU.md`, `docs/memory.md`, or a migration report.

## Agent Instruction Registration

When creating or updating `docs/intel.html`, register it in project agent
instructions so future agents know it exists and should be maintained.

Check for these files:

- `AGENTS.md`
- `agents.md`
- `CLAUDE.md`
- `claude.md`

If one or more exists, add or update a short section:

```markdown
## Project Intelligence

- Read `docs/intel.html` for the current project overview, architecture, stack, risks, docs map, and evidence.
- When project structure, stack, workflows, release state, or source-of-truth docs change, update `docs/intel.html` in the same work session.
```

If none exists, do not silently create one unless the user asked to initialize
agent instructions. Instead, report that no agent instruction file was found and
suggest adding `AGENTS.md` or `CLAUDE.md`.

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
