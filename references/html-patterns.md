# HTML Patterns

Use self-contained HTML as a working interface, not as decoration.

These patterns are inspired by the design approach in
`https://thariqs.github.io/html-effectiveness/`: the important lesson is not
the exact CSS. The lesson is to make project knowledge spatial, skimmable,
portable, and useful for the next decision.

Treat that site as a style reference, not a style cage. Learn from its
information density, sectioning, inline evidence, compact comparison layouts,
and interaction patterns. Do not require artifacts to copy its palette,
typography, spacing, borders, or tone. Agents may create a different visual
language when the project, audience, or artifact type calls for it.

## File Rules

- Prefer one directly openable `.html` file.
- For project-level intelligence, prefer the stable path `docs/intel.html`.
- Avoid build steps for documentation artifacts.
- Use inline CSS and JavaScript only when they keep the artifact portable.
- Keep the page readable without network access.
- Use semantic filenames such as `implementation-plan.html`, `architecture-map.html`, or `docs-dashboard.html`.

## Layout Rules

- Start with title, context, recommendation, and next action.
- Use side-by-side sections for comparisons.
- Use timelines for plans, reports, and incidents.
- Use diagrams or boxes and arrows for architecture and flow.
- Use tables only when comparison benefits from rows and columns.
- Keep mobile readability: single-column fallback, no fixed-width overflow for main content.

## First Screen Intelligence Standard

For project-level artifacts, the first screen must teach the project before it asks the reader to navigate.

Within roughly the first screen, show:

- what the project is
- who or what it serves
- core product or workflow
- major system parts
- core tech stack
- current state or release posture
- top risks or next decisions
- clear drilldown entry points

If the first screen is mostly title, metrics, and links, it is not rich enough.

## Style Thinking

Do not hard-code a house style. Instead, design each artifact around the shape
of the work.

Use these style principles:

- Treat the page as a workbench, not a blog post. The reader should be able to compare, inspect, decide, and export.
- Make the scan path obvious: title, context, key metrics, recommendation, then supporting detail.
- Give each section a clear role. Examples: prompt/context, options, code, tradeoffs, timeline, diagram, risks, export.
- Use spatial layout to reduce memory load. Put comparable things next to each other instead of stacking them far apart.
- Prefer real project content over placeholders. Real filenames, code paths, statuses, risks, owners, and snippets make the artifact trustworthy.
- Use restrained visual hierarchy. Labels, section numbers, compact summaries, chips, and callouts should help orientation rather than decorate the page.
- Use color semantically. Reserve emphasis for status, severity, category, or recommendation; avoid arbitrary ornament.
- Use surfaces and boundaries to separate kinds of information. A code sample, risk table, mockup, and recommendation should not look like the same object.
- Keep dense information readable. Dense is fine when it is organized; crowded is not.
- Show the recommendation without hiding alternatives. The reader should see both the decision path and the rejected paths.
- Make artifacts feel portable. They should still make sense when opened outside the original chat or handed to another agent.
- Let the artifact carry the project's tone. A SaaS implementation plan, design-system sheet, incident report, and playful prototype should not all look identical.
- Preserve creative latitude. If a different layout, interaction model, or visual tone makes the artifact easier to understand, use it.
- Match style to content. A technical risk map, design-system reference, onboarding explainer, and incident timeline can use different visual languages.

## Style Reference Guidance

When referencing `html-effectiveness`, borrow ideas such as:

- compact first-screen framing
- side-by-side option comparison
- visible section numbering or labels
- inline code, mockup, timeline, map, or risk evidence
- restrained but meaningful visual hierarchy
- copy/export affordances for agent handoff
- interaction that reveals more detail without sending the reader away

Do not treat these as mandatory surface styling:

- exact colors
- exact typefaces
- exact border radius
- exact card style
- exact spacing scale
- exact background treatment

The artifact should feel intentional and project-specific, not like a cloned theme.

## Information Architecture Patterns

Use these reusable composition patterns:

- Hero summary: one compact opening area with artifact type, project name, prompt/context, and the decision the page enables.
- Project brief panel: what the project is, who it serves, current stage, and primary workflow.
- System shape map: apps, packages, workers, services, schemas, external APIs, and runtime boundaries.
- Stack strip: technologies grouped by frontend, backend, data, jobs, auth, deployment, testing, and integrations.
- Current-state board: working surfaces, blocked surfaces, release gates, high-risk areas, and recent completed work.
- Metrics strip: small facts such as effort, packages touched, risk count, owner, dates, or affected surfaces.
- Option grid: parallel cards or columns for alternatives that must be compared.
- Annotated code block: code plus short notes about what matters and where mistakes happen.
- Timeline: milestones, incidents, releases, or migration steps.
- Map: boxes and arrows for modules, data flow, ownership, or request paths.
- Risk table: severity, failure mode, mitigation, owner, and verification.
- Export block: a concise Markdown, JSON, or prompt payload that can go back into an agent.

Pick only the patterns that serve the artifact. Do not include every pattern by default.

## Richness Checklist

Before calling an HTML artifact complete, ask:

- Can a new reader understand project background, structure, stack, and current state from the artifact itself?
- Can the reader learn something important without clicking away?
- Can the reader drill into the highest-risk or highest-value areas?
- Are relationships visible, not only described?
- Are findings backed by evidence or examples?
- Is there a recommended path through the artifact?
- Is there a clear next-agent export or handoff?

If the answer is mostly no, the artifact is probably an index. Improve the artifact by adding a map, timeline, comparison, evidence drawer, annotated excerpt, or interactive focus control.

## Drilldown Detail Standard

For non-trivial project-level artifacts, include local drilldowns for at least four of these categories when evidence exists:

- overview: project brief, domain model, and current state
- architecture: system shape, module map, request flow, job flow, service boundaries
- stack: technologies and evidence paths
- docs: source-of-truth map, historical docs, generated artifacts, raw evidence
- risks: risk surface, impact, evidence, next action
- tasks: prioritized follow-up work and verification
- evidence: file paths, snippets, command outputs, or summarized proof

Use tabs, anchors, expandable sections, clickable cards, filters, or a detail pane. Do not require the reader to open many separate files just to understand the basics.

## Interaction Rules

Use interaction when it helps the reader decide or export state:

- tabs for related views
- details/summary for progressive disclosure
- filters for large inventories
- copy buttons for prompt payloads or decision summaries
- export sections for Markdown or JSON

Do not hide required information only behind hover states.

## Visual Rules

- Structure first, polish second.
- Avoid decorative backgrounds that do not explain the work.
- Use color to encode status, severity, or grouping.
- Keep text selectable.
- Keep contrast high enough for comfortable reading.
- Avoid making a generic dashboard when the user needs a specific artifact. The visual form should match the task: comparison, map, timeline, review, editor, or report.
- Avoid style rules that require future artifacts to copy exact colors, fonts, spacing, or borders from another example.

## Required Export Area for Complex Artifacts

For exploration, implementation, editor, and review artifacts, include an export area with one of:

- decision summary
- Markdown handoff
- JSON state
- prompt payload for the next agent

## Verification

Before completion:

- open the HTML or inspect it with an appropriate browser tool when available
- check that no major content overlaps
- test interactive controls if present
- verify copy/export content is visible and useful
