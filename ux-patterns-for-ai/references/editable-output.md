# Editable output

When AI output is the artifact (a draft email, a doc, a code change, a design brief), make it directly editable in place. Read-only output that the user has to copy elsewhere telegraphs that the AI's work is performative, not real, and trains users to treat it as throwaway.

**Two design questions to answer:**

1. **Do edits persist when the user regenerates?** If the user edited paragraph 2 and clicks regenerate, does paragraph 2 stay edited (with regeneration of 1, 3, 4) or get blown away? "Persist" is the right default for most products but requires a non-trivial diffing flow.

2. **Does the model see the user's edits in subsequent turns?** If the user edits the draft and asks "make it more casual," does the AI work from the edited version or the original? "Yes, see them" is almost always right — but it requires you to send the edited content as part of the next prompt.

**By feature type:**
- **Email/document drafters**: full inline edit, edits persist, model sees edits on next turn. The user is the author; the AI is a collaborator.
- **Code suggestions**: inline edit with diff view. Changes commit only when the user accepts. Edits during review become part of the commit.
- **Generated images / structured outputs**: edits usually live in a separate step (regenerate with adjusted parameters) rather than direct manipulation. Direct manipulation works only when you can re-run the model from the edited state.

**Anti-patterns to flag:**
- Read-only AI output with a "Copy" button as the primary action. Users will paste into another app and ignore your AI from then on.
- Edits that vanish on regenerate with no warning. The user assumes the system saved their work; the system threw it away.
- Edits the AI never sees in subsequent turns. The user says "make it shorter" after editing; the AI shortens the original, undoing the edit. Frustrating and breaks trust.

**The decision the designer needs to make:** Is the AI's output a draft the user finishes, or a proposal the user accepts/rejects? The former needs editable output; the latter needs accept/reject affordances.

**Revisit if:** Users copy output to other apps to edit (your edit experience isn't good enough — make it the default), or users complain that the AI "doesn't remember my edits" (you're not feeding edits back into context).
