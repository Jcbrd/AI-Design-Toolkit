# Pattern Index

Fifteen tactical patterns for designers shipping AI features. Each operationalizes one or more Microsoft HAX guidelines and adds the specific UI choices, copy, and failure modes that strategic frameworks don't go into.

Grouped by what you're asking when you reach for a pattern. See [`references/_frameworks.md`](./references/_frameworks.md) for the full HAX mapping.

---

## Trust surfaces
*How the user calibrates trust in this feature*

**[designing-for-uncertainty](./references/designing-for-uncertainty.md)**
The meta-frame. Classic UX is decision trees; AI UX is probability fields. Three layers worth designing for: source signal, confidence signal, and boundary signal. Read this one for almost every feature.

**[citations-and-sources](./references/citations-and-sources.md)**
Inline vs. footnoted, hover behavior, dataset vs. claim-level attribution. The hardest design problem is which claims to attach citations to, not how to render them.

**[confidence-and-hedging](./references/confidence-and-hedging.md)**
Score vs. badge vs. language. Numbers earn their place only when the user does something different at different values. Why traffic-light colors on confidence import moral weight that confidence doesn't carry.

**[refusal-and-fallback](./references/refusal-and-fallback.md)**
Refusals are a normal mode, not a failure state. Three categories — capability, policy, confidence — and what UX each needs. Why dead-end "I can't help with that" trains users to stop trying.

---

## Interaction shape
*What the user sees and does*

**[streaming-vs-batch](./references/streaming-vs-batch.md)**
Stream when the wait is long and the content is sequential. Batch when content is a unit. How to handle interruption and what not to make clickable mid-stream.

**[latency-and-loading](./references/latency-and-loading.md)**
Three thresholds (under 1s, 1–4s, over 4s) call for three different indicators. Skeleton vs. shimmer vs. status text. What users tolerate vs. abandon.

**[input-scaffolding](./references/input-scaffolding.md)**
The blank chat box is the worst onboarding in software. Chat vs. structured form vs. hybrid. Suggested prompts that demonstrate range. Surfacing constraints in the input instead of in error messages.

**[editable-output](./references/editable-output.md)**
Read-only AI output trains users to treat it as throwaway. When to make AI output directly editable, how to handle edits across regeneration, whether the model sees the user's edits in subsequent turns.

**[regenerate-and-undo](./references/regenerate-and-undo.md)**
Always preserve history. Silent replacement is the most common source of confusion in AI features. Placement by feature type, branching ("regenerate from here"), and why undo for AI actions is harder than it looks.

**[feedback-and-correction](./references/feedback-and-correction.md)**
Thumbs up/down is meaningful only if the system uses it and the user can see something happened. Three feedback modes — quality, granular correction, behavioral — and when each is worth designing for.

---

## Source and context
*What the AI is actually working from*

**[rag-and-retrieval-ux](./references/rag-and-retrieval-ux.md)**
The honesty of the retrieval is what users actually trust. Surfacing what was retrieved, what wasn't found, and how the user steers the search. Why hiding retrieval makes the AI feel like a black box.

**[memory-and-context](./references/memory-and-context.md)**
Three memory layers — conversation, user-level, team — and how to make memory inspectable and editable instead of invisibly surprising.

---

## Agentic behavior
*When the AI does, not just says*

**[agent-roles-and-boundaries](./references/agent-roles-and-boundaries.md)**
Four roles: tool, assistant, copilot, agent. Most teams undershoot. Defining scope, approval thresholds, reporting cadence, and stop conditions.

**[permissions-and-safety-friction](./references/permissions-and-safety-friction.md)**
Confirm before external send. Dry-run for batch operations. Undo window for reversible actions. Why generic "are you sure?" dialogs provide false safety.

---

## Entry points
*What the user sees before the AI has done anything*

**[empty-and-first-run](./references/empty-and-first-run.md)**
The first run is your demo. Mediocre output here calibrates trust for the entire relationship with the feature. Why decorative empty states cost adoption.

---

## How to use this index

**Scoping a new feature** — read `designing-for-uncertainty` first, then skim the descriptions above and pick the 4–6 patterns most relevant to your feature. Most AI features touch four to seven — don't try to design for all fifteen at once.

**Reviewing someone else's design** — use this as a critique checklist. Map the UI to the patterns above and check whether the designer handled the failure modes in each one.

**Learning AI UX** — start with the trust surfaces section. That's where most AI features fail first, and those four patterns inform everything below.

---

## What's not here yet

Five HAX guidelines aren't currently operationalized. Two are intentionally out of scope (G5, G6 — closer to content design and responsible AI). Three are candidates for future patterns:

- **G13** Learn from user behavior — when and how the AI should adapt based on observed behavior
- **G14** Update and adapt cautiously — UX for model updates, behavior changes, and capability shifts
- **G18** Notify users about changes — disclosing version updates and new capabilities

If one of these gaps showed up in real work, [open an issue](../../issues).
