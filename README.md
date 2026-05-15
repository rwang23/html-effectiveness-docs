# html-effectiveness-docs

An agent skill for project documentation that turns complex project knowledge into useful HTML work interfaces, then syncs durable conclusions back into Markdown.

[中文说明](README.zh-CN.md)

Inspired by [The unreasonable effectiveness of HTML](https://thariqs.github.io/html-effectiveness/).

## Clone

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git
```

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
- project intelligence dashboards that combine docs, code, config, runtime, tests, scripts, and integration evidence
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
  project-intelligence.md
  markdown-sync.md
  quality-bar.md
  html-patterns.md
```

`SKILL.md` stays small. It tells the agent when to use the skill and which reference file to read.

The `references/` files hold the deeper behavior:

- `routing.md` classifies the request.
- `workflows.md` defines the default process.
- `artifact-types.md` defines the supported HTML artifact types.
- `project-intelligence.md` defines how project-level artifacts extract background, structure, stack, current state, risks, and evidence from docs plus code/config/runtime sources.
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

## Install

This is a plain Agent Skills-style package: one folder with `SKILL.md` plus a `references/` directory.

### Install for Codex

```powershell
git clone https://github.com/rwang23/html-effectiveness-docs.git "$env:USERPROFILE\.codex\skills\html-effectiveness-docs"
```

Restart Codex or reload skills after installation.

### Install for Claude Code

Personal skill:

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git ~/.claude/skills/html-effectiveness-docs
```

Project skill:

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git .claude/skills/html-effectiveness-docs
```

Claude Code discovers skills from `~/.claude/skills/` and project `.claude/skills/` directories.

### Install for OpenCode

OpenCode native global skill:

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git ~/.config/opencode/skill/html-effectiveness-docs
```

OpenCode project skill:

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git .opencode/skill/html-effectiveness-docs
```

OpenCode can also discover Claude-compatible skill paths, so the Claude Code install path is a useful shared option.

### Install for OpenClaw

Global skill:

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git ~/.openclaw/skills/html-effectiveness-docs
```

Workspace skill:

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git skills/html-effectiveness-docs
```

Review the skill contents before loading it into OpenClaw, especially in environments where skills can access tools or shell commands.

### Install for Hermes

Local skill:

```bash
git clone https://github.com/rwang23/html-effectiveness-docs.git ~/.hermes/skills/html-effectiveness-docs
```

Hermes can also scan external skill directories. If you keep shared skills in `~/.agents/skills`, clone there and add that directory to `skills.external_dirs` in `~/.hermes/config.yaml`.

### Generic Manual Install

1. Clone this repository.
2. Put the folder in your agent's skills directory.
3. Keep `SKILL.md` and `references/` together.
4. Restart or reload the agent's skill index.

## Principles

- Do not generate HTML just because it looks nicer.
- Use HTML when information needs comparison, structure, visual state, interaction, or fast scanning.
- Keep HTML artifacts self-contained and directly openable.
- Sync durable conclusions back to Markdown.
- Verify artifacts and docs before reporting completion.
