# UX Patterns for AI — full index

Fifteen tactical patterns for designers shipping AI features. Each operationalizes one or more Microsoft HAX guidelines and adds the specific UI choices, copy, and failure modes that strategic frameworks don't go into.

Each pattern has a **plain-language tagline** so the index reads cleanly whether you're a designer (and already know the term) or a PM, exec, or recruiter (who shouldn't have to Google "RAG" to follow along). The italic line under each is the punchy designer take.

Grouped below by what the designer is asking when they reach for a pattern, not by HAX phase. See `references/_frameworks.md` for the HAX mapping and coverage analysis.

---

## Trust surfaces — how the user calibrates trust in this feature

### designing-for-uncertainty — *how to handle "the AI might be wrong"*

*The meta-frame. Classic UX is decision trees; AI UX is probability fields. Trust transfers differently.*

The foundational pattern. Trust in deterministic software is downstream of correctness; in AI, correctness alone doesn't earn trust. Three layers worth designing for: source signal (where did this come from), confidence signal (how sure is the system), boundary signal (what won't the system do, and why).

→ [`references/designing-for-uncertainty.md`](references/designing-for-uncertainty.md)

### citations-and-sources — *where the AI's claims come from*

*Cite at the level that matches the user's relationship to the sources.*

Inline vs. footnoted citations, hover behavior, source attribution at the dataset level vs. the claim level. The hardest design problem is which claims to attach citations to, not how to render them.

→ [`references/citations-and-sources.md`](references/citations-and-sources.md)

### confidence-and-hedging — *how the AI signals when it's unsure*

*Numbers earn their place only when the user does something different at different values.*

Score vs. badge vs. language. When numeric confidence backfires. Why traffic-light colors on confidence import moral weight that confidence doesn't carry.

→ [`references/confidence-and-hedging.md`](references/confidence-and-hedging.md)

### refusal-and-fallback — *what happens when the AI can't or won't help*

*Refusals are a normal mode, not a failure state. Design them like answers, not exceptions.*

Three categories of refusal — capability, policy, confidence — and what UX each needs. Why dead-end "I can't help with that" trains users to stop trying.

→ [`references/refusal-and-fallback.md`](references/refusal-and-fallback.md)

---

## Interaction shape — what the user sees and does

### streaming-vs-batch — *should the answer appear all at once or as it's typed?*

*Stream when the wait is long and the content is sequential. Batch when content is a unit.*

When streaming earns its complexity, how to handle interruption, what NOT to make clickable mid-stream.

→ [`references/streaming-vs-batch.md`](references/streaming-vs-batch.md)

### latency-and-loading — *designing the wait*

*Three thresholds (under 1s, 1–4s, over 4s) call for three different indicators.*

Skeleton vs. shimmer vs. status text vs. coarse progress. What users tolerate vs. abandon.

→ [`references/latency-and-loading.md`](references/latency-and-loading.md)

### input-scaffolding — *helping the user know what to ask*

*The blank chat box is the worst onboarding in software.*

Chat vs. structured form vs. hybrid. Suggested prompts that demonstrate range. Surfacing constraints in the input instead of in error messages.

→ [`references/input-scaffolding.md`](references/input-scaffolding.md)

### editable-output — *letting the user fix the AI's work*

*Read-only AI output trains users to treat it as throwaway.*

When to make AI output directly editable, how to handle edits across regeneration, whether the model sees the user's edits in subsequent turns.

→ [`references/editable-output.md`](references/editable-output.md)

### regenerate-and-undo — *letting the user try again or take it back*

*Always preserve history. Silent replacement is the most common source of confusion in AI features.*

Placement of the regenerate button by feature type, branching ("regenerate from here"), and why undo for AI actions is harder than it looks.

→ [`references/regenerate-and-undo.md`](references/regenerate-and-undo.md)

### feedback-and-correction — *thumbs-up/down and other signals back to the model*

*Thumbs up/down is meaningful only if the system actually uses it and the user can see something happened.*

Three feedback modes — quality, granular correction, behavioral — and when each is worth designing for.

→ [`references/feedback-and-correction.md`](references/feedback-and-correction.md)

---

## Source and context — what the AI is actually working from

### rag-and-retrieval-ux — *showing which documents the AI looked at*

*The honesty of the retrieval is what users actually trust. The model's reasoning is downstream.*

Surfacing what was retrieved, what wasn't found, why those sources and not others, and how the user steers the search. Why hiding retrieval makes the AI feel like a black box.

→ [`references/rag-and-retrieval-ux.md`](references/rag-and-retrieval-ux.md)

### memory-and-context — *what the AI remembers about you*

*Make a "what the AI knows about you" surface. Pull state updates out of free-text chat.*

Three memory layers — conversation, user-level, team — and how to make memory inspectable and editable instead of invisibly surprising.

→ [`references/memory-and-context.md`](references/memory-and-context.md)

---

## Agentic behavior — when the AI does, not just says

### agent-roles-and-boundaries — *what the AI can do on your behalf*

*Four roles: tool, assistant, copilot, agent. Most teams undershoot — picking "agent" when the use case wants a "tool."*

Defining scope, approval thresholds, reporting cadence, and stop conditions. Why "magic agent" framing breaks trust, and what predictability looks like instead.

→ [`references/agent-roles-and-boundaries.md`](references/agent-roles-and-boundaries.md)

### permissions-and-safety-friction — *when to make the user confirm before the AI acts*

*Confirm before external send. Dry-run for batch operations. Undo window for reversible actions. No undo for irreversible — design the dialog instead.*

The friction-vs-agency tension. When to use confirmation dialogs vs. undo toasts vs. dry-run previews. Why generic "are you sure?" dialogs provide false safety.

→ [`references/permissions-and-safety-friction.md`](references/permissions-and-safety-friction.md)

---

## Entry points — what the user sees before the AI has done anything

### empty-and-first-run — *what to show before there's anything to show*

*The first run is your demo. Mediocre output here calibrates trust for the entire relationship with the feature.*

What to show before the user has used the feature. Why suggested prompts that demonstrate range earn their space. Why decorative empty states cost adoption.

→ [`references/empty-and-first-run.md`](references/empty-and-first-run.md)

---

## How to read this index

**If you're scoping a new AI feature:** read `designing-for-uncertainty` first (the meta-frame), then skim the italic take lines above and pick the four to six patterns most relevant to your feature. Most AI features touch four to seven — don't try to design for all fifteen at once.

**If you're reviewing someone else's design:** use the index as a critique checklist. Map the UI you're reviewing to the patterns above and check whether the designer handled the "Watch for" cases in each one.

**If you're learning AI UX:** start at the top with the trust surfaces section. That's where most AI features fail first, and the four patterns there inform everything below.

**If you're not a designer:** the plain-language tagline under each pattern name should be enough to follow along. The italic line under that is the designer's punchy take; you can skip it without losing the point.

---

## What's not in here yet

Five HAX guidelines aren't currently operationalized as patterns. Two are intentionally out of scope (G5 match social norms, G6 mitigate biases — closer to content design and responsible AI). Three are candidates for future patterns based on real-use feedback:

- **G13 Learn from user behavior** — when and how the AI should adapt based on observed behavior
- **G14 Update and adapt cautiously** — UX for model updates, behavior changes, and capability shifts
- **G18 Notify users about changes** — disclosing version updates, behavior changes, and new capabilities

If you've used the skill in real work and one of these gaps showed up, [open an issue].

---

## Contributing

Built on Microsoft HAX (Amershi et al., 2019). If you've used this on a real project and have a pattern to add, an edit to make, or a wrong take to argue with, open an issue or contact me.

— Jacine
