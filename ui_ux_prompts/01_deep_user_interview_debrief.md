# 01. Deep User Interview Debrief
**Category:** User Research · 🔀 Mix (Web + Phone)
**Phase:** Discovery — after 5+ user interviews are complete
**Where:** Miro / FigJam / Notion — synthesis workspace

---

## Strategic Context

Raw interview transcripts are the most valuable asset in product design — and the most commonly wasted. Teams transcribe interviews, dump them into a folder, then write a 1-page summary based on memory. The result is a report shaped by what the interviewer *expected to hear*, not what users actually said.

Senior UX researchers know that the real insight is **what users do not say explicitly**. Users describe symptoms ("the screen is confusing"), not root causes ("the mental model I have about this workflow doesn't match how you organized the navigation"). Your job when analyzing transcripts is to decode the language users use and extract the underlying mental model, emotional driver, and unstated desire hidden underneath.

The best research teams use **affinity diagramming** before writing any synthesis — grouping raw quotes by theme before any narrative is attached. This prompt forces the LLM into that discipline, producing an insight hierarchy rather than a narrative summary.

---

## Relevant Dimensions

This prompt is platform-agnostic — it applies to any platform your users are describing.

**When presenting your synthesis output:**
- Display it on a web canvas (1280 px max-width, 80 px margins) in a Notion/Miro page.
- If presenting findings on a mobile device, use **390 × 844** canvas and 16 pt side margins.
- All quotes should be displayed in **Body text (16 px / 17 pt)** with a **4:1 minimum contrast** against the background.

---

## The Master Prompt

```markdown
You are a Principal UX Researcher with 15+ years of experience running discovery research at top-tier product companies. I will paste raw user interview transcripts below.

Your task is to produce a rigorous, structured research synthesis report. Work through this process in order:

STEP 1 — RAW QUOTE EXTRACTION:
- Extract every meaningful direct quote from the transcripts.
- Tag each quote with: Speaker ID (User A, User B, etc.), Topic, and Emotional Intensity (Neutral / Frustrated / Delighted / Confused).

STEP 2 — THEMATIC CLUSTERING:
- Group quotes into themes using affinity mapping logic.
- Name each theme with a verb phrase (e.g., "Struggling to compare options" not "Comparison").

STEP 3 — INSIGHT HIERARCHY:
Rank themes by: Frequency (how many users mentioned it) × Severity (how much it blocks their goal).
For each theme produce:
(1) The surface complaint — what users literally say
(2) The root cause — what structural problem underlies it
(3) The unstated desire — what they actually want (not their proposed solution)
(4) The mental model mismatch — where their expectation differs from how the product works
(5) Evidence quotes — minimum 2 verbatim quotes per theme

STEP 4 — OPPORTUNITY SPACES:
- List 3–5 opportunity spaces ranked by frequency × severity.
- For each opportunity: write a one-sentence "How Might We" framing.

STEP 5 — ASSUMPTIONS TO INVALIDATE:
- List 3 product team assumptions that these transcripts either support or challenge.

Output as a structured research report with clear section headers.
Do not paraphrase quotes — preserve the user's exact words.

Transcripts:
[PASTE TRANSCRIPTS HERE]
```

---

## Follow-Up Prompts

### Follow-Up 1: Insight Validation Workshop Facilitator
```markdown
Based on the research synthesis above, design a 60-minute insight validation workshop for the product team.
Include:
(1) A warm-up activity to align the team on the key themes (10 minutes).
(2) A structured voting activity to prioritize the top 3 opportunities (20 minutes).
(3) An assumption-mapping exercise for the 3 challenged assumptions (20 minutes).
(4) A synthesis activity to agree on the top "How Might We" statement to pursue (10 minutes).
Output: Facilitator script with timings, materials needed, and instructions for each activity.
```

### Follow-Up 2: Research-to-Design Brief Translator
```markdown
Convert the top 3 ranked opportunity spaces from the research synthesis into Design Briefs.
For each opportunity, write a brief containing:
(1) The design challenge in one sentence.
(2) The user context (who, when, and what they are trying to do).
(3) The constraints the solution must respect.
(4) 3 success criteria — how will we know the design solves this problem?
(5) What must NOT be in the solution (the anti-solution).
Format: ready to hand directly to a UX designer or design sprint facilitator.
```

---

## Designer Wisdom

- **Separate observation from interpretation.** When synthesizing, never write "users want X." Write "users say Y, which suggests X." The distinction protects your team from building on assumptions disguised as facts.
- **The word "confusing" is a dead end.** When a user says something is confusing, dig deeper. Ask what they expected to happen. The answer to *that* question is the insight — not the word "confusing."

**Tools that pair with this prompt:**
- **Dovetail** — for tagging and clustering transcripts with AI assistance
- **Otter.ai / Rev** — for auto-transcription before you paste into this prompt
- **FigJam** — for visual affinity mapping after running this prompt
- **Notion** — for storing the final synthesis as a living document
