# html-effectiveness-docs

A Codex skill for project documentation that uses self-contained HTML artifacts as working interfaces and Markdown as the durable source of truth.

中文说明: [README.zh-CN.md](README.zh-CN.md)

Inspired by [The unreasonable effectiveness of HTML](https://thariqs.github.io/html-effectiveness/).

The skill helps agents produce exploration matrices, implementation plans, architecture maps, design references, documentation dashboards, annotated reviews, reports, and interactive editors.

## Core Idea

HTML is the thinking surface.
Markdown is the memory surface.

Use HTML when documentation needs comparison, spatial structure, visual states, interaction, or fast scanning. Sync decisions, risks, tasks, architecture facts, user preferences, and verification results back into Markdown.

## Install

Copy this folder to:

```text
C:\Users\desre\.codex\skills\html-effectiveness-docs\
```

Restart Codex or reload skills after installation.

## Structure

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

## Default Artifact Location

Final HTML artifacts should be written to:

```text
docs/effectiveness-artifact/
```

Temporary explorations and drafts should go under `context/raw/` when the project uses a `context/` directory.
