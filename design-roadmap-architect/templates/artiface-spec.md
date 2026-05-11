# Living tracker artifact specification
 
This is the spec for the HTML artifact output the skill produces in Cowork (via `mcp__cowork__create_artifact`).
 
**Canonical reference: `templates/artifact-example.html`** — a complete, working example artifact for an agentic AI gardening app. Use it as your structural reference and substitute project-specific content in. Don't try to compose from scratch — copy the structure, replace the data.
 
## Overall structure
 
The HTML is a single self-contained document:
 
- `<style>` — inline CSS, light-mode design (background `#FAF9F5`, white surfaces, purple accent `#534AB7`, green progress `#639922`)
- `<body>`:
  - Header with project name, meta line, and progress bar
  - `<ol class="stages">` — stage cards
  - Risks section (project-specific risks based on stages skipped, team size, etc.)
  - Frameworks section (the reading list folded in)
  - Hidden tool detail panel (slides up from bottom when a tool pill is clicked)
- `<script>` — inline JS, ~400 lines, no external libraries
## What to substitute per project
 
**`project` data structure** (in the inline script):
```js
const project = {
  name: '[project name]',
  stages: [
    {
      id: 1,
      title: '[stage title]',
      desc: '[one-line description]',
      tools: ['key1','key2'],   // keys from the tools{} object
      framework: 'Anchored in [framework references]',
      deliverable: '[concrete artifact this stage produces]',
      why: '[one sentence on why this stage exists, framework-tied]',
      tasks: [
        { id: '1-1', text: '[task]', tool: 'key1', estimate: '[time]' },
        // tasks: tool field references a tool key; estimate is a string like "45 min", "2 hrs", "1 day"
        // tasks without a tool dependency: tool: null, estimate: null
      ]
    },
    // ... one entry per chosen stage
  ]
};
```
 
**`tools` object** — one entry per unique tool referenced in any stage:
```js
const tools = {
  'tool-key': {
    name: '[Display name]',
    icon: '[1-3 letters]',         // brand letter(s) for the tile
    color: '[hex]',                 // brand color for the tile background
    fluency: 'expert' | 'proficient' | 'willing-to-learn',
    description: '[one sentence]',
    why: '[why this tool fits this project]',
    homepage: '[URL]',
    swapOptions: ['Alt 1', 'Alt 2', 'Alt 3'],
    learning: [                    // only for willing-to-learn
      { title: '[resource title]', url: '[URL]' }
    ]
  }
};
```
 
**Header fields** (in `<header class="head">`):
- `<h1>` — project name
- `<p class="meta">` — "[project type] · [N] stages · [team size]"
**Risks section** — pick 3-4 project-specific risks based on:
- Stages skipped (e.g., "Skipped user research: [why this matters for this project type]")
- Team size + shape combo (e.g., "Solo + production-grade: plan for an outside review")
- Project type specifics (e.g., for AI products: "agentic AI safety review before handoff")
**Frameworks section** — pull URLs and one-line descriptions from the framework reference file used.
 
## State persistence (localStorage)
 
Storage key format: `design-flow-planner:[project-slug]:v4`
 
State shape:
```js
{
  taskState: { 'task-id': true | false, ... },     // checked/unchecked
  customTasks: { 'stage-id': [{ id, text, custom: true, ... }] },
  shippedNotes: { 'stage-id': { what, link, savedAt } },
  skippedTasks: { 'stage-id': ['task-id-1', ...] }, // framework tasks user skipped
  taskOverrides: { 'task-id': '[edited text]' },   // edited task text
  lastUpdated: '[ISO timestamp]'
}
```
 
## Critical interaction details
 
**Status auto-derives from checkbox completion** — never expose manual status buttons. Function `deriveStageStatus(stage, state)` returns:
- `'not-started'` if 0 tasks ticked
- `'in-progress'` if some but not all ticked
- `'done'` if all ticked
**Checkbox change handler must NOT trigger full re-render** — that collapses the expanded stage. Targeted update only: change the stage's `data-status` attribute, update progress bar, and conditionally inject the shipped capture form if status just transitioned to done.
 
**"What did you ship?" capture** appears inside the expanded stage when the stage transitions to done AND no shipped note exists yet. Save persists to `shippedNotes`; once saved, replaces with a green "✓ Shipped" banner at top of the stage body.
 
**Tool pills display fluency state** — willing-to-learn tools get a small `↗` chip; expert/proficient tools have no chip.
 
**Tool detail panel** opens from bottom-right when a pill is clicked. Contains: tool name + brand tile + fluency status, description, why-this-tool reasoning, "Ask Claude about this for my project" button, "Open homepage" link, learning path (only for willing-to-learn), swap alternatives (always visible at bottom — no click required to reveal).
 
**askClaude integration** — primary action button calls `window.cowork.askClaude(prompt, [])` with a project-specific prompt. Show loading state, render response inline as plain text. Wrap in try/catch.
 
## Composition order (copy + targeted Edits — NOT from-scratch composition)
