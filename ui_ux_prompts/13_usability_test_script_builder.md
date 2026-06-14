# 13. Usability Test Script Builder
**Category:** User Testing · 🔀 Mix (Web + Phone)
**Phase:** Before or during build — ideally when a clickable prototype exists
**Where:** Test on real devices: phone at 390 × 844 pt/dp · web at 1280 px viewport

---

## Strategic Context

Usability testing is the most cost-efficient research method in product design. Jakob Nielsen's research established that **5 users find 85% of usability problems**. You do not need a large panel. You need the right tasks and the right facilitation technique.

The critical facilitation skill is the **Think-Aloud Protocol**, developed by Clayton Lewis and first described by Newell and Simon. Participants verbalize their thought process as they interact with the product. The facilitator's job is to keep them talking without leading them — a discipline that requires specific techniques and specific script phrasing.

The two most dangerous facilitator behaviors to avoid:
1. **Rescuing users**: when a user struggles, the instinct is to help. Suppress it. The struggle is the data.
2. **Leading questions**: "Did you find that easy?" is a leading question. "How did that feel?" is neutral. The phrasing of every question matters.

The script structure that senior UX researchers use:
1. **Briefing**: explain the purpose (testing the design, not the participant)
2. **Baseline questions**: understand their existing behavior and context
3. **Tasks**: structured, scenario-based, measurable
4. **Probes**: neutral follow-up questions for each task
5. **Debrief**: open-ended impressions and suggestions

A great usability task has three properties: it has a clear start condition, a clear end condition, and uses scenario language (not "click the search button" but "imagine you are looking for...").

---

## Relevant Dimensions

**Session logistics:**
- Session duration: **45–60 minutes** per participant (90 minutes maximum — beyond this, fatigue degrades data quality)
- Participant count: **5 participants** for 85% issue coverage · **8 participants** for distinct segment comparison
- Recording: screen recording + webcam for face/body language — inform participant and get consent

**Platform-specific test environment:**
- Mobile: test on a physical device at **390 × 844 pt/dp** (medium) and one at **320 × 568** (small)
- Web: test at **1280 × 800 px viewport** on a standard laptop — use Chrome DevTools to normalize viewport
- Remote testing: use Maze, UserZoom, or Lookback for unmoderated remote sessions

**Timing for tasks:**
- Give each task a **target completion time** (e.g., "we expect this to take under 60 seconds")
- Record **actual completion time** for benchmarking
- Flag if completion exceeds **2× target time** as a critical failure signal

---

## The Master Prompt

```markdown
You are a Principal UX Researcher with 15+ years of experience designing and facilitating usability studies for mobile apps and web products.

Product: [DESCRIBE YOUR PRODUCT]
Prototype fidelity: [Low-fi wireframes / Medium-fi clickable prototype / High-fi near-final build]
Platform: [iOS / Android / Web / Both mobile and web]
Research objectives: [LIST 3–5 specific questions you need answered, e.g., "Can users complete checkout without assistance?"]
User profile: [DESCRIBE THE TARGET PARTICIPANT — experience level, context, job title if B2B]

Write a complete moderated usability test script:

SECTION 1 — INTRODUCTION SCRIPT (3–5 minutes):
Write a verbatim introduction the facilitator reads aloud, covering:
  - Purpose: "We are testing the design, not you — there are no wrong answers."
  - Think-Aloud Protocol instruction: how to verbalize thoughts as they navigate
  - Recording consent statement
  - Ground rules: don't ask for help, stop if uncomfortable, ask about process not feelings

SECTION 2 — WARM-UP BASELINE QUESTIONS (5–7 minutes):
Write 4–5 open-ended questions to understand the participant's:
  - Current behavior in this domain (without the product)
  - Tools they currently use and frustrations with them
  - Frequency and context of the relevant task
These are NOT about your product — they establish baseline context.

SECTION 3 — 5 USABILITY TASKS:
For each task:
  Task number and title (descriptive, e.g., "Task 3: Finding a past order")
  Scenario: a realistic story context (one paragraph, present tense, includes who/what/why)
  Task prompt: the exact sentence the participant reads on a card (max 2 sentences)
  Target element: what the participant should end up at if they succeed (for observer scoring)
  Success criteria: what counts as task completion
  Failure criteria: what counts as task failure
  Time limit: recommended max time before facilitator intervenes
  Observer notes template: what to track during this task

SECTION 4 — PROBING QUESTIONS (per task):
For each task, write 3 neutral follow-up probes:
  One about process: "Can you walk me through what you were thinking when..."
  One about expectation: "What did you expect to happen when you tapped/clicked..."
  One about emotion: "How did that feel compared to how you usually do this?"
Probes must be neutral — never leading. Avoid "Did you find that intuitive?"

SECTION 5 — SYSTEM USABILITY SCALE (SUS):
Include the standard 10-question SUS questionnaire exactly as written.
Add instructions: how to score it (alternating scoring method) and what the benchmark scores mean.

SECTION 6 — DEBRIEF (5 minutes):
Write 3 open-ended closing questions:
  Overall impression
  What would they change first
  Would they use this — and why or why not
Close with verbatim facilitator thank-you and explanation of next steps.

Output: complete, verbatim script the facilitator can print and use on the day of testing.
```

---

## Follow-Up Prompts

### Follow-Up 1: Synthesis Rainbow Spreadsheet Template
```markdown
Based on the 5 usability tasks above, create a Rainbow Spreadsheet template for synthesis.
The Rainbow Spreadsheet is a structured analysis grid where:
  - Rows = observations / themes (from the sessions)
  - Columns = individual participants (P1, P2, P3, P4, P5)
  - Cell = ✅ passed / ❌ failed / ⚠️ struggled / blank = not observed

Create the template with:
(1) Pre-filled rows for every task (pass/fail tracking)
(2) Pre-filled rows for every usability heuristic violation to watch for (based on Nielsen's 10 heuristics)
(3) 10 blank rows for emergent observations
(4) A severity scoring row: multiply frequency × severity (1–3) for each observation
Output: the spreadsheet structure as a markdown table I can copy into Google Sheets.
```

### Follow-Up 2: Unmoderated Remote Study Design
```markdown
Adapt the moderated usability test script above for an unmoderated remote study using [Maze / Lookback / UserZoom].
For unmoderated format:
(1) Rewrite each task as a self-explanatory card that participants can read without a facilitator
(2) Add multiple-choice check-in questions after each task (confidence rating + what they expected to happen)
(3) Remove any task that requires facilitator probing to interpret — flag these as "moderated only"
(4) Add a screener questionnaire (5 questions max) to qualify participants before they start
(5) Specify: session recording on/off, screen recording on/off, think-aloud prompt (if supported)
Output: a complete self-contained remote study ready to upload to [chosen tool].
```

---

## Designer Wisdom

- **Never ask "Is this clear?" or "Is this easy?"** Users almost universally say yes because they do not want to seem slow. Ask "What would you do next?" instead. The action they take (or don't take) is the real answer.
- **5 sessions in the morning, synthesis in the afternoon.** Run all 5 sessions on the same day with 45-minute gaps between participants. Synthesize immediately — your memory of the sessions is freshest in the 4 hours after the last session. Do not let a week pass before synthesis.

**Tools that pair with this prompt:**
- **Maze** — unmoderated usability testing with task flows and click maps
- **Lookback** — moderated and unmoderated remote research with live observer rooms
- **Dovetail** — AI-assisted synthesis and tagging of session recordings
- **Optimal Workshop** — tree testing, card sorting, and first-click testing
