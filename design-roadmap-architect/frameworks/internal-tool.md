# Internal tool / dashboard project flow
 
## Framework anchors
 
- **Utility-first design** — Function over polish. Internal tools serve power users doing repetitive work; clarity, speed, and density beat visual delight.
- **Power-user UX patterns** (UXmatters et al.) — https://www.uxmatters.com/mt/archives/2014/06/expert-users-and-power-users-special-needs-special-design.php — Patterns specific to expert users: keyboard-first interaction, dense tables, customizable views, explicit shortcuts, tolerance for complexity.
For dashboards specifically: Stephen Few's *Information Dashboard Design* and "Big Book of Dashboards" patterns.
 
## Canonical step sequence (standard build, 5 steps)
 
### Step 1: Audit the workflow
- **Goal:** Understand the current pain — what manual steps the user repeats, where they lose time, what they hate.
- **What happens:** Shadow 2-4 users doing the actual work. Time their tasks. Capture every workaround they've built (spreadsheet macros, copy-paste loops, Slack threads).
- **Default tools:** Claude (synthesis), Notion (workflow doc), screen recording.
- **Default time:** 3-5 days standard · 1-2 days quick · 5-7 days full launch.
- **Deliverable:** A workflow audit doc — who does what, how long it takes today, where the pain is.
- **Framework attribution:** Power-user UX research method (shadowing rather than survey).
- **Sub-tasks:**
  - Shadow 2-4 power users for a full task cycle
  - Time every step (find the slow ones)
  - Capture every workaround / spreadsheet hack
  - Quote the user verbatim on what they hate
  - Rank pain points by frequency × severity
### Step 2: Identify automation opportunities
- **Goal:** Decide what to remove, automate, or accelerate vs. what stays manual.
- **What happens:** For each pain point, ask: can this step be removed entirely? Automated? Just made faster? Define the new workflow.
- **Default tools:** FigJam (workflow re-mapping), Notion (decisions doc).
- **Default time:** 2-3 days standard · 1 day quick · 4-5 days full launch.
- **Deliverable:** A new workflow diagram showing what's automated, what's accelerated, what's still manual.
- **Framework attribution:** Utility-first principle — the best UI is no UI when a step can be automated.
- **Sub-tasks:**
  - Categorize each step: remove / automate / accelerate / keep
  - Sketch the new workflow
  - Validate with 1-2 power users
  - Identify required system integrations
  - Stakeholder sign-off
### Step 3: Design utility-first UI
- **Goal:** Design dense, fast, keyboard-friendly UI. No marketing polish. No empty whitespace as decoration.
- **What happens:** Design the screens — typically a dashboard, a few list views, and 1-2 detail/edit views. Tables get serious attention. Keyboard shortcuts are first-class. Loading states are designed (long queries are normal).
- **Default tools:** Figma, v0 (for table-heavy starter layouts), Claude (for SQL or filter-spec drafting).
- **Default time:** 5-8 days standard · 3-4 days quick · 8-12 days full launch.
- **Deliverable:** Designed screens with explicit keyboard shortcuts, dense tables, and all states (loading, empty, error, success).
- **Framework attribution:** Power-user UX patterns · Few's dashboard density principles.
- **Sub-tasks:**
  - Design the dashboard (overview at a glance)
  - Design list views (sortable, filterable, dense)
  - Design detail/edit views
  - Document keyboard shortcuts
  - Design every state (loading, empty, error, success, partial)
### Step 4: Build with the team
- **Goal:** Get to a working tool fast. Internal users will tolerate rough edges if it solves the problem.
- **What happens:** Pair with engineering. Use AI-paired coding heavily — internal tools are perfect Cursor/Claude territory because they don't need bespoke craft. Ship a working version in 1-2 weeks.
- **Default tools:** Cursor, Claude (paired coding), Retool / Internal.io / custom build.
- **Default time:** 1-2 weeks for first ship.
- **Deliverable:** A working tool deployed for internal users.
- **Framework attribution:** Lean shipping for internal tools (don't gold-plate).
- **Sub-tasks:**
  - Pair with engineering (or build solo with Cursor + Claude)
  - Use a low-code tool if it fits (Retool, etc.) — internal tools rarely justify custom UI
  - Ship to a small group of beta users
  - Fix the showstoppers, ignore the polish requests
  - Demo to the wider team
### Step 5: Train + document
- **Goal:** Make sure the tool actually replaces the old workflow, not just sits alongside it.
- **What happens:** Write a one-page how-to. Run a 30-minute training. Pair with each user once. Track adoption.
- **Default tools:** Notion (docs), Loom (recorded walkthroughs), Slack (support channel).
- **Default time:** 3-5 days for training rollout.
- **Deliverable:** Adoption metrics + a runbook the team can self-serve from.
- **Framework attribution:** Power-user adoption research.
- **Sub-tasks:**
  - Write a one-page how-to
  - Record a Loom walkthrough
  - Run a 30-min team training
  - Pair-shadow with each user once
  - Set up a feedback channel and review weekly
## Adjustments by project shape
 
**Quick exploration (3-4 steps):** Skip step 5 (formal training) — Slack-based support is enough. Compress step 1 to a half-day shadow + 2-3 user calls. Build with a low-code tool to get to step 4 in 3 days.
 
**Standard build (5 steps):** Use the sequence as-is.
 
**Full production launch (6-7 steps):** Insert "Permissions + access design" between 2 and 3 if the tool touches sensitive data. Add "Long-term maintenance plan" after step 5 (who owns it, who fixes bugs).
 
## Hybrid project notes
 
For an **AI-powered internal tool** (e.g., LLM that drafts replies, classifies tickets), blend with `frameworks/ai-product.md`. Internal tools tolerate AI imperfection better than external products — but power users notice errors immediately, so step 2 (uncertainty) and step 4 (feedback) of the AI framework still matter.
 
For a **customer-facing internal-style tool** (e.g., admin panel for partners), this framework still applies but bump up polish slightly. Consider `frameworks/web-saas.md` as supplemental.
 
## Reading list seeds
 
**Primary:**
- "Information Dashboard Design" (Stephen Few) — book, foundational for dashboards
- Power-Users and Expert Users (UXmatters) — https://www.uxmatters.com/mt/archives/2014/06/expert-users-and-power-users-special-needs-special-design.php
**Adjacent:**
- "The Big Book of Dashboards" (Wexler, Shaffer, Cotgreave)
- Linear's "design principles" page (canonical example of utility-first UI) — https://linear.app/method
- Retool / Internal.io as patterns to study
**Key concepts:**
- Density vs. whitespace (internal tools want density)
- Keyboard-first interaction
