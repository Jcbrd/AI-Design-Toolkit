# Regenerate and undo

Regenerate buttons live in three places — next to the answer, in a hover toolbar, or in a menu — and the choice depends on how often regeneration is the expected next action.

**Placement by feature type:**
- **Chat**: hover toolbar above each AI message. Regeneration is common but not the primary action; visible-on-hover keeps the rail clean.
- **One-shot generation** (image, draft email, summary): inline button below the answer, equal weight to "use this." Regeneration is the expected next step if the first try misses.
- **Embedded suggestions** (autocomplete, inline rewrites): a small "↻" affordance attached to the suggestion. Don't disrupt flow.

**Always preserve history.** When regenerating, show the previous response collapsed or in a "previous version" toggle. Silent replacement is the most common cause of "wait, where did the thing go?" support tickets in AI features. Users want to compare and pick.

**"Regenerate from here" (branching)** is powerful for long outputs but adds UI weight. Only ship it if users are routinely scrolling back to mid-response. Otherwise, full regeneration is enough.

**Undo is harder than it looks.** If the AI took an action (sent an email, modified a file, made a database change), undo needs a real reversal flow — not just visual rollback. Design the reversal at the same time as the action; bolting it on later usually fails because the data layer isn't reversible.

**Anti-patterns to flag:**
- Regenerate button next to a "Send" or "Submit" button, with no visual separation. Misclicks during streaming send the wrong thing.
- Regenerate that loses the user's edits to the previous response. Either preserve edits or warn before discarding.
- "Undo" labels on actions that aren't actually reversible. Either make undo real or use different language ("Discard draft" vs. "Undo send").

**The decision the designer needs to make:** How often is regeneration the next action, and what gets lost when it happens?

**Revisit if:** Users regenerate the same prompt repeatedly without modifying it (the model can't improve on retry — fix prompts or seed variation) or users complain about losing edits (history isn't being preserved).
