# Feedback and correction

Thumbs up / thumbs down are everywhere in AI products and almost universally under-designed. The pattern is meaningful only if (a) the user knows what their click does, (b) the system actually uses the feedback, and (c) the user can see that something happened. Most products skip all three. Operationalizes HAX G15 (Encourage granular feedback) and supports HAX G9 (Support efficient correction).

The honest question: what's this feedback affordance actually for — improving the model, improving the user's session, or signaling acknowledgment? Different goals need different surfaces.

**Three feedback modes worth designing distinctly:**

1. **Quality feedback** (thumbs up / down, star rating). Tells the system whether this answer was good in aggregate. Useful for product analytics and training signal. Low-stakes for the user, so participation is high but signal is weak — a downvote can mean ten different things, and the system can't tell which.

2. **Granular correction** (edit the answer, mark the wrong sentence, "this part was wrong, try again"). Tells the system *what specifically* to fix. Higher friction, much higher signal. The right pattern when the user is invested in the answer's accuracy — drafting tools, code suggestions, anything where the user is the author and the AI is the assistant.

3. **Behavioral feedback** (the user regenerates, abandons, copies-and-edits, never returns). Implicit feedback the system can read without asking. Often more honest than explicit feedback because the user isn't performing for the rating. Design analytics around this; don't try to collect it as explicit signal.

**Anti-patterns to flag:**

- Thumbs up / down with no follow-up surface ("thanks for your feedback!" and nothing happens). Trains users to stop bothering. Worse, it telegraphs that the team isn't actually using the data.
- Asking for feedback after every interaction. Feedback fatigue means quality drops and people start clicking randomly to dismiss the prompt.
- No way for the user to *see* that their feedback affected something. Even "we use this to train future versions" beats silence; a more honest version is "this turned off this kind of suggestion for you" when applicable.
- Treating quality feedback as if it were granular. Assuming a downvote tells you what to fix, when it just tells you something was off.

**The decision the designer needs to make:** What kind of signal does this feature actually need from users, and what's the lowest-friction way to collect an honest version of it?

**Revisit if:** Feedback rates are low (the affordance feels pointless) or feedback rates are high but unactionable (you're collecting noise — switch to granular correction or behavioral signals).
