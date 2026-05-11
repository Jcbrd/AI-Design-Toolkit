# RAG and Retrieval UX

When the AI is reading something to answer — a knowledge base, an uploaded document, internal docs — the design problem becomes: how does the user sense whether the AI looked at the right things?

RAG is most AI features in disguise: every chatbot over a corpus, every "ask your documents" feature, every internal search tool with an answer layer. The honesty of the retrieval is what users actually trust. If the model is working from the wrong sources, the prettiest answer is still wrong.

---

## Four surfaces designers control

**What was retrieved** — show the source documents (or chunks) the AI actually used. The top 3–5 is usually enough for the user to sense-check.

**Why those, not others** — when retrieval is doing something non-obvious (recency boost, document-type filter, semantic similarity), surface it. "Searching only docs from the last 90 days" beats silent assumptions.

**What wasn't found** — empty retrieval is information. "I didn't find anything in your handbook about this — answering from general knowledge" is a real trust move that most products skip.

**How the user steers** — let users narrow the search before the answer (filter by source, date, collection, author). The "I want to talk to this set of documents" need is real and almost universally underdesigned.

---

## The decision

What does the user need to see about the retrieval to trust — or correctly distrust — the answer that follows?

**Revisit if:** Users complain the AI "doesn't see" obvious documents (retrieval is failing silently) or don't trust answers despite good retrieval (retrieval isn't surfaced prominently enough).

---

## Anti-patterns

- Showing retrieval results as a flat list with no relevance signal. Users can't tell which chunk drove the answer.
- Hiding retrieval entirely and presenting only the answer. Users can't catch retrieval failures, and the AI feels like a black box.
- Confident answers from low-quality or no retrieval. If the system retrieved one document with marginal relevance, the answer should hedge.
- Letting the user upload documents but not letting them inspect what was indexed or how it was chunked. They'll discover misses by accident.

---

*HAX guidelines: G4, G11*
