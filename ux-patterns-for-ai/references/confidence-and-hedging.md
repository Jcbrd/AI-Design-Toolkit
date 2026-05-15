# Confidence and hedging

A 73% confidence score sounds precise but users round it to "might be wrong." Numeric confidence works only when the user can take a different action at different thresholds — auto-approve above 95%, route to human below 60%, surface for review in between. For everything else, hedge in language: "I'm not sure, but..." or "Based on a partial match..."

**The first question to ask:** what action does the user take when confidence is low? If the answer is "nothing different," the indicator is decorative — and decorative confidence indicators erode trust because users can't act on them.

**By indicator type:**
- **Numeric score (e.g., "82%")**: Only when paired with thresholds that drive different UI or workflow. Common in moderation, fraud, document classification.
- **Badge (e.g., "high confidence")**: Useful when there are 2–3 clear bands and users learn what each means. Don't use more than 3 bands.
- **Language hedge ("I'm not sure, but...")**: The right default for chat and content generation. Doesn't require the user to learn a new vocabulary.
- **Source diversity ("Based on 12 sources" vs. "Based on 1 source")**: Honest, transparent, and actually predictive of quality.

**Anti-patterns to flag:**
- Traffic-light colors (green/yellow/red) on confidence. Green/red imports moral weight ("good answer / bad answer") that confidence doesn't carry, and color-blind users miss the cue.
- Hiding low-confidence answers from the user. Better to show with a hedge — silent suppression breaks the user's mental model of when the AI works.
- Confidence on creative outputs. "I'm 84% confident in this poem" is meaningless and faintly absurd.

**The decision the designer needs to make:** Is confidence actionable in this product, or is it just a comfort blanket?

**Revisit if:** Users ignore the indicator (it doesn't drive different behavior — drop it or make it actionable) or users over-trust answers regardless of indicator (the indicator isn't honest enough — recalibrate or replace with hedging language).
