
# Frameworks Reference

This skill is tactical. Each pattern operationalizes one or more strategic guidelines from established research. The primary anchor is Microsoft's HAX guidelines.

---

## Microsoft HAX Guidelines

Published by Amershi et al. at CHI 2019. Eighteen design principles for AI systems organized into four interaction phases. This skill operationalizes them — each pattern names what specifically to ship to satisfy one or more guidelines.

### Initially

| Guideline | Operationalized by |
|---|---|
| G1 — Make clear what the system can do | `input-scaffolding`, `empty-and-first-run`, `agent-roles-and-boundaries`, `refusal-and-fallback` |
| G2 — Make clear how well the system can do what it can do | `confidence-and-hedging`, `designing-for-uncertainty`, `citations-and-sources`, `empty-and-first-run` |

### During interaction

| Guideline | Operationalized by |
|---|---|
| G3 — Time services based on context | `latency-and-loading`, `streaming-vs-batch` |
| G4 — Show contextually relevant information | `rag-and-retrieval-ux` (partial) |
| G5 — Match relevant social norms | Not operationalized — out of scope (content design / brand voice) |
| G6 — Mitigate social biases | Not operationalized — out of scope (responsible AI / ethics design) |

### When wrong

| Guideline | Operationalized by |
|---|---|
| G7 — Support efficient invocation | `input-scaffolding`, `streaming-vs-batch` |
| G8 — Support efficient dismissal | `streaming-vs-batch` (stop affordance) |
| G9 — Support efficient correction | `regenerate-and-undo`, `editable-output`, `feedback-and-correction` |
| G10 — Scope services when in doubt | `refusal-and-fallback`, `permissions-and-safety-friction`, `agent-roles-and-boundaries` |
| G11 — Make clear why the system did what it did | `citations-and-sources`, `rag-and-retrieval-ux`, `designing-for-uncertainty` |

### Over time

| Guideline | Operationalized by |
|---|---|
| G12 — Remember recent interactions | `memory-and-context` |
| G13 — Learn from user behavior | Not yet operationalized — candidate for future pattern |
| G14 — Update and adapt cautiously | Not yet operationalized — candidate for future pattern |
| G15 — Encourage granular feedback | `feedback-and-correction` |
| G16 — Convey the consequences of user actions | `permissions-and-safety-friction`, `agent-roles-and-boundaries`, `regenerate-and-undo` |
| G17 — Provide global controls | `agent-roles-and-boundaries` (partial) |
| G18 — Notify users about changes | Not yet operationalized — candidate for future pattern |

### Coverage

| Status | Count | Guidelines |
|---|---|---|
| Operationalized | 13 | G1, G2, G3, G4, G7, G8, G9, G10, G11, G12, G15, G16, G17 |
| Out of scope (intentional) | 2 | G5, G6 |
| Candidates for future patterns | 3 | G13, G14, G18 |

Coverage rate: 13 of 18 guidelines operationalized (72%); 83% when including intentionally out-of-scope guidelines.

---

## Other influences

**Google PAIR Guidebook** — informs the philosophy of `designing-for-uncertainty` and the framing of human-AI collaboration in `agent-roles-and-boundaries`.

**NN/g AI usability heuristics** — informs `input-scaffolding`, `latency-and-loading`, and the designer-readable voice of the patterns overall.

**Anthropic's Building with Claude documentation** — informs technical defaults around streaming, context windows, and tool use.

---

## References

- Amershi, S., et al. (2019). Guidelines for Human-AI Interaction. CHI 2019. [Link](https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/)
- Microsoft HAX Toolkit. [Link](https://www.microsoft.com/en-us/haxtoolkit/)
- Google PAIR Guidebook. [Link](https://pair.withgoogle.com/guidebook/)
- Nielsen Norman Group, AI usability articles. [Link](https://www.nngroup.com/topic/ai/)

---

## Citation

If you use this skill in a project or writing:

> AI UX Patterns — operationalizing HAX guidelines for product designers shipping AI features. Built on Microsoft HAX (Amershi et al., 2019).
