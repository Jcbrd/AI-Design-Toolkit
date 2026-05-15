# Memory and context

What does the AI remember between turns? Between sessions? Between users on the same team? Memory is the most under-designed dimension of AI features and the one that creates the most user surprise — both delight ("oh, it remembers I prefer concise answers") and dread ("wait, why does it know that about me?"). Operationalizes HAX G12 (Remember recent interactions).

The honest design question: what should the AI know, and what should the user be able to see, edit, or forget?

**Three memory layers, designed separately:**

1. **Conversation memory** — what the AI carries within a single session. Default behavior in chat-style products; usually invisible to the user. Surface this when conversations get long enough that the user starts wondering ("does it still remember what I said five messages ago?").

2. **User-level memory** — what the AI remembers about the user across sessions. Preferences, projects, history. Big trust implications: people get uncomfortable when the AI knows "too much" without disclosure. Make this inspectable and editable in a clear, dedicated surface — not buried in settings.

3. **Shared / team memory** — what the AI knows about the user's organization (docs, teammates, decisions). Often pulled via RAG. The privacy boundary here matters: a user shouldn't be surprised by what the AI knows about a colleague, or what a colleague might learn from the AI about them.

**Anti-patterns to flag:**

- Invisible memory that surfaces unexpectedly. ("How did it know I'm allergic to nuts?") Even helpful memory feels invasive when undisclosed.
- Memory the user can't inspect or edit. Trust requires the option to see and change what the AI knows about you.
- Conflating memory layers. "It remembers our conversation" implies session memory; "it remembers you" implies user-level memory; the gap between those is where most expectation mismatches live.
- Long-term memory presented as a feature without a corresponding "forget" affordance.

**The decision the designer needs to make:** What's the smallest amount of memory this feature needs to be useful, and how does the user see and control it?

**Revisit if:** Users are surprised by what the AI knows (memory isn't disclosed clearly enough) or feel like the AI doesn't remember anything useful (you over-conservatized — add user-level memory with disclosure).
