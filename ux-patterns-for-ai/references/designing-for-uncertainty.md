# Designing for uncertainty

Classic UX is built on decision trees: the user does X, the system does Y. Branches are binary; outcomes are predictable. AI features are built on probability fields: the system has a guess about what the user wants and a confidence level about its own answer, and the design has to make both of those legible without overwhelming the user.

The shift matters because trust transfers differently. In deterministic software, trust is mostly downstream of correctness — the button does what it says, the page loads, the form submits. In AI software, the model can be confident and wrong, can refuse for reasons it can't explain, can produce something that looks right and isn't. Correctness alone won't earn trust. Trust has to be designed onto the surface itself.

This pattern is the meta-frame for the rest of the patterns in this skill. If a feature involves AI, designing for uncertainty applies — even if you don't mention it explicitly, the feature's trust surfaces (confidence, citation, refusal, "I don't know") are doing this pattern's work.

**Three layers worth designing for:**

1. **Source signal** — where did this come from? Citations, retrieved documents, "based on your data." See `citations-and-sources.md` and `rag-and-retrieval-ux.md` for tactical guidance.

2. **Confidence signal** — how sure is the system? Numeric (only when it drives different action), badge (when there are 2-3 clear bands), or hedged in language. See `confidence-and-hedging.md`.

3. **Boundary signal** — what won't the system do, and why? Refusals, capability limits, "I don't have access to X." Boundary clarity is itself a trust signal, even when the answer is "no." See `refusal-and-fallback.md`.

**Anti-patterns to flag:**

- Designing the AI feature like deterministic software, then bolting trust signals on after launch when users complain. The trust surfaces have to be in v1; retrofitting them feels apologetic.
- Hiding uncertainty to make the product feel "magical." Users notice the moment the magic breaks, and the trust hit is bigger than the perceived polish gain.
- Stacking every trust signal at maximum density. Three good ones, well-placed, beat seven that compete for attention.

**The decision the designer needs to make:** Which kinds of uncertainty does this feature surface (source, confidence, boundary), and which is the most important for *this* user's *this* task?

**Revisit if:** Users describe the AI as "weirdly confident" (uncertainty isn't surfaced honestly enough) or "I never know if it's right" (uncertainty is surfaced but not in a way that helps the user act).
