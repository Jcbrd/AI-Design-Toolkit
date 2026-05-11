# Designing for Uncertainty

Classic UX is built on decision trees: the user does X, the system does Y. AI features are built on probability fields: the system has a guess about what the user wants and a confidence level about its own answer, and the design has to make both legible without overwhelming the user.

Trust transfers differently in AI software. The model can be confident and wrong, can refuse for reasons it can't explain, can produce something that looks right and isn't. Correctness alone won't earn trust — trust has to be designed onto the surface itself.

This is the meta-frame for the rest of the patterns in this skill. If a feature involves AI, designing for uncertainty applies — even when you don't mention it explicitly.

---

## Three layers worth designing for

**Source signal** — where did this come from? Citations, retrieved documents, "based on your data." See [`citations-and-sources.md`](./citations-and-sources.md) and [`rag-and-retrieval-ux.md`](./rag-and-retrieval-ux.md).

**Confidence signal** — how sure is the system? Numeric (only when it drives different action), badge (when there are 2–3 clear bands), or hedged in language. See [`confidence-and-hedging.md`](./confidence-and-hedging.md).

**Boundary signal** — what won't the system do, and why? Refusals, capability limits, "I don't have access to X." Boundary clarity is itself a trust signal, even when the answer is no. See [`refusal-and-fallback.md`](./refusal-and-fallback.md).

---

## The decision

Which kinds of uncertainty does this feature surface — source, confidence, boundary — and which is most important for this user's task?

**Revisit if:** Users describe the AI as "weirdly confident" (uncertainty isn't surfaced honestly enough) or "I never know if it's right" (uncertainty is surfaced but not in a way that helps the user act).

---

## Anti-patterns

- Designing the AI feature like deterministic software, then bolting trust signals on after launch. The trust surfaces have to be in v1 — retrofitting them feels apologetic.
- Hiding uncertainty to make the product feel "magical." Users notice the moment the magic breaks, and the trust hit is bigger than the perceived polish gain.
- Stacking every trust signal at maximum density. Three good ones, well-placed, beat seven that compete for attention.

---

*HAX guidelines: G2, G11*
