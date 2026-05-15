# Style Reference

This reference summarizes the design approach observed in
`https://thariqs.github.io/html-effectiveness/`.

Use it as a style reference, not a style cage. The point is not to clone its
CSS. The point is to make generated HTML feel like a rich, inspectable work
surface instead of a static document or link index.

## Design Thesis

The examples work because each HTML file is shaped around the job it replaces.

- Exploration becomes side-by-side comparison.
- Implementation planning becomes timeline, data flow, mockups, key code, risks, and open questions.
- Code understanding becomes module map, hot path, key files, snippets, and gotchas.
- Flow explanation becomes a clickable diagram.
- Research becomes tabs, collapsible steps, glossary, and examples.
- Editing becomes a small custom UI with export.

Do the same: let the artifact's form follow the project question.

## Visual Grammar Observed

Common visual ingredients:

- warm paper-like background rather than generic white dashboard
- compact but readable density
- serif display headings, sans body copy, mono labels/code
- muted neutrals with a small semantic accent palette
- thin borders and quiet surfaces separating information types
- chips, labels, counters, and section numbers for orientation
- code blocks, inline snippets, mockups, SVG maps, and tables treated as first-class content
- restrained emphasis; color usually encodes status, category, severity, or recommendation

These are not mandatory CSS rules. They are evidence that a coherent visual
system helps the reader understand the artifact quickly.

## Information Architecture Patterns

Borrow these patterns when they fit:

- compact prompt/context box near the top
- first-screen summary that states the artifact's job
- option grid for comparing approaches
- metrics strip for small high-value facts
- numbered sections for long artifacts
- timeline for plans, incidents, migrations, and release tracks
- annotated code for risky implementation details
- SVG map or flowchart for system structure
- mockups for UX or workflow decisions
- risk table with severity and mitigation
- export block for next-agent handoff

Avoid applying all patterns by default. Choose the few that make the specific
artifact more observable.

## Interaction Patterns Observed

Use local interaction when it helps the reader inspect or decide:

- click a diagram node to reveal step details
- expand details for evidence, gotchas, or logs
- switch tabs between views
- filter large inventories
- drag or reorder when prioritization is the task
- tune controls when the artifact is a prototype
- copy/export the final state
- keyboard navigation for slide-style artifacts

Interaction should reveal more project truth. It should not be decorative.

## Artifact Morphology

Different artifact types should look different:

- Comparison artifacts: parallel columns, tradeoff grids, recommendation block.
- Implementation plans: milestone timeline, data flow, mockups, key code, risk table.
- Architecture maps: visual system map, hot path, entry points, key files, gotchas.
- Docs dashboards: source-of-truth map, relationship graph, stale/duplicate evidence, cleanup board.
- Project intelligence pages: project brief, system shape, stack, state, risks, tasks, evidence drilldowns.
- Reports: timeline, impact, metrics, action items.
- Editors: purpose-built controls plus copy/export output.

If every artifact uses the same dashboard layout, the skill is failing.

## Creative Latitude

Agents may and should create project-specific visual language.

Use a different style when:

- the project domain calls for a different tone
- the artifact is a prototype, report, course, or editor rather than a plan
- the project already has a design system
- a different visual layout makes relationships clearer

Do not hard-code exact colors, typefaces, spacing, shadows, or card styles from
the reference site.

## Practical Checklist

Before writing HTML, decide:

- What document or workflow is this replacing?
- What would be painful to understand in Markdown?
- What should be compared side by side?
- What should be shown spatially?
- What should be clickable or expandable?
- What evidence should be visible in the artifact?
- What should be exported back to Markdown or the next agent?

If the artifact is just a header, metrics, links, and a table, redesign it.
