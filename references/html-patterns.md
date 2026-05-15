# HTML Patterns

Use self-contained HTML as a working interface, not as decoration.

## File Rules

- Prefer one directly openable `.html` file.
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
