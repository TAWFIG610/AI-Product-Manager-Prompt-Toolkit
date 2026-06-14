# 10. Jobs-to-Be-Done Feature Map
**Category:** Product Strategy · 🔀 Mix (Web + Phone)
**Phase:** Early Discovery or Roadmap Planning — before committing to a feature list
**Where:** Platform-agnostic strategic exercise — outputs feed into design and PM work

---

## Strategic Context

The Jobs-to-Be-Done (JTBD) framework was articulated by Clayton Christensen at Harvard Business School with the famous "milkshake" research. Customers were hiring McDonald's milkshakes not for lunch but for their morning commute — a boring, lonely drive that the thick shake made tolerable for 23 minutes. Understanding the actual job being hired (make a boring commute bearable) versus the assumed job (satisfy hunger) changed the product strategy entirely.

In digital products, JTBD prevents a common design trap: **building features that users say they want instead of features that actually do the job they need done**. When a user says "I need a better export function," their Job-to-Be-Done is probably "report to my manager without embarrassment." A better export function is one solution — but it might not be the best one.

JTBD has three dimensions that senior product designers always analyze together:
1. **Functional job**: the practical task (import data, generate a report, notify my team)
2. **Emotional job**: how the user wants to feel while doing it (competent, trusted, in control)
3. **Social job**: how they want to be perceived by others (professional, organized, innovative)

The highest-value product opportunities are almost always hidden in the emotional and social jobs — the functional job is what the user articulates, but the emotional and social jobs are what they actually pay for.

---

## Relevant Dimensions

This is a strategic analysis exercise. The outputs are used to inform design and product decisions.

**When visualizing the JTBD matrix in your design tools:**
- Web display: content area **1120 px max**, 12-column grid
- Use **H4 (24 px / Title Small 20 pt)** for matrix section headers
- Use **Body (16 px / 17 pt)** for matrix cell content
- Use **Green (Success-200: #97C459)** for "satisfied" states
- Use **Amber (Warning-200: #EF9F27)** for "partially met" states
- Use **Coral (Coral-200: #F0997B)** for "gap / unmet" states

**Table column spacing:**
- Desktop: each column approximately **200–280 px** wide
- Mobile (if showing a simplified view): collapse to 2-column layout at 390 pt

---

## The Master Prompt

```markdown
You are a Senior Product Strategist and JTBD Practitioner with expertise in applying the Jobs-to-Be-Done framework to SaaS and consumer product design decisions.

Product: [DESCRIBE YOUR PRODUCT IN 2–3 SENTENCES]
User segments: [LIST 3 DISTINCT USER SEGMENTS — e.g., "solo freelancers, team leads at SMBs, enterprise project managers"]

Apply the Jobs-to-Be-Done framework to every segment.

STEP 1 — JTBD ANALYSIS PER SEGMENT:
For each segment, identify:
  Functional Job: What specific task are they trying to accomplish? (verb + object)
  Emotional Job: How do they want to feel while doing it? (use emotion words)
  Social Job: How do they want to be perceived by others while using this? (colleagues, clients, managers)

STEP 2 — FEATURE GAP MATRIX:
Map every existing feature against the identified jobs using this classification:
  ✅ Fully satisfied — feature completely addresses this job
  ⚠️ Partially met — feature addresses part of the job but with friction or limitation
  ❌ Gap — job is not addressed by any current feature

Output as a matrix: JTBD (rows) × Features (columns)

STEP 3 — OPPORTUNITY RANKING:
Rank the top 5 unmet or partially-met JTBDs by:
  Market pull = (number of segments affected) × (severity of the gap) × (frequency of the job)
For each ranked opportunity:
  - Write a "How Might We" statement
  - List 2–3 potential feature directions (do NOT over-constrain — preserve design latitude)
  - Identify the risk: what assumption about user behavior must be true for this opportunity to be real?

STEP 4 — EMOTIONAL JOB DESIGN IMPLICATIONS:
For the top 3 ranked opportunities:
  - Translate the emotional job into specific UX design requirements
    (e.g., "User wants to feel in control" → "Show a clear progress indicator, allow undo on every action, never hide the current system state")
  - List 3 design decisions that must be made to satisfy the emotional job
  - List 3 design decisions that would violate the emotional job (anti-requirements)

Output: Full JTBD analysis + feature gap matrix + ranked opportunity backlog + emotional design requirements.
```

---

## Follow-Up Prompts

### Follow-Up 1: Feature Concept Brief from Top JTBD
```markdown
Take the #1 ranked unmet JTBD from the analysis above.
Write a Feature Concept Brief:
(1) JTBD statement: the full functional + emotional + social job description
(2) User scenario: a 5-sentence narrative describing the context in which this job arises
    (day of week, what just happened, who is watching, what is at stake)
(3) Success definition: how does the user feel and what have they accomplished when the job is done?
(4) Feature concept: a 3-sentence description of the minimum feature needed to do the job
(5) What this is NOT: explicit non-requirements to prevent feature creep
(6) Open questions: 3 things that must be validated with real users before building
```

### Follow-Up 2: Persona-to-JTBD Crosswalk
```markdown
Using the JTBD analysis above, map each JTBD to the user personas [PASTE YOUR PERSONA NAMES].
For each persona:
(1) Their primary JTBD (the job they hire the product for most frequently)
(2) Their secondary JTBD (the job they care about but use the product for less often)
(3) Their "job they don't know they have" (the latent need they haven't articulated)
(4) The feature that, if we built it perfectly, would make them recommend the product to a colleague
Output: crosswalk table + one-sentence product pitch customized for each persona.
```

---

## Designer Wisdom

- **The job stays stable. The solution changes.** People have been hiring solutions to "communicate quickly with someone far away" for 100 years — from telegraph to telephone to email to SMS to Slack. The job never changed. The solutions changed entirely. When you design to the job, you build products with a long shelf life.
- **Listen for "so that."** When a user says "I want a better search," ask "so that...?" Keep asking until they cannot answer. The last answer before they run out of words is the real job. Everything before it is an assumed solution.

**Tools that pair with this prompt:**
- **Miro / FigJam** — for building collaborative JTBD matrices with the product team
- **Notion** — for documenting and linking JTBD insights to roadmap items
- **Dovetail** — for tagging interview transcripts with JTBD themes
- **Jobs-to-Be-Done.com** — Tony Ulwick's Outcome-Driven Innovation resources
