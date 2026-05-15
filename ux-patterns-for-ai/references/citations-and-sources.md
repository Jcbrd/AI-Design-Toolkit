# Citations and sources

Inline citations (`[1]`, `[Source]`) work when sources are real, stable URLs the user might actually click. They fail when sources are internal IDs, when links rot, or when there are seven citations per sentence and no one can tell which claim each supports. Default to footnoted citations with hover previews unless the product is explicitly research-oriented (legal research, academic search, journalism tools).

**Defaults by product type:**
- Consumer chat over web sources: footnoted citations, hover preview, max one per claim.
- Internal docs / RAG over enterprise content: source chips below the answer rather than inline. Internal users care more about "which doc" than "which sentence."
- Research / legal / journalism: inline citations, possibly multiple per claim. The audience reads citations as the work product.

**The hardest design problem:** not *how* to show citations, but *which claims* to attach them to. Over-citation reads as defensive ("I'm not sure, here's a cover"). Under-citation reads as confident hallucination. Aim for citations on factual claims that the user might reasonably want to verify; skip them on transitions, paraphrases of the user's own input, or generally accepted background.

**Anti-patterns to flag:**
- Citations to internal source IDs the user can't actually click ("Source: doc_a8f3c"). Either resolve to a meaningful link/title or attribute at the category level.
- Showing citations when the model can't reliably cite. If retrieval is unreliable, "Based on your documents" beats fake-precise citations to the wrong source.
- Hover previews that load on hover and take 2+ seconds. Either preload or use a static excerpt.

**The decision the designer needs to make:** What's the user's relationship to the sources — verifying, browsing, or ignoring? Cite at the level that matches.

**Revisit if:** Users never click citations (they're decorative; consider category-level attribution instead) or users complain about wrong/missing sources (retrieval problem upstream of UX, but the UX is amplifying it).
