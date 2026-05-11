# Service / system design project flow
 
## Framework anchors
 
- **Service blueprint** (Lynn Shostack, refined by NN/g) — https://www.nngroup.com/articles/service-blueprints-definition/ — A diagram showing the customer's actions across touchpoints alongside the frontstage, backstage, and support processes that enable them.
- **Customer journey mapping** — https://www.nngroup.com/articles/journey-mapping-101/ — A visualization of the user's end-to-end experience including actions, thoughts, emotions, and pain points.
## Canonical step sequence (standard build, 5 steps)
 
### Step 1: Map the current journey
- **Goal:** Capture how customers actually experience the service today, including emotional highs and lows.
- **What happens:** Interview customers and frontline staff. Map every touchpoint, what the customer does, thinks, feels, and where they hit friction.
- **Default tools:** Claude (interview synthesis), Dovetail (transcripts), FigJam or Miro (the journey map itself).
- **Default time:** 5-7 days standard · 2-3 days quick · 8-12 days full launch.
- **Deliverable:** A current-state journey map with touchpoints, emotions, and pain points marked.
- **Framework attribution:** Customer journey mapping methodology (NN/g).
- **Sub-tasks:**
  - Interview 5-10 customers across journey stages
  - Interview 3-5 frontline staff (they see the seams)
  - Map every touchpoint chronologically
  - Annotate emotion at each touchpoint
  - Mark friction, confusion, and abandonment points
### Step 2: Identify opportunities
- **Goal:** Pick the moments that most need (re)design and prioritize them.
- **What happens:** Identify "moments of truth" — interactions disproportionately important to the relationship. Prioritize by impact and feasibility. Decide what to redesign vs. what to leave.
- **Default tools:** FigJam, Notion (opportunities doc).
- **Default time:** 2-3 days standard · 1 day quick · 4-5 days full launch.
- **Deliverable:** A prioritized opportunity list with 3-7 moments to redesign and a rationale for each.
- **Framework attribution:** Service design "moments of truth" concept.
- **Sub-tasks:**
  - Identify candidate moments of truth from the journey map
  - Score each on impact (to satisfaction or revenue) and feasibility
  - Pick 3-7 to redesign in this project
  - Write a one-line "why" for each
  - Stakeholder review
### Step 3: Design service touchpoints
- **Goal:** Redesign the chosen interactions — digital and physical.
- **What happens:** For each opportunity, design the new interaction. Some are screens, some are scripts, some are physical artifacts (signage, packaging). Treat each consistently.
- **Default tools:** Figma (digital touchpoints), Notion (scripts/playbooks), Adobe (physical artifacts).
- **Default time:** 7-12 days standard · 3-5 days quick · 12-18 days full launch.
- **Deliverable:** Designed touchpoints for each opportunity, with consistent voice and visual identity.
- **Framework attribution:** Service design holistic touchpoint design.
- **Sub-tasks:**
  - Design each digital touchpoint
  - Write each script or conversation flow
  - Design any physical artifacts
  - Pressure-test for consistency across touchpoints
  - Internal walkthrough
### Step 4: Blueprint the backstage
- **Goal:** Document the operational reality of the redesigned service — what employees do, what systems run, what enables the new touchpoints.
- **What happens:** Build the service blueprint: customer actions, frontstage staff actions, backstage staff actions, support processes. Identify gaps where new tooling or training is needed.
- **Default tools:** FigJam (the blueprint), Notion (operational doc).
- **Default time:** 3-5 days standard · 1-2 days quick · 5-7 days full launch.
- **Deliverable:** A complete service blueprint covering every redesigned touchpoint.
- **Framework attribution:** Shostack's service blueprint methodology.
- **Sub-tasks:**
  - Map customer actions for each touchpoint
  - Map frontstage employee actions (visible to customer)
  - Map backstage actions (invisible but necessary)
  - Map support processes (systems, tools, third parties)
  - Identify gaps: what's missing to make this work?
### Step 5: Pilot + measure
- **Goal:** Roll the new service out small, measure, iterate.
- **What happens:** Pick one location, region, or customer segment. Run the new service for 2-4 weeks. Measure satisfaction, completion rates, friction. Iterate.
- **Default tools:** Maze or Lookback (qualitative testing), Notion (operational tracking), spreadsheet (KPIs).
- **Default time:** 2-4 week pilot.
- **Deliverable:** Pilot report with KPIs vs. baseline + a list of fixes for the next iteration.
- **Framework attribution:** Service design pilot-and-iterate principle.
- **Sub-tasks:**
  - Pick a pilot scope (location/segment)
  - Train the staff involved
  - Define 3-5 KPIs to measure
  - Run for 2-4 weeks
  - Synthesize, decide on full rollout vs. iterate
## Adjustments by project shape
 
**Quick exploration (3-4 steps):** Compress step 1 to desk research + 3 customer interviews. Skip step 4 (full blueprint) — replace with a single op-spec doc. Pilot in step 5 is a thought experiment.
 
**Standard build (5 steps):** Use the sequence as-is.
 
**Full production launch (6-7 steps):** Insert "Stakeholder + leadership alignment" between 2 and 3 (services touch many teams). After step 5, add "Full rollout + change management."
 
## Hybrid project notes
 
For a **digital service** (no physical touchpoints), this is essentially a SaaS UI project — consider also `frameworks/web-saas.md`. Step 4 (blueprint) becomes lighter; the systems are mostly digital.
 
For a **healthcare or government service**, add a "compliance + regulatory review" step between 3 and 4.
 
## Reading list seeds
 
**Primary:**
- NN/g Service Blueprints — https://www.nngroup.com/articles/service-blueprints-definition/
- NN/g Journey Mapping 101 — https://www.nngroup.com/articles/journey-mapping-101/
**Adjacent:**
- "This is Service Design Doing" (Stickdorn et al.) — https://www.thisisservicedesigndoing.com/
- IDEO Field Guide to Human-Centered Design — https://www.designkit.org/
**Key concepts:**
- Frontstage vs. backstage
- Moments of truth
- Customer journey emotion curves
- Pain points and gain points
- Service prototyping (role-play, walkthrough, paper)
