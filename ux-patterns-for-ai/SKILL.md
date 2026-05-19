
---
 
# UX Patterns for AI
 
Designers shipping AI features make the same eight to ten decisions on every project: streaming or batch, how to surface confidence, what to do when the model refuses, how to handle regeneration, where citations live. This skill maps a feature concept to the patterns that matter for it and surfaces the failure modes most teams hit.
 
## Frameworks this skill builds on
 
The patterns in this skill are tactical — they answer "what specifically to ship" — and they sit on top of strategic guidelines from established research:
 
- **Microsoft HAX (Human-AI Interaction) guidelines** by Amershi et al. (CHI 2019) are the primary anchor. HAX defines 18 design guidelines for AI products at the strategic level ("Make clear what the system can do," "Convey the consequences of user actions"). This skill operationalizes HAX — mapping each pattern to one or more guidelines and adding the specific UI choices, copy, and failure modes HAX doesn't go into.
- **Google PAIR Guidebook** and **NN/g's AI usability heuristics** inform several patterns, especially around input scaffolding, error recovery, and the philosophy of designing for uncertainty.
See `_frameworks.md` for the full pattern-to-HAX mapping, the guidelines not yet operationalized (kept honest about gaps), and citation info.
 
## When to use
 
Use this skill any time the user is making AI feature design decisions — early scoping, design critique, spec review, or post-launch debugging. Don't wait for them to say "pattern." If they describe an AI feature and ask "how should this work" or "what are we missing," map it to patterns.
 
## How to use
 
1. **Get the feature description.** One or two sentences is enough. If the user gave less, ask: "What's the feature, who's the user, and where does it live in the product?" Don't go deeper than that — the patterns are the value, not a full discovery interview.
2. **Map the feature to its workflow phases.** Most AI features follow a sequence: user provides input → AI generates output → user refines or explores. Identify which phases matter for this feature. Some features skip phases (e.g., a summarizer might skip "Letting them steer").
3. **For each phase, identify the critical design decision.** Read the relevant pattern reference files (each lives in `references/<pattern-name>.md`). Extract the specific decision the designer needs to make, not all possible patterns. If a pattern doesn't answer a real question for this feature, skip it.
4. **Write the TL;DR.** Two to three sentences naming the central tension and the highest-leverage decisions. The designer should be able to stop reading there if they only need direction.
5. **Write one detail block per phase** using the format below. Each block is focused on what the user is doing, and patterns are embedded naturally within it rather than listed separately.
6. **End with "The hard part" summary** — two to three sentences naming the central tension. Designers steal this language for design reviews, so make it useful.
## Output format
 
Use this exact structure. Organize by the feature's workflow phases, not by design principle categories. This keeps the output focused on what the user is doing and reduces cognitive load.
 
```
### [Feature in one phrase]
 
[2-3 sentence TL;DR. Name the central tension and the 2-3 highest-leverage decisions for this feature. The designer should be able to stop reading here if they only need direction. Plain language — no jargon in the TL;DR.]
 
---
 
#### [Phase name — what the user is doing here]
 
*[One-line italic "take" — the punchy version of your recommendation, ~12-20 words. The designer scanning three to five blocks should be able to read each take and decide which to dig into.]*
 
**Decide:** [The question the designer needs to answer. One sentence.]
 
**Recommendation:**
- [If the recommendation has 2+ distinct actions, USE BULLETS. Each bullet is one specific action, naming a UI element / copy / threshold where possible.]
- [Multiple bullets when there are multiple actions. Don't run them together with semicolons or "and also" / "but also" / parenthetical asides.]
- [If only one action, write it as a single sentence (no bullet) — but most phases have 2-4 distinct actions.]
 
**Watch for:** [What teams ship that breaks. 1-2 short sentences, max ~30 words.]
 
**Revisit if:** [The signal that this decision was wrong. One short clause, max ~20 words.]
 
[Repeat the above block for each phase that matters for this feature. Typically 3-5 phases per feature.]
 
---
 
**The hard part:** [Two or three sentences naming the central tension. This is the designer's elevator pitch in their next design review.]
```
 
Notes on the format:
- The TL;DR is the most important part. Designers under time pressure read only it; make sure it earns its place by naming the tension specifically (not "trust matters"). Use plain language here — no jargon — so a PM or non-designer reading the output gets the central point.
- Each phase represents a moment in the user's workflow where the designer needs to make a decision. Name the phase by what the user is doing, not by the pattern name. Good: "Showing concepts — how to present them as explorations." Bad: "Designing for uncertainty — the pattern."
- The italic "take" line at the top of each phase block is the second-most-important part. Designers scan it first to decide whether to read the full block. Aim for ~12-20 words and treat it as the line a designer would say out loud at a whiteboard.
- Inside detail blocks, every field is on its own paragraph with a blank line above and below. Never run "Decide:", "Recommendation:", "Watch for:", and "Revisit if:" together as a single paragraph — that's the failure mode that makes the output read as a wall of text.
- Recommendations with 2+ distinct actions MUST use bullets. The dense-paragraph fallback is the most common output failure; bullets force the model to enumerate actions instead of stringing them together with parentheticals and "but also" clauses.
- "Watch for" replaces older "Failure mode" language because it sounds more like a designer at a whiteboard and less like a reference textbook. Same content, warmer voice.
- Length guideline per phase block (excluding labels): italic take ~15 words, decide ~20 words, recommendation ~50-100 words across bullets, watch for ~25 words, revisit if ~15 words. A full phase block lands around 130-180 words. If yours is over 250, it's too dense — split into bullets, cut parentheticals, and shorten.
- Do NOT call out which patterns are "must-haves" or "nice-to-haves." Instead, focus on the decision at hand and why it matters for this feature. If a pattern doesn't answer a real question, leave it out entirely rather than listing it and explaining why it's a "consider."
## Bad and good output examples
 
The single most common failure is the model collapsing the detail block into one dense paragraph. Here's what to avoid and what to ship instead.
 
### Don't write this (framework-first, repetitive, heavy):
 
> **Must address**
> - Designing for uncertainty (how to handle "the AI might be wrong")
> - Input scaffolding (helping the user know what to ask)
> - Editable output (letting the user fix the AI's work)
>
> **Should address**
> - Regenerate and undo (letting the user try again or take it back)
> - Memory and context (what the AI remembers about you)
> 
> #### Designing for uncertainty — how to handle "the AI might be wrong"
>
> *Frame brand concepts as directions to iterate on, not fixed outputs.*
>
> [detail block here...]
 
Why this is bad: Opens with framework categories (Must/Should) before the user knows what the feature is or what to focus on; repeats "designing for uncertainty" as both a category label and a section heading; makes the reader hunt for the actual decision buried in the detail block.
 
### Write this instead (phase-first, concrete, scannable):
 
> #### Setting up the discovery questions
>
> *Start with 3-4 foundational questions in plain language, not jargon.*
>
> **Decide:** Do you start with open-ended questions, visual pickers, or a hybrid? How do you avoid overwhelming users while still gathering detail?
>
> **Recommendation:**
> - Begin with 3-4 foundational questions in plain language: "If your brand were a person, what would they be like?" (freeform text, not jargon)
> - Layer in a visual picker after one or two questions — color moods, typography samples, competitor examples
> - Add conditional follow-ups based on their answers: if they pick "playful," ask "Playful like Mailchimp or Duolingo?"
> - After ~4-5 questions, show a "Preview" of what you've learned so they can edit it before generating
>
> **Watch for:** Asking ten questions upfront (users abandon); pickers with no freeform option (advanced users feel boxed in).
>
> **Revisit if:** Users skip questions or leave them blank; you're asking about things they don't actually care about.
 
Why this works: Leads with what the user is doing (answering discovery questions), not a pattern name; the italic take gives a 5-second scan; fields are separated so the eye doesn't collapse them; bullets enumerate distinct actions instead of stringing them together with "also" and parentheticals.
 
## Voice
 
Write like someone who has been burned by these patterns, not like someone who read about them. Specific examples beat principles every time:
 
- Weak: "Confidence indicators help users calibrate trust."
- Strong: "Showing a 73% confidence score sounds precise but users round it to 'might be wrong.' If you can't act differently at 73 vs. 91, hedge in language ('I'm not sure, but...') instead of a number."
Avoid AI-design clichés ("delight," "magic," "reduce cognitive load," "leverage," "unlock"). Name specific UI elements, specific copy, specific anti-patterns. Where there's research to point to, name it briefly. Where there's only opinion, own that with "I'd lean toward X because Y."
 
The reason: this skill is read by designers who can tell within ten seconds whether the writer has shipped AI features or just read about them. Generic advice gets ignored; specific advice gets quoted in design reviews.
 
## Pattern index
 
The full pattern set lives in `references/`. Read only the files for the patterns you'll discuss in the output. Each file is short — a paragraph or two — so reading two or three is cheap.
 
The first pattern, **designing-for-uncertainty**, is foundational — it's the meta-frame that the other patterns operationalize. Read it for almost every feature even when you don't write a block about it explicitly; it informs which trust surfaces matter most.
 
Each pattern has a plain-language tagline in parentheses. Use the tagline whenever you reference a pattern — designers know what "RAG" means, but a PM or non-designer reading the output shouldn't have to guess.
 
1. **designing-for-uncertainty** *(how to handle "the AI might be wrong")* — the binary→probabilistic shift; trust as a designed surface; source/confidence/boundary signals
2. **streaming-vs-batch** *(should the answer appear all at once or as it's typed?)* — when to stream output, how to handle interruption, what NOT to make clickable mid-stream
3. **citations-and-sources** *(where the AI's claims come from)* — inline vs. footnoted, hover behavior, dead-link handling, when citations hurt
4. **rag-and-retrieval-ux** *(showing which documents the AI looked at)* — surfacing what was retrieved, what wasn't, and how the user steers the search
5. **confidence-and-hedging** *(how the AI signals when it's unsure)* — score vs. badge vs. language; when confidence indicators backfire
6. **refusal-and-fallback** *(what happens when the AI can't or won't help)* — "I don't know" UX; how to avoid dead-ends; offering an out
7. **regenerate-and-undo** *(letting the user try again or take it back)* — placement, labeling, history surfacing, "regenerate from here"
8. **latency-and-loading** *(designing the wait)* — skeleton vs. shimmer vs. status text; what users tolerate vs. abandon
9. **input-scaffolding** *(helping the user know what to ask)* — chat vs. form vs. hybrid; suggested prompts; constraint surfacing
10. **editable-output** *(letting the user fix the AI's work)* — when to make AI output directly editable; tracking user edits; re-running with edits in context
11. **memory-and-context** *(what the AI remembers about you)* — what the AI remembers (session, user, team); inspectable and editable memory surfaces
12. **feedback-and-correction** *(thumbs-up/down and other signals back to the model)* — thumbs up/down vs. granular correction vs. behavioral signals; when each is worth designing
13. **permissions-and-safety-friction** *(when to make the user confirm before the AI acts)* — confirm-before-action, dry-run, undo windows for agentic features
14. **agent-roles-and-boundaries** *(what the AI can do on your behalf)* — tool/assistant/copilot/agent; scope, approval thresholds, reporting cadence, stop conditions
15. **empty-and-first-run** *(what to show before there's anything to show)* — what to show before the user has used the feature; the "what can I ask?" problem
## Patterns NOT to recommend
 
A few patterns get hyped but rarely earn their place. Avoid suggesting:
- Personality / "AI as character" framing unless the brand explicitly calls for it
- Animated typing dots that aren't tied to actual streaming
- Confidence percentages without an action that changes at different thresholds
- "Magic" or "✨" language in copy
If the user asks about these directly, explain why they often hurt more than they help. The reason to flag this list explicitly: AI feature design is full of cargo-culted patterns that ship because they look like other AI products, not because they work.
 
## Edge cases
 
**The user describes a non-AI feature.** Tell them the skill is for AI features specifically and ask if they meant to invoke a different design skill. Don't try to apply the patterns to non-AI UX — the recommendations won't be specific or useful.
 
**The user gives a one-word description ("chatbot").** Ask one clarifying question: who's the user and what's the job-to-be-done. Then proceed.
 
**The user asks about a pattern not in the index.** If it's a real AI UX pattern (e.g., multi-turn correction, RAG attribution, tool-call previews), respond from general design knowledge but flag that it's outside the indexed set. Don't fabricate a reference file.
 
**The feature is agentic (takes actions, not just generates content).** Permissions — whether the user confirms before the AI acts — becomes a critical early phase. Lead with that decision. Agentic features fail catastrophically when permissions are wrong; they fail gently when content patterns are undesigned.
