# Agent Roles and Boundaries

When the AI is doing something, not just saying something, the design problem changes. You're designing a colleague, not a conversation. The user has to know what the colleague will do unsupervised, what it'll check before doing, and what's permanently out of scope.

Get this wrong and either the agent is useless (asks permission for everything) or unsettling (acts irreversibly with no preview).

---

## Four roles

**Tool** — AI runs only when the user explicitly asks. No autonomy, no scheduled actions. Good default for high-stakes work and users new to AI.

**Assistant** — AI runs when asked, but offers proactive suggestions in-context. The user accepts or dismisses each one. Good for content creation and research.

**Copilot** — AI works alongside the user continuously, often editing the same artifact. The user reviews regularly but doesn't approve every action. Good for code and document workflows.

**Agent** — AI runs autonomously toward a goal, takes actions in external systems, and reports back. User reviews outcomes, not steps. Good for batch operations and well-bounded tasks.

The role you pick is the most important design decision in an agentic feature — every other pattern downstream (permissions, undo, latency, reporting) cascades from it. Most teams undershoot: they design something autonomous because "AI," but the actual job wants a tool, and the result feels heavy and intrusive.

---

## Boundaries the designer controls

**Scope** — which surfaces, files, accounts, or actions the agent can touch. Make this visible and editable, not buried in settings.

**Approval thresholds** — which actions require human confirmation (high-risk, irreversible) vs. which the agent does freely (low-risk, reversible). See [`permissions-and-safety-friction.md`](./permissions-and-safety-friction.md).

**Reporting cadence** — when and how the agent communicates progress. Tools and assistants report inline; copilots report on review; agents report on completion.

**Stop conditions** — how the user halts the agent mid-execution. There must be one, and it must be discoverable in under five seconds.

---

## The decision

Which of the four roles is the right shape for this feature, and what does the user need to see to keep the agent's behavior predictable?

**Revisit if:** Users disable the agent (you went too autonomous) or routinely override it (the role is right but the boundaries are wrong).

---

## Anti-patterns

- "Magic agent" framing where autonomy is sold as a feature instead of disclosed as a contract. Users want predictability, not surprise.
- Agents whose scope expands silently over time. Expansion without disclosure breaks trust permanently.
- No visible "what the agent is doing right now" surface for autonomous flows. Users assume the worst when the agent is silent.
- Treating role as a setting the user can toggle freely. The role shapes the entire feature; toggling it should be rare and well-onboarded.

---

*HAX guidelines: G1, G10, G16, G17*
