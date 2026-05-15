# html-effectiveness-docs

A Codex skill for project documentation that turns complex project knowledge into useful HTML work interfaces, then syncs durable conclusions back into Markdown.

[中文说明](README.zh-CN.md)

Inspired by [The unreasonable effectiveness of HTML](https://thariqs.github.io/html-effectiveness/).

## Background

Project documentation often fails because it is too linear. Architecture, implementation plans, design systems, PR reviews, reports, and handoffs are usually spatial and comparative: there are modules, tradeoffs, timelines, flows, states, risks, and decisions.

Markdown is still the right long-term source of truth. But for exploration, comparison, review, and handoff, a self-contained HTML artifact can be much easier to read and act on.

`html-effectiveness-docs` packages that pattern as an agent skill:

```text
HTML artifact = working interface for exploration, comparison, review, interaction, and handoff
Markdown docs = durable source of truth for decisions, tasks, architecture, memory, and project state
```

The goal is not prettier documentation. The goal is documentation that helps a human or agent decide what to do next.

## What This Skill Does

The skill helps agents create:

- exploration matrices for comparing solution directions
- implementation plans with milestones, data flow, risks, and verification
- architecture maps with modules, entry points, hot paths, and boundaries
- design references for tokens, components, variants, and states
- documentation dashboards for audits, gaps, staleness, and duplication
- annotated reviews for PRs, designs, architecture, or docs
- status reports and incident timelines
- interactive editors for sorting, selecting, tuning, filtering, and exporting decisions

## Design

The skill uses a Router + References structure:

```text
SKILL.md
references/
  routing.md
  workflows.md
  artifact-types.md
  markdown-sync.md
  quality-bar.md
  html-patterns.md
```

`SKILL.md` stays small. It tells the agent when to use the skill and which reference file to read.

The `references/` files hold the deeper behavior:

- `routing.md` classifies the request.
- `workflows.md` defines the default process.
- `artifact-types.md` defines the supported HTML artifact types.
- `markdown-sync.md` defines what must be written back to Markdown.
- `quality-bar.md` defines completion criteria and anti-patterns.
- `html-patterns.md` defines portable HTML conventions.

## Default Workflow

```text
Context Scan
-> Route
-> Artifact Plan
-> Create or Update Work Interface
-> Extract Decisions
-> Sync Markdown
-> Verify
-> Report
```

The skill first inspects local project rules such as `AGENTS.md`, `README`, `docs/`, and `context/`. Then it chooses whether the output should be Markdown, HTML, or both.

## Default Artifact Locations

Final HTML artifacts should be written to:

```text
docs/effectiveness-artifact/
```

Temporary explorations and drafts should go under:

```text
context/raw/
```

Durable conclusions should be synced to project docs such as:

```text
docs/TODO.md
docs/active-tasks.md
docs/CHANGELOG.md
docs/memory.md
docs/FORYOU.md
docs/plan/
docs/report/
```

Project-local rules override these defaults.

## Clone

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git
```

## Install for Codex

Copy or clone this repository into your Codex skills directory:

```powershell
git clone https://github.com/rwang23/html-effectiveness-docs.git "$env:USERPROFILE\.codex\skills\html-effectiveness-docs"
```

Then restart Codex or reload skills.

Manual install:

```powershell
Copy-Item -Recurse -Force .\html-effectiveness-docs "$env:USERPROFILE\.codex\skills\html-effectiveness-docs"
```

## Install for Other Agents

This repository is plain Markdown. Any agent system that supports local skills, instructions, or reusable prompts can use it.

### Generic local-agent install

1. Clone the repo.
2. Register `SKILL.md` as the skill entrypoint.
3. Keep the `references/` folder beside `SKILL.md`.
4. Tell the agent to read only the relevant reference file for the current task.

### Claude Code-style agents

Copy the folder into the agent's skills directory if your setup supports skills:

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git ~/.claude/skills/html-effectiveness-docs
```

If your agent does not have a formal skill directory, add `SKILL.md` to your project instructions and keep `references/` available as linked context.

### Cursor, Windsurf, or IDE agents

Clone the repository somewhere stable and reference `SKILL.md` from your rules or custom instructions. The important part is that the agent can open the adjacent `references/` files.

## Usage Examples

Ask your agent:

```text
Use html-effectiveness-docs to compare three implementation approaches and create a final artifact under docs/effectiveness-artifact/.
```

```text
Use html-effectiveness-docs to audit our docs folder and sync durable action items back to docs/TODO.md.
```

```text
Use html-effectiveness-docs to create an architecture map of this repo, then write the durable mental model to docs/FORYOU.md.
```

## Principles

- Do not generate HTML just because it looks nicer.
- Use HTML when information needs comparison, structure, visual state, interaction, or fast scanning.
- Keep HTML artifacts self-contained and directly openable.
- Sync durable conclusions back to Markdown.
- Verify artifacts and docs before reporting completion.
