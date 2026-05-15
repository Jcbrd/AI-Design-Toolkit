# Frameworks reference

This skill is tactical: each pattern operationalizes one or more strategic guidelines from established research. The primary anchor is Microsoft's HAX (Human-AI Interaction) guidelines.

## Microsoft HAX Guidelines

The 18 HAX guidelines were published by Amershi et al. at CHI 2019 ("Guidelines for Human-AI Interaction"). They define design principles for AI systems at a strategic level and are organized into four phases of interaction.

This skill operationalizes them: each pattern below names *what specifically* to ship to satisfy one or more HAX guidelines.

### Initially

- **G1 — Make clear what the system can do**
  Operationalized by: `input-scaffolding`, `empty-and-first-run`, `agent-roles-and-boundaries`, `refusal-and-fallback`

- **G2 — Make clear how well the system can do what it can do**
  Operationalized by: `confidence-and-hedging`, `designing-for-uncertainty`, `citations-and-sources`, `empty-and-first-run`

### During interaction

- **G3 — Time services based on context**
  Operationalized by: `latency-and-loading`, `streaming-vs-batch`

- **G4 — Show contextually relevant information**
  Operationalized by: `rag-and-retrieval-ux` (partial)

- **G5 — Match relevant social norms**
  *Not currently operationalized.* Likely outside the scope of this skill — closer to content design and brand voice.

- **G6 — Mitigate social biases**
  *Not currently operationalized.* Likely outside the scope of this skill — closer to responsible AI / ethics design.

### When wrong

- **G7 — Support efficient invocation**
  Operationalized by: `input-scaffolding`, `streaming-vs-batch`

- **G8 — Support efficient dismissal**
  Operationalized by: `streaming-vs-batch` (stop affordance)

- **G9 — Support efficient correction**
  Operationalized by: `regenerate-and-undo`, `editable-output`, `feedback-and-correction`

- **G10 — Scope services when in doubt**
  Operationalized by: `refusal-and-fallback`, `permissions-and-safety-friction`, `agent-roles-and-boundaries`

- **G11 — Make clear why the system did what it did**
  Operationalized by: `citations-and-sources`, `rag-and-retrieval-ux`, `designing-for-uncertainty`

### Over time

- **G12 — Remember recent interactions**
  Operationalized by: `memory-and-context`

- **G13 — Learn from user behavior**
  *Not currently operationalized.* Candidate for a future "adaptive-behavior" pattern.

- **G14 — Update and adapt cautiously**
  *Not currently operationalized.* Candidate for a future "model-versioning-ux" pattern.

- **G15 — Encourage granular feedback**
  Operationalized by: `feedback-and-correction`

- **G16 — Convey the consequences of user actions**
  Operationalized by: `permissions-and-safety-friction`, `agent-roles-and-boundaries`, `regenerate-and-undo`

- **G17 — Provide global controls**
  Operationalized by: `agent-roles-and-boundaries` (partial)

- **G18 — Notify users about changes**
  *Not currently operationalized.* Candidate for a future "change-disclosure" pattern.

## Coverage summary

| Status | Count | Guidelines |
|---|---|---|
| Operationalized | 13 | G1, G2, G3, G4, G7, G8, G9, G10, G11, G12, G15, G16, G17 |
| Out of scope (intentional) | 2 | G5, G6 |
| Candidates for future patterns | 3 | G13, G14, G18 |

**Coverage rate:** 13 of 18 guidelines (72%) operationalized; 15 of 18 (83%) when including the two intentionally-out-of-scope ones.

## Other influences

- **Google PAIR Guidebook** — informs the philosophy of `designing-for-uncertainty` and the framing of human-AI collaboration in `agent-roles-and-boundaries`.
- **NN/g AI usability heuristics** — informs `input-scaffolding`, `latency-and-loading`, and the designer-readable voice of the patterns overall.
- **Anthropic's Building with Claude documentation** — informs technical defaults around streaming, context windows, and tool use.

## Citing this skill

If you use this skill in a project or writing, you can reference it as:

> *UX Patterns for AI* — operationalizing HAX guidelines for product designers shipping AI features. Built on Microsoft HAX (Amershi et al., 2019).

## References

- Amershi, S., Weld, D., Vorvoreanu, M., Fourney, A., Nushi, B., Collisson, P., Suh, J., Iqbal, S., Bennett, P. N., Inkpen, K., Teevan, J., Kikin-Gil, R., & Horvitz, E. (2019). *Guidelines for Human-AI Interaction*. CHI 2019. https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/
- Microsoft HAX Toolkit. https://www.microsoft.com/en-us/haxtoolkit/
- Google PAIR Guidebook. https://pair.withgoogle.com/guidebook/
- Nielsen Norman Group, AI usability articles. https://www.nngroup.com/topic/ai/
