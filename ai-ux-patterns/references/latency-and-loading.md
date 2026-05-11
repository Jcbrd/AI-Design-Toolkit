# Latency and Loading

Three thresholds shape the right indicator:

**Under 1 second** — no indicator. Anything you add here is friction.

**1–4 seconds** — skeleton or shimmer. The shape of the answer-to-come tells the user the system understood and is working.

**Over 4 seconds** — status text describing what's happening. "Searching your documents... Found 12 results... Drafting reply..." Users tolerate long waits when they can see progress.

**Over 30 seconds** — always have visible progress, even if coarse ("Still working — this can take up to a minute for complex queries"). Users assume failure and refresh without it.

Indeterminate spinners over 10 seconds feel broken even when they aren't. The bar is higher for AI features because users have been trained by faster apps that "thinking" should resolve quickly.

---

## Design the wait, not just the loader

What can the user do, read, or prepare while they wait? In a chat, they can re-read the prompt or scroll up. In a generative tool, they could see the prompt being parsed into structured intent. The wait is content too.

---

## The decision

What's the realistic latency distribution for this feature, and what's the right indicator at p50, p95, and p99?

**Revisit if:** Users abandon during the wait (the indicator isn't engaging enough, or latency is genuinely too long) or users complain about "stuck" loading (progress information is too vague at long durations).

---

## Anti-patterns

- Static spinner with no progress information for 30+ seconds. Users assume failure.
- "Loading..." text that never changes. Users learn to ignore it.
- Optimistic UI (showing a fake answer that gets replaced). Users notice the swap, and the trust hit is bigger than the perceived speed gain.
- Skeleton that doesn't match the actual answer shape. If the skeleton implies a paragraph and the answer is a table, the swap is jarring.

---

*HAX guidelines: G3*
