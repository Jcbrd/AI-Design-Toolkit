# Marketing site project flow
 
## Framework anchors
 
- **CRO methodology** (Conversion Rate Optimization) — https://cxl.com/conversion-optimization/ — A data-driven approach to designing pages that convert: research → hypothesis → test → iterate.
- **StoryBrand BrandScript** (Donald Miller) — https://storybrand.com/ — A narrative framework that positions the customer as the hero and the brand as the guide, organizing site copy around a 7-part story structure.
## Canonical step sequence (standard build, 5 steps)
 
### Step 1: Define audience + offer
- **Goal:** Pin down exactly who the page is for and what you're asking them to do.
- **What happens:** Identify the ideal customer profile (ICP). Write the one-sentence value proposition. Build a StoryBrand BrandScript (hero, problem, guide, plan, action, success, failure).
- **Default tools:** Claude (BrandScript drafting, ICP synthesis), Notion (audience + offer doc).
- **Default time:** 2-4 days standard · 1 day quick · 4-6 days full launch.
- **Deliverable:** A one-page strategy doc with ICP, value prop, BrandScript, and the primary conversion goal.
- **Framework attribution:** StoryBrand BrandScript framework · CRO research phase.
- **Sub-tasks:**
  - Define the ICP (1-2 segments max)
  - Write the value proposition (under 12 words)
  - Complete the StoryBrand 7-part BrandScript
  - Identify the single primary conversion goal
  - Stakeholder sign-off before designing
### Step 2: Build the message hierarchy
- **Goal:** Translate the strategy into a section-by-section content outline.
- **What happens:** Outline the page sections from hero down to footer. Decide what message each section delivers and what action it asks for. Draft headlines and CTAs first.
- **Default tools:** Claude (headline drafting), FigJam (section sketching).
- **Default time:** 2-3 days standard · 1 day quick · 3-5 days full launch.
- **Deliverable:** An annotated content outline showing each section's purpose, headline, supporting copy, and CTA (if any).
- **Framework attribution:** StoryBrand narrative arc · CRO above-the-fold conversion theory.
- **Sub-tasks:**
  - Outline sections in narrative order (StoryBrand arc)
  - Write headlines for every section first (they're the spine)
  - Draft supporting copy
  - Place CTAs deliberately (every section should know whether it has one)
  - Pressure-test against "would the ICP keep scrolling?"
### Step 3: Design the visual story
- **Goal:** Visual design — layout, typography, imagery, brand voice.
- **What happens:** Design the page in Figma. Hero first, then below the fold. Source or commission imagery. Apply brand voice consistently.
- **Default tools:** Figma, Framer (if Framer is the build target), Claude (copy refinement).
- **Default time:** 5-8 days standard · 3-4 days quick · 8-12 days full launch.
- **Deliverable:** A complete designed page (desktop + mobile) ready to build.
- **Framework attribution:** CRO visual hierarchy principles · StoryBrand visual storytelling.
- **Sub-tasks:**
  - Design the hero section first (it carries the conversion)
  - Design every section below the fold
  - Source or generate imagery
  - Build mobile layouts (treat as primary, not adaptation)
  - Internal critique with focus on conversion path
### Step 4: Wire up + test conversion
- **Goal:** Build it, instrument it, run conversion experiments.
- **What happens:** Build in Framer (or hand off to engineering). Set up analytics, heatmaps, and at least one A/B test on the hero or primary CTA.
- **Default tools:** Framer (build), Cursor + Claude (custom build), Hotjar (heatmaps), Posthog (analytics).
- **Default time:** 4-7 days standard · 2-3 days quick · 7-10 days full launch.
- **Deliverable:** Live page with analytics + heatmaps + first A/B test running.
- **Framework attribution:** CRO testing methodology.
- **Sub-tasks:**
  - Build the page (Framer or hand off)
  - Set up analytics for the conversion goal
  - Add heatmaps and session recordings
  - Define and launch the first A/B test (usually on the hero)
  - Document the testing roadmap (what to test next)
### Step 5: Launch + iterate
- **Goal:** Ship it, measure, iterate weekly.
- **What happens:** Public launch. Weekly review of conversion data. Run the next A/B tests. Update content based on what's working.
- **Default tools:** Framer / CMS (updates), Claude (copy iteration), Posthog (data).
- **Default time:** Launch + 2 weeks of iteration.
- **Deliverable:** Live page with at least 2 iterations shipped based on data.
- **Framework attribution:** CRO continuous optimization.
- **Sub-tasks:**
  - Launch publicly
  - Set up a weekly conversion review
  - Run the next A/B test
  - Update copy based on what's converting
  - Plan v2 based on aggregate data
## Adjustments by project shape
 
**Quick exploration (3-4 steps):** Skip step 4 (formal A/B testing) for v0. Just ship and watch raw conversion. Compress step 1 to a couple hours of strategy work.
 
**Standard build (5 steps):** Use the sequence as-is.
 
**Full production launch (6-7 steps):** Add "SEO + technical foundations" before step 4 (page speed, schema, OG tags). Add "Paid traffic landing page variants" after step 5 if running ads.
 
## Hybrid project notes
 
For a **product launch landing page** (single high-stakes moment), compress to 3 steps: define + design + launch. Skip iteration in favor of pre-launch testing.
 
For a **content marketing site** with many pages (blog, resources), use this framework for templates and treat individual articles as production work outside this skill.
 
## Reading list seeds
 
**Primary:**
- CXL on Conversion Optimization — https://cxl.com/conversion-optimization/
- StoryBrand BrandScript — https://storybrand.com/
**Adjacent:**
- "Made to Stick" (Heath brothers) for sticky messaging
- "Don't Make Me Think" (Steve Krug) for clarity testing
- Marketing Examples newsletter — https://marketingexamples.com
**Key concepts:**
- The above-the-fold conversion test
- StoryBrand 7-part narrative arc
- Hypothesis-driven A/B testing
- The "would they keep scrolling?" question
