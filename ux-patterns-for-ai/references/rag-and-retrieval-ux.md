# RAG and retrieval UX

When the AI is reading something to answer (a knowledge base, a document the user uploaded, the company's internal docs), the design problem becomes: how does the user sense whether the AI looked at the right things? Retrieval-augmented generation (RAG) is most AI features in disguise — every chatbot over a corpus, every "ask your documents" feature, every internal search tool with an answer layer.

The honesty of the retrieval is what users actually trust. The model's reasoning is downstream — if it's working from the wrong sources, the prettiest answer is still wrong.

**Four surfaces designers control:**

1. **What was retrieved** — show the source documents (or chunks) the AI actually used. Doesn't have to be every document; the top three to five is usually enough for the user to sense-check.

2. **Why those, not others** — when retrieval is doing something non-obvious (recency boost, document-type filter, semantic similarity), surface it. "Searching only docs from the last 90 days" beats silent assumptions.

3. **What wasn't found** — empty retrieval is information. "I didn't find anything in your handbook about this — answering from general knowledge" is a real trust move that most products skip.

4. **How the user steers** — let users narrow the search before the answer (filter by source, by date, by collection, by author). The "I want to talk to *this* set of documents" need is real and almost universally underdesigned.

**Anti-patterns to flag:**

- Showing retrieval results as a flat list with no relevance signal. Users can't tell which retrieved chunk drove the answer, and trust drops.
- Hiding retrieval entirely and presenting only the answer. Users can't catch retrieval failures, and you've made the AI feel like a black box that may or may not have read the right thing.
- Confident answers from low-quality or no retrieval. If the system retrieved one document with marginal relevance, the answer should hedge — not match the confidence of an answer with five strong sources.
- Letting the user upload documents but not letting them inspect what was indexed or how it was chunked. They'll discover misses by accident, and they'll stop trusting the upload.

**The decision the designer needs to make:** What does the user need to see about the retrieval to trust (or correctly distrust) the answer that follows?

**Revisit if:** Users complain the AI "doesn't see" obvious documents (retrieval is failing silently — surface what's being searched and what's being missed) or users don't trust answers despite good retrieval (retrieval isn't surfaced enough — make it more prominent).
