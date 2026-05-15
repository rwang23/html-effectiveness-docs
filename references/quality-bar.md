# Quality Bar

The completion standard is not "created a nice-looking page." The standard is:

```text
Project understanding is compressed into an actionable interface.
Durable conclusions are synchronized back to Markdown.
The next human or agent can continue from the result.
```

## Successful Run

A successful run satisfies:

- clear intent route
- justified output format
- useful HTML when HTML is used
- HTML artifacts expose relationships, evidence, and actions instead of merely linking to files
- project-level HTML artifacts explain project background, structure, tech stack, current state, and evidence from docs plus code/config/runtime sources
- project-level intelligence is written to a stable `docs/intel.html` entrypoint unless project-local rules choose another path
- durable Markdown sync for decisions and project facts
- readable handoff for a future agent or developer
- verification performed and reported
- final response includes paths and residual risks

## Rich HTML Artifact Bar

An HTML artifact should feel closer to an inspectable work surface than a static index.

For non-trivial artifacts, require:

- observable structure: relationships, flow, sequence, categories, or hierarchy are visible without opening another file
- local interaction: tabs, filters, anchors, expandable evidence, sortable groups, or copy/export controls
- evidence: key findings cite file paths, snippets, summarized proof, or concrete examples
- decision support: the artifact shows recommended action, alternatives, risk, and next step
- export path: the reader can copy a concise handoff, task list, JSON state, or prompt payload

If an artifact mostly contains metrics, links, and a table of files, treat it as an index. An index can be useful, but it does not satisfy this skill's bar for a rich effectiveness artifact unless the user explicitly asked for an index.

## Project Intelligence Quality Bar

For project-level artifacts, the first screen must answer:

- What is this project?
- Who or what does it serve?
- What are the main system parts?
- What stack does it use?
- What is the current implementation or release state?
- What are the top risks or next decisions?
- Where can the reader click to inspect architecture, stack, docs, risks, tasks, and evidence?

The artifact fails this bar if a reader must open README, docs, package files, or source files before understanding the basic project context.

The artifact must also show evidence source types:

- docs
- code structure
- config/runtime files
- tests/scripts
- external integration signals
- recent changes when available

If any major source type was not inspected, say so explicitly.

For `docs/intel.html`, also satisfy `project-intelligence-artifact.md`.
It must be a project intelligence workbench, not only a docs/reference dashboard.

When `docs/intel.html` is created or updated, the run is incomplete until one of
these is true:

- `AGENTS.md`, `agents.md`, `CLAUDE.md`, or `claude.md` references it and says it should be maintained.
- No agent instruction file exists, and the final report clearly says registration was not possible.

## Anti-Patterns

Avoid:

- treating HTML as prettier Markdown
- treating HTML as a link index when the task calls for observation, drill-down, or decision support
- generating project-level HTML from docs alone when code/config/runtime evidence is available
- omitting project background, structure, stack, or current state from a project-level artifact
- producing `docs/intel.html` as a docs index instead of a project intelligence workbench
- copying a reference site's visual skin without adapting the information architecture to the project
- blocking agent creativity with fixed CSS rules when a different visual approach would communicate better
- generating decorative pages with no decision value
- leaving final decisions only in HTML
- generating HTML for simple facts that belong in Markdown
- adding build steps or large frameworks for temporary artifacts
- reporting without verification
- listing options without recommendation criteria
- giving abstract docs-audit advice without concrete files or task-list updates
- ignoring project-local instructions
- forcing heavy ceremony onto a trivial edit
- moving, renaming, archiving, or deleting docs without first searching project-wide references and preparing link rewrites
- treating missing links as acceptable collateral damage during document cleanup

## Documentation Organization Safety Bar

For docs cleanup work, the quality bar includes link safety.

Before recommending any move, rename, archive, or delete:

- search the full project for references to the current path, filename, title, and known aliases
- identify Markdown links, HTML links, README references, plans, reports, code comments, config references, and generated artifacts
- show referencing files in the organization workbench
- provide a link rewrite plan for each reference
- mark the action blocked when references cannot be updated confidently

Before executing any filesystem organization:

- get explicit user approval
- preserve history by archiving or marking historical unless deletion was explicitly requested
- update all known references in the same change
- verify old references no longer appear except in intentional history/archive notes
- verify new links resolve when practical

## Completion Checklist

Before final response, verify:

- local rules were inspected
- task intent was named
- output strategy was chosen
- required artifact exists
- Markdown sync was considered and performed when needed
- artifact and docs were checked
- final report names paths, checks, and unresolved questions
