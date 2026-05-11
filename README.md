# 🧭 Design Roadmap Architect

AI-fluent design project roadmaps for product designers, anchored in established frameworks and biased toward surfacing specialist tools the designer doesn't know yet.

---

## Overview

**design-roadmap-architect** turns a rough project idea into a personalized, framework-anchored design roadmap — with tool picks per stage, learning paths for new tools, and a living tracker to keep work moving.

It's built for the earliest moment of a design project: figuring out how to start. Describe your project in plain language and get back a complete plan structured through frameworks like Double Diamond, PAIR, HAX, Jobs-to-be-Done, Lean UX, and StoryBrand — matched automatically to your project type.

---

## Key Features

**Framework-matched planning** — Automatically pairs your project type to the right design process (mobile → Apple HIG + Double Diamond, AI product → PAIR + HAX, etc.).

**Personalized tool picks** — Suggests tools per stage based on your fluency. Tools you're learning are tagged with time estimates and inline learning paths. Tools you don't want are swapped out.

**Specialist-first recommendations** — Surfaces purpose-built tools over generalists wherever possible. Dovetail over Notion for research repos. Linear over Notion for sprint tracking. Anima over Cursor alone for handoff.

**Low-friction onboarding** — Reads your project description and infers framework, timeline, team size, and tool preferences. Asks only for what's genuinely missing.

**Fluency profiles** — Saves your tool proficiency to `design-flow-profile.json` and pre-fills it on future runs.

**Two output modes** — Interactive HTML tracker in Cowork, or a portable SVG + Markdown bundle everywhere else.

---

## When It Triggers

Use this skill at the planning stage of any design project — even if you don't use the word *roadmap*. Common trigger phrases:

- "How do I start designing this?"
- "Help me plan my project"
- "What tools should I use for X?"
- "How should I scope this?"
- "I need a roadmap for designing Y"
- "How do I approach an AI feature?"

---

## How It Works

### Stage 0 — Load Proficiency Profile

Checks for an existing `design-flow-profile.json` locally or in Cowork. If found and under 6 months old, silently pre-fills tool fluency. If older, uses it as a hint and asks for confirmation.

### Stage 1 — Onboarding

Reads your project description and infers:

- Project type and framework match
- Timeline and polish level
- Team size
- Tools to learn or avoid

Returns a one-paragraph read-back for confirmation before generating anything. You can confirm, adjust specific details, or opt into a structured form if you want full control.

### Stage 2 — Generation

Builds the full output in a single pass.

| Environment | Output |
|---|---|
| Cowork | `roadmap.html` — interactive tracker with persistent progress |
| Everywhere else | `roadmap.svg` + `project-plan.md` + updated fluency profile |

Every stage in the roadmap lists tasks with their assigned tool — not just a tool list at the top of the stage, but tool attribution per sub-task.

---

## Output Artifacts

**In Cowork (`roadmap.html`)**
- Expandable stage cards with sub-task checkboxes
- Tool detail panels with learning paths
- "What I shipped" capture per completed stage
- localStorage persistence across sessions

**Outside Cowork**
- `roadmap.svg` — linear visual roadmap
- `project-plan.md` — Markdown checklist with folded reading list
- `design-flow-profile.json` — updated tool fluency state

---

## Framework Reference

| Project Type | Framework Spine |
|---|---|
| Mobile / native app | Apple HIG + Double Diamond |
| Web SaaS UI | Jobs-to-be-Done + Lean UX |
| AI product | Google PAIR + Microsoft HAX |
| Marketing site | CRO Funnel + StoryBrand |
| Service design | Service Blueprint + Customer Journey |
| Internal tool / dashboard | Utility-first + Power-user UX |
| Hybrid | Blend of relevant spines |
| No match found | Double Diamond fallback |

---

## Tool Diversity Rule

To prevent over-reliance on general-purpose tools:

- Generalist tools (Claude, Notion) appear a maximum of 2–3 times across the full roadmap
- Specialist tools take priority at any stage where one exists
- Each stage should introduce at least one specialist or "willing-to-learn" tool
- Tools the user is investing in learning appear across multiple stages for repeated practice

---

## Edge Cases

| Scenario | Behavior |
|---|---|
| Branching or loops requested | Linear only in v1 — branch described in text, flagged as v2 |
| Stages skipped (e.g. user research) | Honored; missing stages noted in Risks section |
| No framework match | Falls back to Double Diamond with a note |
| Profile older than 6 months | Used as a hint only — confirmation required |

---

## File Structure

```
design-roadmap-architect/
├── frameworks/
│   ├── mobile-app.md
│   ├── web-saas.md
│   ├── ai-product.md
│   ├── marketing-site.md
│   ├── service-design.md
│   └── internal-tool.md
├── tools/
│   └── library.md
├── templates/
│   ├── artifact-example.html   # Canonical interactive tracker (Cowork)
│   ├── svg-spec.md             # Static SVG roadmap spec
│   ├── checklist.md            # Markdown project plan format
│   └── artifact-spec.md        # Maintainer docs — not loaded at runtime
└── README.md
```

---

## Contributing

When editing this skill, do not modify `templates/artifact-example.html` unless you intend to change the tracker's structure or interactivity for all future projects — it is the canonical template that gets copied and edited at generation time. Document any structural changes in `templates/artifact-spec.md`.
