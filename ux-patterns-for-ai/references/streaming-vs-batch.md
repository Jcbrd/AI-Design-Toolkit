# Streaming vs. batch

Streaming makes the wait feel productive but introduces a class of bugs: users click action buttons (copy, regenerate, send) while the answer is mid-stream and get something incomplete or stale. Stream when answers take longer than ~2 seconds and the content is sequential — text, code, lists. Don't stream JSON, tool outputs, or anything the user is meant to act on as a unit; partial JSON is worse than a one-second wait.

**Default:** Stream for chat-style answers and long-form generation. Batch for structured outputs and anything under 2 seconds.

**Anti-patterns to flag:**
- Action buttons (copy, send, regenerate) live and clickable during a stream. Disable them — gray them out so the affordance is still discoverable, don't hide them.
- Fake streaming animation over a batched response. Users will notice the moment the cadence is too smooth, and trust drops permanently.
- Streaming into a non-resizing container that jumps the page as content arrives. Reserve vertical space or stream into a scroll-locked region.

**What good looks like:** Stream begins within ~500ms of submit. Content appears at human-readable cadence (not character-by-character — chunks of a few tokens). Copy/regenerate disabled until completion. Stream is interruptible with a visible "Stop" affordance for long generations.

**The decision the designer needs to make:** Is the wait long enough that streaming earns its complexity, and is the content shape compatible with partial display?

**Revisit if:** Users report seeing incomplete copy/sent content (controls were live too early), or analytics show high abandonment during streams (stream isn't fast enough to be worth it — try smaller batched responses).
