# Web SaaS UI project flow
 
## Framework anchors
 
- **Jobs-to-be-Done (JTBD)** — https://strategyn.com/jobs-to-be-done-theory/ — Tony Ulwick's framework for understanding what customers are "hiring" your product to do, expressed as outcome statements rather than features.
- **Lean UX** — https://www.oreilly.com/library/view/lean-ux-3rd/9781098116293/ — Jeff Gothelf and Josh Seiden's iterative, hypothesis-driven approach: build the smallest thing that tests an assumption, measure, learn, repeat.
## Canonical step sequence (standard build, 5 steps)
 
### Step 1: Define the jobs
- **Goal:** Articulate what users are hiring the product to do, in their words.
- **What happens:** JTBD interviews with current or target users; convert insights into outcome statements; identify the dominant job and 2-3 supporting jobs.
- **Default tools:** Claude (interview synthesis), Dovetail (transcripts), Notion (job statements doc).
- **Default time:** 4-7 days standard · 1-2 days quick · 7-10 days full launch.
- **Deliverable:** A "jobs map" — a one-pager with the dominant job, supporting jobs, and 5-7 outcome statements ranked by importance and current satisfaction.
- **Framework attribution:** JTBD outcome-driven innovation methodology.
- **Sub-tasks:**
  - Recruit 5-8 users (mix of current customers and prospects)
  - Run JTBD-style interviews focused on context, struggle, hire/fire moments
  - Synthesize into outcome statements (verb + measure + object + clarifier)
  - Rank outcomes by importance × current satisfaction
  - Identify the dominant job — the one that pays the bills
### Step 2: Map the workflows
- **Goal:** Translate jobs into concrete task flows and the screens needed to support them.
- **What happens:** For each top outcome, sketch the task flow (current state and ideal state). Map empty/error/edge states. Identify must-have vs. nice-to-have screens.
- **Default tools:** FigJam, Miro.
- **Default time:** 2-4 days standard · 1 day quick · 5-6 days full launch.
- **Deliverable:** A workflow map for the top 3 jobs, each showing the steps, screens, and key states (loading, error, empty, success).
- **Framework attribution:** Lean UX hypothesis mapping · JTBD context circumstances.
- **Sub-tasks:**
  - Pick the top 3 outcomes from step 1
  - Sketch the current state workflow (with friction points marked)
  - Sketch the ideal state workflow
  - Enumerate all states for each screen (the dreaded "five states")
  - Stakeholder walkthrough
### Step 3: Design the screens
- **Goal:** Visual design of the must-have screens with a coherent system.
- **What happens:** Build or extend a design system, design the must-have screens, write all UI copy, design empty/error states explicitly.
- **Default tools:** Figma, v0 (AI starter layouts), Claude (copy and microcopy).
- **Default time:** 7-12 days standard · 3-5 days quick · 12-18 days full launch.
- **Deliverable:** Designed screens for the 3 dominant workflows, plus a documented component library.
- **Framework attribution:** Lean UX collaborative design.
- **Sub-tasks:**
  - Adopt or extend a design system / component library
  - Design every must-have screen for the 3 workflows
  - Design every state (loading, empty, error, success) — don't just design happy paths
  - Write all UI copy
  - Run an internal design critique
### Step 4: Prototype + test
- **Goal:** Validate the design with real users before development.
- **What happens:** Stitch screens into an interactive prototype. Run usability tests with 5-8 users. Identify and fix blockers before handing to engineering.
- **Default tools:** Figma (prototyping), Maze (unmoderated testing), Lookback (moderated).
- **Default time:** 3-5 days standard · 2 days quick · 5-7 days full launch.
- **Deliverable:** Tested prototype + usability findings doc with prioritized fixes.
- **Framework attribution:** Lean UX build-measure-learn cycle.
- **Sub-tasks:**
  - Build interactive prototype in Figma
  - Write task scenarios for testing
  - Run 5-8 sessions (moderated or unmoderated)
  - Synthesize findings (severity-ranked)
  - Fix the blockers; defer the rest to v2
### Step 5: Build + iterate
- **Goal:** Ship the smallest valuable version, then learn and iterate.
- **What happens:** Hand off to engineering (or build alongside). Define success metrics. Ship behind a feature flag, gather data, iterate.
- **Default tools:** Cursor, Claude (paired with engineering), Figma Dev Mode.
- **Default time:** 1-2 weeks for first ship, ongoing.
- **Deliverable:** Shipped feature behind a flag + metrics dashboard + plan for the first iteration.
- **Framework attribution:** Lean UX measure-learn loop · JTBD outcome tracking.
- **Sub-tasks:**
  - Define 2-3 success metrics tied to JTBD outcomes
  - Pair with engineering (Cursor + Claude where helpful)
  - Ship behind feature flag to a small audience
  - Instrument analytics for the success metrics
  - Plan the next iteration based on data, not opinions
## Adjustments by project shape
 
**Quick exploration (3-4 steps):** Skip step 4 (formal usability testing) — replace with 2-3 informal demos. Compress step 1 to "5 customer calls in a week."
 
**Standard build (5 steps):** Use the sequence as-is.
 
**Full production launch (6-7 steps):** Insert "Beta with real customers" between 4 and 5. After 5, add "Track outcomes + decide next bet" — formalize the measure-learn-decide loop.
 
## Hybrid project notes
 
For an **AI feature inside a SaaS product**, blend with `frameworks/ai-product.md`. Insert "Define the human-AI relationship" between steps 2 and 3, and add "Design for uncertain output" as a sub-step of step 3.
 
For an **enterprise SaaS** (long sales cycle, complex IT landscape), add a "Compliance + integrations review" step before step 5.
 
## Reading list seeds
 
**Primary:**
- Strategyn JTBD — https://strategyn.com/jobs-to-be-done-theory/
- Lean UX, 3rd edition (Gothelf & Seiden) — https://www.oreilly.com/library/view/lean-ux-3rd/9781098116293/
**Adjacent:**
- The Five States of Every Page (Scott Hurff) — https://scotthurff.com/posts/why-your-user-interface-is-awkward-youre-ignoring-the-ui-stack
- Refactoring UI (Wathan & Schoger) — https://www.refactoringui.com
**Key concepts:**
- Outcome statements (vs. feature requests)
- Hire/fire moments
- The five UI states (blank, loading, partial, error, ideal)
- Hypothesis-driven design
- Build-measure-learn cycles
