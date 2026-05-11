# AI product project flow
 
## Framework anchors
 
- **Google PAIR Guidebook** (People + AI Research) — https://pair.withgoogle.com/guidebook/ — Six chapters covering user needs, mental models, explainability, feedback, errors, and trust calibration for AI products.
- **Microsoft HAX Toolkit** (Human-AI eXperience) — https://www.microsoft.com/en-us/haxtoolkit/ — 18 guidelines organized in four phases (initially, during interaction, when wrong, over time) plus a workbook and pattern library.
## Canonical step sequence (standard build, 5 steps)
 
### Step 1: Define the human-AI relationship
- **Goal:** Make explicit who has authority, where AI is allowed to act, and how oversight works.
- **What happens:** Decide on the autonomy level (assistant, copilot, automation, generator). Map override paths. Define what the AI can and can't do, and how confident it should be before acting.
- **Default tools:** FigJam (autonomy gradient mapping), Claude (sounding board for autonomy decisions), Notion (relationship spec doc).
- **Default time:** 3-5 days standard · 1-2 days quick · 5-8 days full launch.
- **Deliverable:** A one-page "AI relationship spec" covering capabilities, autonomy level, override paths, oversight model, and the explicit list of what the AI is not allowed to do.
- **Framework attribution:** PAIR ch.1 (User Needs + Defining Success) · HAX guidelines 1-2 (clarity about capabilities and confidence).
- **Sub-tasks:**
  - Decide the autonomy level (assistant / copilot / automation / generator)
  - Write what the AI can do (HAX 1)
  - Write how confident it should be before acting (HAX 2)
  - Map override paths and human-in-the-loop checkpoints
  - List explicit boundaries (what it must never do)
### Step 2: Design for uncertainty
- **Goal:** Design the UX of being wrong — confidence states, error messaging, trust calibration.
- **What happens:** Design how the AI surfaces confidence (or lack of it). Design "I don't know" states. Design error UX that calibrates trust without destroying it.
- **Default tools:** Figma (confidence/error state designs), Maze (testing trust calibration).
- **Default time:** 4-6 days standard · 2-3 days quick · 6-9 days full launch.
- **Deliverable:** A complete set of confidence-state and error-state designs, plus a written rationale for why each one builds (or protects) trust.
- **Framework attribution:** PAIR ch.3 (Mental Models) and ch.4 (Explainability + Trust) · HAX guidelines 3-6 (during interaction).
- **Sub-tasks:**
  - Design the "high confidence" UI state
  - Design the "uncertain" UI state (with appropriate hedging)
  - Design the "I don't know" state
  - Design error / wrong-answer states
  - Test trust calibration with 5+ users
### Step 3: Prototype with real AI behavior
- **Goal:** Don't prototype with cherry-picked outputs. Wire up real model output, including its messy edges.
- **What happens:** Stand up a working prototype that uses real model calls. Capture and design for refusals, hallucinations, edge cases, latency. Measure how often each happens.
- **Default tools:** v0 (AI-paired UI generation), Claude (model behavior testing), Cursor (paired implementation).
- **Default time:** 5-8 days standard · 3-4 days quick · 8-12 days full launch.
- **Deliverable:** Working prototype connected to a real model + a "behavior map" cataloging the failure modes you saw and how you handled each.
- **Framework attribution:** PAIR ch.2 (Data Collection + Evaluation) · HAX guidelines 7-10 (when wrong).
- **Sub-tasks:**
  - Stand up the prototype with live model calls
  - Capture 50+ representative model outputs (good and bad)
  - Categorize failure modes (refusal, hallucination, off-topic, slow)
  - Design UX response for each failure mode
  - Measure latency and design for it (skeleton, streaming, partial)
### Step 4: Build feedback + correction loops
- **Goal:** Let the user steer, correct, and teach the AI in-product.
- **What happens:** Design how a user signals "this is wrong" or "I want it different." Design how the system uses that signal — for the user's own session, and for system-level learning.
- **Default tools:** Figma (correction UX patterns), Cursor (implement), Claude (drafting system prompts and feedback flows).
- **Default time:** 4-6 days standard · 2-3 days quick · 6-9 days full launch.
- **Deliverable:** Feedback UX patterns implemented for the top 3 interactions, plus a doc explaining how each feedback signal feeds back into model behavior.
- **Framework attribution:** PAIR ch.5 (Feedback + Control) · HAX guidelines 13-15 (over time).
- **Sub-tasks:**
  - Design the "correct this" / "regenerate" affordance
  - Design implicit feedback capture (dwell, retry, abandonment)
  - Design explicit feedback (thumbs up/down, free-form)
  - Write the system prompt or fine-tuning approach that uses feedback
  - Test the feedback loops with real users
### Step 5: Plan graceful degradation
- **Goal:** Design what happens when the AI is unavailable, slow, wrong, or has changed.
- **What happens:** Document fallbacks for every AI-driven feature. Plan how you communicate model changes to users. Plan failure modes the user can recover from on their own.
- **Default tools:** Notion (write the fallback playbook), Cursor (implement fallbacks), Maze (test failure paths).
- **Default time:** 3-5 days standard · 1-2 days quick · 5-7 days full launch.
- **Deliverable:** A "graceful degradation playbook" — for each AI feature, the fallback when the model is down, slow, wrong, or has changed.
- **Framework attribution:** PAIR ch.6 (Errors + Graceful Failure) · HAX guidelines 16-18 (changes over time).
- **Sub-tasks:**
  - For each AI feature, define the "model unavailable" fallback
  - Design the "this answer changed" transparency UI (HAX 18)
  - Plan model version notifications (when behavior shifts)
  - Document recovery paths the user can self-serve
  - Test failure modes end-to-end
## Adjustments by project shape
 
**Quick exploration (3-4 steps):** Skip step 4 (feedback loops) — capture as a v2 backlog. Compress step 1 to a half-day decision on autonomy level + override paths. Get to step 3 (real prototype) fast — that's where the truth is.
 
**Standard build (5 steps):** Use the sequence as-is.
 
**Full production launch (6-7 steps):** Add "Bias + safety review" between steps 3 and 4. After step 5, add "Monitoring + model versioning" — instrument production for drift, add a kill switch.
 
## Hybrid project notes
 
For an **AI mobile app**, blend with `frameworks/mobile-app.md`. Add HIG-conformant patterns to step 2 (mobile-specific confidence indicators) and step 4 (mobile-friendly feedback gestures).
 
For an **AI feature inside a SaaS product**, blend with `frameworks/web-saas.md`. Step 1 (jobs) feeds the autonomy decisions in this framework's step 1.
 
## Reading list seeds
 
**Primary:**
- Google PAIR Guidebook — https://pair.withgoogle.com/guidebook/
- Microsoft HAX Toolkit — https://www.microsoft.com/en-us/haxtoolkit/
**Adjacent:**
- Apple Machine Learning HIG — https://developer.apple.com/design/human-interface-guidelines/machine-learning
- Anthropic's product principles — https://www.anthropic.com
- "Designing AI Products that People Trust" (NN/g) — https://www.nngroup.com/articles/ai-product-trust/
**Key concepts:**
- Autonomy gradient (assistant → copilot → automation → generator)
- Confidence calibration
- Hallucination as a UX problem
- Feedback as system input
- Graceful degradation and model versioning
