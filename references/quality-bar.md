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
- durable Markdown sync for decisions and project facts
- readable handoff for a future agent or developer
- verification performed and reported
- final response includes paths and residual risks

## Anti-Patterns

Avoid:

- treating HTML as prettier Markdown
- generating decorative pages with no decision value
- leaving final decisions only in HTML
- generating HTML for simple facts that belong in Markdown
- adding build steps or large frameworks for temporary artifacts
- reporting without verification
- listing options without recommendation criteria
- giving abstract docs-audit advice without concrete files or task-list updates
- ignoring project-local instructions
- forcing heavy ceremony onto a trivial edit

## Completion Checklist

Before final response, verify:

- local rules were inspected
- task intent was named
- output strategy was chosen
- required artifact exists
- Markdown sync was considered and performed when needed
- artifact and docs were checked
- final report names paths, checks, and unresolved questions
