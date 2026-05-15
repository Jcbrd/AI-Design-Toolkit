# UX Patterns for AI

When AI products can plausibly say anything, "the system works" stops being where trust comes from. Trust has to become something designers build into the surface itself — confidence shown honestly, citations that hold up, refusals that name a real reason, graceful uncertainty made legible.

This is a tactical reference for that work — fifteen patterns that operationalize Microsoft's HAX guidelines for designers shipping AI features.

## What it is

A Claude skill. Describe an AI feature you're designing ("I'm adding AI to our customer support tool") and the skill produces a ranked critique — must address, should address, consider — with concrete UI recommendations, common failure modes, and signals to revisit. Each pattern is grounded in established research and adds the tactical specifics frameworks don't go into.

The output is meant to be the first half of a design crit, not the last word. Every pattern ends with "Watch for" and "Revisit if" — signals that the right call depends on your context, your users, and your judgment.

## Who it's for

A product designer 1–4 years into their career who's been handed an AI feature to design and is the most AI-fluent designer in the room, even when they don't feel like it. Secondary: design-leaning PMs scoping AI features, senior designers using the patterns as a critique checklist, and design managers reviewing AI work.

It's not for visual designers who aren't touching AI, ML engineers (they need a model-evals vocabulary, not UX patterns), or people looking for an academic taxonomy. It's tactical on purpose.

## What it produces

Run the skill against a feature description; get back something shaped like this:

```
### [Feature in one phrase]

[2–3 sentence TL;DR — the central tension + the highest-leverage decisions]

Must address
- Pattern A — why critical
- Pattern B — why critical

Should address
- Pattern C — why this matters
- ...

Consider
- Pattern D — when this becomes relevant
- ...

[Detail blocks for Must and Should patterns:
 italic take + decide + recommendation bullets + watch for + revisit if]

The hard part: [the central design tension to bring to your next crit]
```

The TL;DR is the most-used part — designers under time pressure read only it. The detail blocks are there for when you need to defend a decision upstream.

## Installation

Download `ux-patterns-for-ai.skill` from the latest release. Then:

- **Claude Desktop / Cowork**: drag the file into the app, or use Settings → Skills → Install from file
- **Claude Code**: place the file in `~/.claude/skills/`, or run `claude skill install ux-patterns-for-ai.skill`
- **From source**: clone this repo and copy the `ux-patterns-for-ai/` folder into your skills directory

Once installed, the skill triggers automatically when you describe an AI feature to Claude — no special invocation needed.

## What's in the repo

- `SKILL.md` — the actual skill Claude reads
- `PATTERNS.md` — browsable index of all 15 patterns, grouped by designer intent
- `references/` — one file per pattern, plus `_frameworks.md` mapping each pattern to HAX guidelines
- `examples/` — sample outputs for common feature shapes *(coming soon)*

## What this isn't

This isn't strategic guidance. Strategy lives in HAX, Google's PAIR Guidebook, and NN/g's AI usability heuristics — see `references/_frameworks.md` for the relationships.

This isn't a replacement for design judgment. The patterns name the decision and the failure mode; the right answer depends on your product. Every block has a "Watch for" and a "Revisit if" for exactly this reason.

This isn't content design, responsible AI, or ethics. Those are real disciplines with their own bodies of work. HAX guidelines G5 (match social norms) and G6 (mitigate biases) sit closer to those disciplines and are intentionally not operationalized here.

This isn't exhaustive. Fifteen patterns, opinionated. If something feels missing — especially based on real work you're doing — open an issue.

## Built on

- **Microsoft HAX guidelines** (Amershi et al., CHI 2019) — primary anchor; 15 of 18 guidelines operationalized
- **Google PAIR Guidebook** — informs the philosophy of `designing-for-uncertainty` and agent collaboration framing
- **NN/g AI usability heuristics** — informs the designer-readable voice

See `references/_frameworks.md` for the full HAX mapping and gap analysis.

## Why I made it

I'm a product designer working on AI features. I noticed I was re-deciding the same eight or ten UX questions on every project — stream vs. batch, cite or trust, confidence as number or language, how to handle refusal. There's no canonical reference for any of this, and most teams figure it out by shipping the wrong thing first.

So I started writing patterns down for myself as I noticed them. Fifteen so far. The skill is the version I keep coming back to.

If you find it useful, or there's a pattern that should be here that isn't, [open an issue].

— Jacine
