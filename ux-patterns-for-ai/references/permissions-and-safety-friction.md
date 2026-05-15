# Permissions and safety friction

For features that take action — send an email, modify a file, make a purchase, post a message, run a database query — the central tension is friction vs. agency. Too much confirmation makes the AI useless ("why am I doing all the work?"). Too little risks irreversible mistakes that users blame on the product.

**Defaults that work for most agentic features:**

1. **Always confirm before any external send.** Email, payment, posted message, customer-facing action. The cost of a wrong send is high; one click of confirmation is fine.

2. **Dry-run preview for batch operations.** Before "update 47 contacts," show "Will update these 47 contacts: [preview]." Concrete previews catch errors abstract previews don't ("Will send to your selected list" is uselessly vague).

3. **Undo window of 5–30 seconds for reversible actions.** Better UX than confirmation dialog for things like "archive this thread" — the user gets speed and a safety net.

4. **No undo for irreversible actions** — design the confirmation dialog to make the consequence concrete. "Will permanently delete 3 files" beats "Are you sure?"

**By risk level:**
- **High-risk, irreversible** (delete, send, pay): full confirmation dialog naming the consequence. No defaults — the user has to choose.
- **Medium-risk, reversible** (archive, label, move): no dialog, undo toast. Speed matters more than confirmation.
- **Low-risk** (highlight, draft, suggest): no friction. The AI can act freely; the user reviews the result.

**Anti-patterns to flag:**
- Single "Run" button that executes an agent's full multi-step plan with no preview. Users discover what happened only after it's done.
- Generic confirmation dialogs ("Are you sure?") with no preview of consequences. Users click through reflexively; the dialog provides false safety.
- Undo links that don't actually undo (e.g., undo for an email that was already sent). Either make undo real or remove the affordance.
- Asking the user to confirm every step of a 12-step plan. Confirmation fatigue means the user clicks through everything; you've added friction without safety.

**What good looks like:** The user sees what the agent will do before it does it. They can edit the plan if it's wrong. Reversible actions complete fast with undo. Irreversible actions get one good confirmation that names the consequence concretely.

**The decision the designer needs to make:** For each action this feature can take, is it reversible, and how concrete is the user's preview of what will happen?

**Revisit if:** Users routinely undo or reverse the AI's actions (the previews aren't doing their job; the AI is doing the wrong thing) or users disable confirmation prompts (you've over-confirmed; trim to high-risk only).
