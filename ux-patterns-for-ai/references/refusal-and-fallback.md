# Refusal and fallback

When the model can't or won't answer, the worst pattern is a flat "I can't help with that" with no next step. Always offer an out: a related thing the model *can* do, a way to reformulate, or a path to a human. Phrase refusals as the model's limitation, not the user's fault.

**Three categories of refusal, each needing different UX:**

1. **Capability refusal** — model doesn't have the information or skill. Example: "I don't have access to your calendar." Best response: name the limit, offer the closest adjacent thing, point to where the user can get the answer.

2. **Policy refusal** — request violates a content policy. Example: "I can't help generate that." Best response: be direct about *why* (without lecturing), and don't hide the refusal behind a vague error.

3. **Confidence refusal** — model could try but isn't sure. Example: "I'm not confident I can answer this accurately." Best response: hedge and try anyway, with a clear "this might be wrong" framing. Better than a flat refusal in most cases.

**Anti-patterns to flag:**
- "I can't help with that" with no follow-up suggestion. Dead-end UX trains users to stop trying.
- Vague refusals that don't say why. Users assume the worst — broken product, censorship, bias — and the actual cause is usually mundane.
- Long, lecture-y policy refusals. Direct + brief beats apologetic + verbose.
- Showing refusals as errors (red banner, "Error: Could not complete request"). Refusals are a normal mode, not a failure state — design them like answers, not like exceptions.

**What good looks like:** A refusal feels like a helpful colleague saying "I can't do that, but here's what might help." It names the limit, takes responsibility, and offers a next step.

**The decision the designer needs to make:** What's the user's next action when the model refuses, and is that action one click away?

**Revisit if:** Refusal flow has high abandonment (users hit a wall and leave) or repeat refusals on the same query (users are reformulating without success — your suggestions aren't useful enough).
