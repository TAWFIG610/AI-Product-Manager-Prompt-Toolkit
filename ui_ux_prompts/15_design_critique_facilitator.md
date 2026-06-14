# 15. Design Critique Facilitator
**Category:** Team Collaboration · 🔀 Mix (Web + Phone)
**Phase:** Mid-design — during weekly design reviews or sprint reviews
**Where:** Async in Figma comments / Synchronous in a 60-minute structured critique session

---

## Strategic Context

Design critique is one of the highest-leverage activities in a design team's week — and one of the most commonly conducted poorly. When done poorly, critique sessions become either a validation exercise ("Everyone agrees this looks great") or a chaotic opinion dump ("I don't like that shade of blue"). Neither produces better design.

The foundational discipline of effective critique was codified by Tom Greever in *Articulating Design Decisions* and by Adam Connor and Aaron Irizarry in *Discussing Design*. Their shared insight: **critique is not about judgment — it is about learning.** The goal is not to decide whether the design is "good." The goal is to identify where the design fails to achieve its stated objectives and generate specific, actionable improvements.

The three structures that make critique productive:
1. **Objective-first framing**: the designer states the objective before showing the design. The critique evaluates whether the design achieves that objective — not whether it matches personal taste.
2. **Heuristic-based evaluation**: critique structured around a shared framework (Nielsen's 10 Heuristics, Gestalt principles, WCAG) produces specific, replicable observations rather than subjective opinions.
3. **I like / I wish / What if**: Adam Connor's critique framework forces observers to offer improvements alongside observations.

The most dangerous critique pattern: **HiPPO feedback** (Highest Paid Person's Opinion). When seniority determines the weight of feedback rather than argument quality, the design process stops learning and starts performing for hierarchy.

---

## Relevant Dimensions

**Critique session logistics:**
- Duration: **30–60 minutes** per design (never critique more than 2 designs in one session — attention degrades)
- Participants: **4–7 people maximum** (beyond 7, individual voices are crowded out)
- Format: Designer presents → Structured observation round → Prioritization → Action list

**Async critique (Figma comments):**
- Comments must follow the **I notice / I wonder / I suggest** format
- Every comment must reference a specific element (not a general impression)
- Designer responds to every comment within **24 hours** of session

**Displaying critique materials:**
- Web presentation: **1280 × 800 px** viewport
- Mobile designs: present at **390 pt** canvas, use Figma Mirror on physical device
- Show the design at **100% scale** for mobile — never zoomed out when evaluating touch targets or readability

**Heuristic framework reference (Nielsen's 10):**
1. Visibility of system status
2. Match between system and real world
3. User control and freedom
4. Consistency and standards
5. Error prevention
6. Recognition over recall
7. Flexibility and efficiency of use
8. Aesthetic and minimalist design
9. Help users recognize, diagnose, and recover from errors
10. Help and documentation

---

## The Master Prompt

```markdown
You are a Senior Design Critique Facilitator with 15+ years of experience running structured design reviews at top-tier product organizations. You combine deep UX knowledge with strong facilitation skills to make critique sessions productive, psychologically safe, and improvement-focused.

Design context:
  Designer: [DESIGNER NAME]
  Design description: [DESCRIBE THE DESIGN — what screen(s), what the feature does, what user problem it solves]
  Stated objective: [WHAT WAS THE DESIGNER TRYING TO ACHIEVE? — 1–2 sentences]
  Current stage: [Wireframe / Mid-fi / High-fi / Pre-handoff]
  Review type: [Moderated live session / Async Figma comments / Stakeholder presentation review]

Generate the following:

SECTION 1 — PRE-CRITIQUE BRIEF (for the designer):
Write the brief the designer presents at the start of the session (2 minutes max, verbatim):
  - Context: "Here's the user problem we're solving..."
  - Objective: "Here's what success looks like for this design..."
  - Scope: "Here are the specific questions I want critique on..."
  - Out of scope: "Please don't critique [specific aspects] today — those are decided constraints."

SECTION 2 — STRUCTURED OBSERVATION ROUND (15 minutes):
Write the facilitation script for a round of structured observations.
For each of the following 6 critique lenses, write:
  (a) The lens name and definition
  (b) 2 starter questions to get specific observations (not opinions)
  (c) A redirect prompt for when feedback becomes vague ("Can you be more specific about...")

  Lens 1: Goal alignment — does the design achieve the stated objective?
  Lens 2: Visual hierarchy — does the user's eye land in the right order?
  Lens 3: Navigation & flow — can the user get to where they need to go?
  Lens 4: Accessibility — does the design meet WCAG AA? Are there non-color signals for all states?
  Lens 5: Platform conventions — does it follow iOS/Android HIG / web standards?
  Lens 6: Microcopy & labels — are all labels clear, specific, and action-oriented?

SECTION 3 — HEURISTIC EVALUATION PROMPT:
Using Nielsen's 10 Usability Heuristics, identify:
  For each heuristic: rate the design as ✅ passes / ⚠️ review needed / ❌ violates
  For every ⚠️ or ❌: write one specific observation and one suggested improvement

SECTION 4 — PRIORITIZED ACTION LIST:
At the end of the critique, facilitate a dot-voting exercise:
  (1) List all observations raised during the session (facilitator transcribes during the session)
  (2) Each participant allocates 3 votes to the observations they consider highest priority
  (3) Rank the observations by votes
  (4) Assign each top-3 item: Owner / Due date / Definition of done

SECTION 5 — CLOSING REFRAME:
Write the facilitator's closing statement (verbatim) that:
  - Summarizes the 3 most important agreed-upon changes
  - Separates "must change" from "consider changing" from "out of scope"
  - Sets a clear follow-up expectation (next review date and what it will cover)

Output: complete facilitator script with timing markers.
```

---

## Follow-Up Prompts

### Follow-Up 1: Async Figma Comment Templates
```markdown
Generate 15 reusable comment templates for async design critique in Figma.
Each template must follow the I notice / I wonder / I suggest format.
Cover these 5 critique categories (3 templates each):
  - Visual hierarchy
  - Interaction and flow
  - Accessibility and contrast
  - Microcopy and labels
  - Touch target and spacing (mobile)
Format: a copy-pasteable library of comment starters the team uses in every Figma review.
Each template ends with "[add specific observation]" so reviewers fill in the detail.
```

### Follow-Up 2: Stakeholder Design Review Agenda
```markdown
Convert the design critique session above into a stakeholder presentation format for non-designers.
Stakeholders attending: [LIST — e.g., "CEO, Head of Engineering, Head of Marketing"]
Available time: [30 / 45 / 60 minutes]
Goal: get a decision on [SPECIFIC DECISION NEEDED]

Write the meeting agenda:
(1) Context: why we are here and what decision we need (5 minutes)
(2) The user problem: evidence-based, not assumption-based (5 minutes)
(3) Design walkthrough: 3 screens maximum — show the problem, the solution, the key interaction (10 minutes)
(4) The question for the room: one crisp decision the stakeholders must make (5 minutes)
(5) Q&A with facilitation guide: how to redirect off-topic "design by committee" comments (10 minutes)
Write the designer's verbatim presenter notes for each section.
```

---

## Designer Wisdom

- **Critique the work, never the designer.** "This layout makes it hard to find the primary action" is critique. "You put the button in the wrong place" is an attack. The phrasing distinction seems subtle, but it determines whether designers feel psychologically safe enough to bring their riskiest, most creative work to critique.
- **Separate critique from ideation.** When someone in critique says "What if we did X instead?" — capture the idea and move on. Critique sessions are not design studios. The improvement ideas generated in critique are inputs for the designer to evaluate — not decisions to implement immediately.

**Tools that pair with this prompt:**
- **Figma** — share link with comment permissions for async critique
- **Loom** — async video walkthroughs for remote designers to receive feedback
- **Miro** — collaborative dot-voting and observation clustering in live sessions
- **Notion** — structured critique notes database with linked Figma files
