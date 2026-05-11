---
name: design-roadmap-architect
description: AI-fluent design project roadmaps for product designers, anchored in established frameworks (Double Diamond, PAIR, HAX, JTBD, Lean UX, StoryBrand) and biased toward surfacing specialist tools the designer doesn't know yet. In Cowork, outputs a living HTML tracker with checkboxes, progress, and a "what I shipped" capture per stage. Use this skill whenever a designer mentions planning a project, scoping work, sequencing steps, picking tools for a new project, creating a roadmap, or figuring out how to approach a design project. Trigger on phrases like "plan my project", "how should I scope this", "what tools should I use for X", "create a project roadmap", "design workflow for", "sequence this project", "how do I start designing this". Use even if the user doesn't explicitly ask for a "roadmap" — if they're talking through a design project at the planning stage, turn it into a concrete framework-anchored plan with personalized tool picks.
---
 
# Design Roadmap Architect
 
This skill helps a product designer turn a vague project ("I'm designing a mobile app for X") into a personalized, framework-anchored roadmap. The user picks which stages they actually want, picks tools they're comfortable with vs. willing to learn vs. want to swap out, and gets back either a living HTML tracker (in Cowork) or a portable SVG + Markdown bundle (everywhere else).
 
## Use this skill when
 
A designer is at the planning stage of a project. Common triggers:
 
- "I'm starting a [mobile app / website / dashboard / etc.] and want to plan it out"
- "What tools should I use for X?"
- "How should I scope this project?"
- "Help me figure out the steps for this design"
- "I need a roadmap for designing Y"
- "How do I approach designing an AI feature?"
## What this skill produces
 
**In Cowork** (preferred — using `mcp__cowork__create_artifact`):
- A living HTML tracker artifact with stage cards, click-to-expand sub-tasks (with checkboxes), tool pills (clickable for detail panel), inline learning paths for willing-to-learn tools, "what did you ship?" capture per stage when complete, and localStorage persistence so the tracker remembers progress across sessions.
- The canonical reference for the artifact is `templates/artifact-example.html` — copy it directly per the speed-fix workflow in Stage 2. Do NOT read `templates/artifact-spec.md` at runtime; it is human-facing documentation for skill maintainers, not workflow guidance for Claude.
**Outside Cowork** (Claude Code, Claude.ai, etc.):
- `roadmap.svg` — a static visual roadmap (specified in `templates/svg-spec.md`)
- `project-plan.md` — a tight Markdown checklist with reading list folded in (specified in `templates/checklist.md`)
In both cases, also save `design-flow-profile.json` (the user's tool fluency profile) so subsequent runs can pre-fill it.
 
## Workflow overview
 
The skill runs in two stages: **onboarding** (gather everything in a single session, 5-6 questions max) and **generation** (produce the bundle in one pass). No regeneration step — onboarding upfront is meant to feel less wasteful than seeing an output and being asked to refine it.
 
### Stage 0: Load proficiency profile
 
Before asking new questions, look for `design-flow-profile.json` in:
1. The current working directory
2. The Cowork outputs folder (if running in Cowork mode)
3. `~/.design-flow-planner/profile.json`
If a profile exists and is less than 6 months old, mention to the user that you remember their tool fluency and will pre-fill the proficiency questions. If older than 6 months, treat as a hint but ask them to confirm — tools change fast.
 
### Stage 1: Onboarding (lightweight — infer first, ask only for blocking gaps)
 
The most common failure mode of planning skills is asking too much upfront. Designers don't want to fill out a form to get a roadmap. **Goal: time-to-first-output under 30 seconds for users who provide a clear description.**
 
**The default flow:**
 
1. **Read the user's invocation message.** Most designers will provide enough context in their first sentence: project description, timeline, team, tools they want to learn. Extract:
   - Project type (mobile app, SaaS, AI product, marketing site, service, internal tool, or hybrid)
   - One-line description / domain
   - Team size, if mentioned
   - Polish level / timeline, if mentioned
   - Tools the user named explicitly as "want to learn" or "don't want to use"
2. **Show your reading back, and offer Generate.** This is the single onboarding moment. Format:
   ```
   Got it. Here's my read:
   - [Project type, with framework attribution — e.g., "Hybrid: AI product + mobile (PAIR/HAX + Apple HIG)"]
   - [Polish level inferred from timeline / shape signals — e.g., "Standard 5-step build (6-week timeline)"]
   - [Team size]
   - Willing to learn: [tools mentioned, with typical learning times from tools/library.md]
   - Default proficiency on: [common tools the framework will pull from]
   - Including all [N] framework stages
   
   Hit Generate, or tell me what to adjust.
   ```
 
3. **User responds in one of three ways:**
   - **Confirms** ("Generate" / "Looks good" / "Yes") → proceed to Stage 2
   - **Specific corrections** ("Skip user research" / "Drop Posthog, use Mixpanel" / "Actually solo for the first 3 weeks") → adjust the reading and proceed (don't re-show summary unless multiple things changed)
   - **Asks for the structured form** ("show me the questions") → fall back to the legacy form-based onboarding (4 single-selects + stage multi-select + per-tool fluency questions). Opt-in only — never the default.
4. **Only ask clarifying questions when the description genuinely doesn't have enough.** Examples:
   - User says "redesigning our app" → ask one question: "What kind of app, and roughly when do you need it ready?"
   - User says "new project" with no other detail → ask the single most blocking question first
   - **Don't ask about every dimension. Only the blocking gap.**
5. **Don't ask separate questions about:**
   - Time estimates (default to including time pills; user can opt out by saying "skip times")
   - Stage selection (default to all canonical framework stages; users skip individual tasks or whole stages in the artifact via the existing skip mechanism)
   - Tool fluency for tools the user didn't mention (assume Proficient defaults; the diversity rule in `tools/library.md` will surface specialists the user may not know, which the user can swap in the artifact)
**Profile pre-fill:** If `design-flow-profile.json` exists, fold its answers into the inferred fluency silently. Mention once in the reading summary: "I remember you're proficient in Figma and FigJam, learning Cursor."
 
**Stage selection in the artifact, not the onboarding:** The skill defaults to all canonical framework stages. Users skip individual framework tasks via the ✕ button in the artifact (already built — sets a "skipped" status, struck-through, excludes from completion). Users who want to skip a whole stage can do so by skipping all its tasks. This trades upfront friction for in-context friction, where the user has more information to decide what to skip.
 
### Stage 2: Generation (single pass)
 
With all context gathered, generate the bundle in one pass.
 
**Pick the framework spine.** Load the matching framework reference file from `frameworks/`:
 
| Project type | Reference file |
|---|---|
| Mobile or native app | `frameworks/mobile-app.md` |
| Web SaaS UI | `frameworks/web-saas.md` |
| AI product | `frameworks/ai-product.md` |
| Marketing site | `frameworks/marketing-site.md` |
| Service or system design | `frameworks/service-design.md` |
| Internal tool / dashboard | `frameworks/internal-tool.md` |
 
For hybrid projects, blend two framework files. Note the blend in framework attribution.
 
**Pick tools per stage** from `tools/library.md`. Apply proficiency tiers:
- Expert / Proficient → tool appears as standard pill, no chip
- Willing to learn → tool appears with `↗` chip + timeframe label (e.g., "Cursor ↗ 1wk"); learning path included in the project plan
- Not interested → tool replaced with the user's chosen swap candidate from the onboarding step (no chip)
**Apply the diversity rule** (see `tools/library.md` "Diversity rule" section). Critical for the skill's actual value — exposing designers to new tools. The rule in short:
- Max 2-3 appearances per generalist tool (Claude, Notion) across the whole roadmap
- Specialists beat generalists at any stage where a real specialist exists (Perplexity over Claude for research, Anthropic Console over Claude for prompt testing, Anima over Cursor alone for handoff, Linear over Notion for sprint tracking, Dovetail over Notion for research repository)
- Bias toward "willing to learn" tools across stages — give the user multiple chances to practice the tools they're investing in
- Each stage should introduce at least one specialist or "willing to learn" tool when possible
If you find Claude appearing in 5+ stages of a 6-stage roadmap, that's a failure. Reach for specialists.
 
**Compose the output via copy-and-edit, NOT from scratch.** This is critical for performance — composing the 700-line HTML artifact in one pass causes stream timeouts. Instead:
 
1. **Copy `templates/artifact-example.html` to the output path** via bash: `cp <skill_path>/templates/artifact-example.html <output_path>/roadmap.html`. The example is the canonical reference and contains all the CSS, JS interactivity, dialog logic, and persistence machinery — none of which changes per project.
2. **Use targeted Edit calls** to substitute only the project-specific data. The example contains gardener-project data; replace each block with project-specific content:
   - `<title>...</title>` → user's project title
   - `<h1>Agentic AI gardening app</h1>` → user's project name
   - `<p class="meta">Hybrid mobile + AI · 6 stages · 2-3 person team</p>` → project meta line
   - `const STORAGE_KEY = 'design-flow-planner:agentic-ai-gardening:v4';` → unique slug for this project
   - The entire `const project = {...}` block → new stages array with this project's content
   - The entire `const tools = {...}` block → tools used in this project
   - The `<section class="risks">...</section>` block → 3-4 risks specific to this project
   - The `<section class="frameworks-section">...</section>` block → frameworks actually used
   - The `askClaude` prompt template inside `openToolPanel`: `\`I'm designing an agentic AI gardening app (mobile + AI hybrid, 2-3 person team, 6 stages of work covering strategy through launch).\`` → project context for this user
   That's 9 targeted Edit calls — each small input, small output. Much faster than generating 700 lines of HTML from scratch.
3. **Pass the modified file to `mcp__cowork__create_artifact`** with a project-specific id.
Outside Cowork, follow `templates/svg-spec.md` (SVG) and `templates/checklist.md` (Markdown). The static path can compose more freely since SVG output is smaller.
 
**Critical for the output: every task must name which tool to use, in what order.** Tasks with no tool dependency (e.g., "Stakeholder sign-off") can omit the tool reference. This addresses a common failure mode where designers see a list of tools at the top of a stage but don't know which one to use for which sub-task.
 
**Save the bundle** to the user's outputs folder. Update `design-flow-profile.json` with the latest proficiency answers.
 
Tell the user where the files are. Don't summarize file contents in chat — the artifact (or visual) is the deliverable.
 
## Edge cases and judgment calls
 
**The user wants branches or loops in the diagram.** v1 of this skill draws linear roadmaps only. If the user explicitly asks for a fork, describe in text where it would go but explain branching is a v2 capability.
 
**The user provides existing context.** Skip questions whose answers are already in the conversation.
 
**The user wants to skip the proficiency assessment.** Honor that. Default all framework-suggested tools to Proficient. Save the bundle but don't update the profile.
 
**The user's project doesn't fit any framework.** Fall back to a generic Double Diamond spine (Discover → Define → Develop → Deliver) and tell the user no exact framework match was found.
 
**The user picks fewer stages than the canonical sequence.** Honor it. Note any obviously-skipped stages (e.g., user research, visual design) in the risks section of the project plan as things to watch.
 
## Reference files
 
- `frameworks/mobile-app.md` — Apple HIG + Double Diamond
- `frameworks/web-saas.md` — Jobs-to-be-Done + Lean UX
- `frameworks/ai-product.md` — Google PAIR + Microsoft HAX
- `frameworks/marketing-site.md` — CRO funnel + StoryBrand
- `frameworks/service-design.md` — Service blueprint + customer journey
- `frameworks/internal-tool.md` — Utility-first + power-user UX
- `tools/library.md` — Tool metadata, swap rules, learning paths, **typical learning times** (used in onboarding to show inline estimates next to "willing to learn" options)
- `templates/artifact-example.html` — **Canonical reference for the Cowork HTML artifact. Copy this directly per Stage 2; do not regenerate.**
- `templates/svg-spec.md` — Static SVG specification (non-Cowork fallback only — do not load in Cowork)
- `templates/checklist.md` — Project plan Markdown structure with folded reading list (non-Cowork fallback only)
- `templates/artifact-spec.md` — Human-facing documentation for skill maintainers describing the artifact structure. **Do NOT load at runtime.** Only useful for someone editing the artifact's design.
