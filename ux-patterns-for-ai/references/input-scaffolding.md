# Input scaffolding

The blank chat box is the worst onboarding in software. Users freeze, type "hi," get a generic response, and decide the product doesn't work. Three scaffolds reliably help:

1. **Suggested prompts**: 3–5 specific examples that demonstrate the model's actual range. Not "Tell me a joke" — something product-specific that produces a visibly impressive answer. Suggested prompts double as a tutorial for what the AI can do.

2. **Structured forms that compile to a prompt**: especially good for narrow use cases (cold email generator, SQL builder, design brief writer). The user fills in fields; you turn it into a prompt under the hood. Lower freedom, higher reliability, less anxiety for new users.

3. **Hybrid (structured-then-freeform)**: user starts with a small form (target, tone, length), then drops into a chat to refine. Best of both worlds for medium-complexity tasks.

**Suggested prompts are not "Ask me anything" prompts.** They have to be specific to the product and produce strong results. Generic examples set wrong expectations and undersell the product. Test them — if your top three suggestions return mediocre answers, fix the prompts or the underlying model behavior before shipping.

**Constraints belong in the input, not in error messages.** If the model can only handle PDFs under 50 pages, say so before upload — don't fail after the user waits 30 seconds for parsing. If queries longer than 2,000 characters get truncated, show the count and the limit.

**Anti-patterns to flag:**
- Empty chat box with placeholder "Ask me anything." Sets up a guess-the-model's-capabilities game the user always loses.
- Suggested prompts that don't actually work well. The first run calibrates trust for the entire relationship; mediocre demos do permanent damage.
- Structured form with no escape hatch to freeform. Real users always have a use case the form didn't anticipate.
- Hidden constraints (file size, length, language) revealed only on error. Surface them in the input.

**The decision the designer needs to make:** What does the user know about what the AI can do before they type anything?

**Revisit if:** First-session abandonment is high (users tried, didn't get value, left — usually the input experience, not the model) or queries cluster around a small set of patterns (the form might do better than chat for those patterns).
