# Mobile / native app project flow
 
## Framework anchors
 
- **Apple Human Interface Guidelines (HIG)** — https://developer.apple.com/design/human-interface-guidelines — Apple's canonical guidance on native iOS/iPadOS design, covering navigation, gestures, modality, platform conventions.
- **Double Diamond** (Design Council, UK) — https://www.designcouncil.org.uk/our-resources/the-double-diamond — A four-phase framework (Discover → Define → Develop → Deliver) widely used as the backbone of design process.
For Android-first or cross-platform projects, also reference Material Design 3 (https://m3.material.io/).
 
## Canonical step sequence (standard build, 5 steps)
 
### Step 1: Discover the user
- **Goal:** Build empathy and align on the user's actual job.
- **What happens:** Conduct user interviews, synthesize themes, write personas or JTBD statements, identify the core problem the app solves.
- **Default tools:** Claude (synthesis), Dovetail (transcripts/analysis), Notion (writeups).
- **Default time:** 3-5 days standard · 1-2 days quick · 7-10 days full launch.
- **Deliverable:** Short research synthesis with personas or JTBD statements and a one-line problem statement.
- **Framework attribution:** Discover phase of Double Diamond · HIG: "Designing a Great App" intro guidance.
- **Sub-tasks:**
  - Recruit 3-5 representative users
  - Run interviews, capture transcripts
  - Synthesize themes (Claude as sounding board)
  - Write 1-2 personas or 3-5 JTBD statements
  - Land a one-line problem statement
### Step 2: Map the flow
- **Goal:** Define information architecture, key journeys, navigation pattern.
- **What happens:** Sketch primary user journeys, decide on navigation pattern (tab bar, side menu, modal stack), map IA at screen level.
- **Default tools:** FigJam (or Miro).
- **Default time:** 2-3 days standard · 1 day quick · 4-5 days full launch.
- **Deliverable:** Flow map showing key screens, connections, navigation pattern.
- **Framework attribution:** Define phase of Double Diamond · HIG: Navigation principles.
- **Sub-tasks:**
  - Sketch 3-5 most important user journeys
  - Choose navigation pattern aligned with HIG conventions
  - Map every screen and its parent in the IA
  - Identify shared components across journeys
  - Walkthrough with team or stakeholder
### Step 3: Design the screens
- **Goal:** Visual design of all key screens with components and copy.
- **What happens:** Build UI in Figma — components, layouts, type, color, microcopy. Use v0/AI for starter layouts; refine in Figma. Use Claude for copy.
- **Default tools:** Figma, v0, Claude.
- **Default time:** 5-10 days standard · 3-4 days quick · 10-15 days full launch.
- **Deliverable:** Complete set of designed screens for core journeys, with reusable components.
- **Framework attribution:** Develop phase of Double Diamond · HIG: Layout, Color, Typography, Materials.
- **Sub-tasks:**
  - Build or adopt a component library
  - Design every screen in the core journeys
  - Write all copy (headers, body, CTAs, errors, empty states)
  - Apply HIG-conformant patterns (gestures, modals, sheets)
  - Pressure-test accessibility (contrast, touch targets, type sizes)
### Step 4: Prototype motion
- **Goal:** Bring the design to life with native-feeling interactions and transitions.
- **What happens:** Prototype most important interactions — onboarding, key gesture flows, transitions between screens.
- **Default tools:** Origami Studio (native iOS), Rive (embeddable motion).
- **Default time:** 3-7 days standard · skip in quick · 5-10 days full launch.
- **Deliverable:** Interactive prototype demonstrating 3-5 key interaction moments.
- **Framework attribution:** Develop phase of Double Diamond · HIG: Motion.
- **Sub-tasks:**
  - Identify the 3-5 motion moments that most affect feel
  - Prototype each (Origami for native, Rive for portable)
  - User-test the prototype on a real device
  - Document timing, easing, gestures for handoff
  - Refine based on feedback
### Step 5: Code-ready handoff
- **Goal:** Hand off to engineering (or build it yourself) with everything needed to ship.
- **What happens:** Use Figma Dev Mode or pair-coding (Cursor + Claude) to translate designs into shipping code. Document edge cases, generate specs.
- **Default tools:** Cursor, Claude, Expo (or Figma Dev Mode for native handoff).
- **Default time:** 2-4 days for handoff prep · 1 day quick · 4-7 days full launch.
- **Deliverable:** Spec sheet + code snippets + working stub for the most critical screen.
- **Framework attribution:** Deliver phase of Double Diamond · HIG: Accessibility, Inclusion.
- **Sub-tasks:**
  - Annotate edge cases (empty, error, loading, offline)
  - Generate component specs from Figma
  - Pair with Cursor + Claude on the trickiest screens
  - Document expected accessibility behavior
  - Ship a working stub of the highest-risk flow
## Adjustments by project shape
 
**Quick exploration (3-4 steps):** Skip step 4 (motion). Compress step 1 to a half-day of secondary research + 1-2 informal user chats. Rush 2 → 3 → 5 to get a working v0 in front of users fast.
 
**Standard build (5 steps):** Use the sequence as-is.
 
**Full production launch (6-7 steps):** Insert "Test with real users" between steps 4 and 5 (Maze, UserTesting, or in-person). After step 5, add "Ship-day prep + post-launch iteration" — analytics, crash monitoring, feedback loops.
 
## Hybrid project notes
 
For an **AI mobile app**, blend with `frameworks/ai-product.md`. Insert "Define the human-AI relationship" between steps 1 and 2, and add an explicit "Design for uncertain output" sub-step in step 3.
 
For a **mobile + web companion**, treat as two parallel project flows sharing steps 1, 2 (with platform-specific sub-flows), and 5.
 
## Reading list seeds
 
**Primary:**
- Apple Human Interface Guidelines — https://developer.apple.com/design/human-interface-guidelines
- Double Diamond (Design Council) — https://www.designcouncil.org.uk/our-resources/the-double-diamond
**Adjacent:**
- Material Design 3 (Android) — https://m3.material.io
- Mobbin (real app patterns to study) — https://mobbin.com
**Key concepts:**
- Native vs. cross-platform tradeoffs
- Touch target sizing (44pt iOS / 48dp Android)
- Modal vs. inline navigation
