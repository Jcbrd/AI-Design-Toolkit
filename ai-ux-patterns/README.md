
# AI UX Patterns

Map an AI feature to the design patterns that matter for it — ranked by criticality, with concrete UI guidance and the failure modes most teams hit before you do.

---

## Overview

Designers shipping AI features make the same eight to ten decisions on every project: streaming or batch, how to surface confidence, what to do when the model refuses, how to handle regeneration, where citations live.

This skill maps your feature to the patterns that apply, ranks them by how badly things break without them, and gives you specific UI guidance — not principles, but actual decisions: what to build, what copy to use, what to watch for.

Built on Microsoft HAX guidelines (Amershi et al., CHI 2019), Google PAIR, and NN/g's AI usability heuristics. See `references/_frameworks.md` for the full pattern-to-HAX mapping.

---

## When to use it

Any time you're making AI feature design decisions — early scoping, design critique, spec review, or post-launch debugging. Common trigger phrases:

- "Designing an AI feature"
- "Should this stream?"
- "How do we show citations?"
- "What are we missing on this feature?"
- "AI feature review"

Also useful when reviewing a design spec, mockup, or PR description for an AI feature.

---

## How to use it

1. Open Claude and paste `SKILL.md` into the system prompt
2. Describe your feature in one or two sentences
3. Get back a ranked pattern output with a TL;DR, detail blocks, and "The hard part" summary you can take straight into a design review

---

## Output structure

Every response follows the same format:

**TL;DR** — the central tension and 2–3 highest-leverage decisions for your feature

**Pattern ranking** — Must address / Should address / Consider, each with a one-line summary of why it matters for your specific feature

**Detail blocks** — for every Must and Should pattern:
- The decision you need to make
- Concrete UI recommendation
- What teams ship that breaks
- The signal that your decision was wrong

**The hard part** — two or three sentences naming the central tension, written to be useful in a design review

---

## What's in this folder

| File | What it is |
|---|---|
| `SKILL.md` | The skill file — paste this into Claude |
| `README.md` | This file |
| `PATTERNS.md` | Full pattern index with descriptions and criticality guidance |
| `references/_frameworks.md` | Pattern-to-HAX mapping and citations |
| `references/[pattern].md` | One reference file per pattern |

---

## Patterns not recommended

A few AI UX patterns get hyped but rarely earn their place. This skill won't suggest:

- Personality / "AI as character" framing unless the brand calls for it
- Animated typing dots not tied to actual streaming
- Confidence percentages without an action that changes at different thresholds
- "Magic" or "✨" language in copy

If you ask about these directly, the skill will explain why they tend to hurt more than they help.
