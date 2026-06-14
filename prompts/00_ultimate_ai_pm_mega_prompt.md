# The Ultimate AI PM Mega Prompt

## Strategic Context
The **AI PM Mega Prompt** consolidates the entire product management lifecycle into a single, comprehensive workspace instruction. It collapses all 20 individual prompt domains (Discover, Define, Build, Ship, Learn) into 19 structured sections across 5 phases, culminating in a one-page product brief. 

Use this mega prompt when initiating a new project to generate a complete, end-to-end product playbook in a single run.

---

## The Master Mega Prompt

```markdown
You are a world-class AI Product Manager with 100 years of combined experience across market research, product strategy, UX, engineering collaboration, growth, pricing, retention, and post-launch learning.

I am going to give you ONE product idea or feature. Your job is to walk me through the complete product lifecycle — from raw idea to tested, shipped feature — using the 5-phase PM system below. Work through each phase in order. Be specific, actionable, and ruthlessly practical. No vague advice. No filler. Treat this like a real product at a well-funded startup.

═══════════════════════════════════════════
MY PRODUCT / IDEA:
[DESCRIBE YOUR IDEA IN 1–3 SENTENCES HERE]

MY TARGET USER:
[WHO IS THIS FOR? BE SPECIFIC]

MY MARKET:
[WHAT INDUSTRY OR SPACE IS THIS IN?]

MY STAGE:
[IDEA / PRE-LAUNCH / EARLY / GROWTH / SCALE]
═══════════════════════════════════════════

Now execute the full PM lifecycle below. Complete every section. Do not skip any phase.

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 1 — DISCOVER
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[1A] HYPOTHESIS (Prompt 19)
Write a falsifiable product hypothesis:
"We believe [user type] has a problem with [situation]. We will know this is true when [measurable signal]."

Then list:
• The 3 riskiest assumptions buried in this idea
• For each assumption — the fastest, cheapest test to validate it (fake door / landing page / concierge MVP / 5 user interviews)
• Kill criteria: what result kills this idea
• Green light criteria: what result makes us start building

---

[1B] MARKET LANDSCAPE (Prompt 1)
Analyze the market for this product:
• Top 5 competitors — pricing, strengths, weaknesses
• The single biggest gap in the market right now
• Emerging trends in the next 18 months
• Our recommended entry angle (how we win, not just what we build)

---

[1C] USER PERSONAS (Prompt 2)
Create 3 realistic, specific user personas for this product.
For each:
• Name, age, occupation, income
• Primary goal (product-specific)
• Top 3 frustrations with current solutions
• Behavior patterns and motivations
• A direct quote they'd say about their pain
• Which features matter most to them

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 2 — DEFINE
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[2A] METRICS FRAMEWORK (Prompt 14)
Before writing any requirements, define success:
• North Star Metric — the single number that proves we're delivering value (explain why)
• 3–5 input metrics that drive the North Star
• 3 health/guardrail metrics (what breaks when we're failing)
• 3 vanity metrics to AVOID and why
• Metrics tree (show the hierarchy with indentation)
• 5 key events to instrument on day 1

---

[2B] PRODUCT REQUIREMENTS DOCUMENT — PRD (Prompt 3)
Write a complete PRD:
• Problem Statement — the exact pain, for whom, and why now
• Goals — what success looks like in 30/60/90 days
• Non-Goals — explicitly what we are NOT building
• Success Metrics — tied to the metrics framework above
• User Stories — at least 5, with full acceptance criteria for each
• Technical Considerations — known constraints or dependencies
• Edge Cases & Risks — at least 5, with severity rating
• Open Questions — what must be resolved before we build

---

[2C] FEATURE PRIORITIZATION (Prompt 6)
List the 5–8 features implied by this PRD.
Prioritize using the RICE framework:
• Reach / Impact / Confidence / Effort for each
• RICE Score
• Final ranked list
• Top 3 to ship in the first sprint — with clear reasoning

---

[2D] COMPETITOR TEARDOWN (Prompt 5)
Pick the #1 competitor identified in Phase 1. Tear it down:
• Onboarding flow — steps, friction, aha moment timing
• Retention loops — what brings users back
• Monetization mechanics
• Their biggest UX weakness we can exploit
• One thing we steal, one thing we do differently

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 3 — BUILD
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[3A] USER STORIES + ACCEPTANCE CRITERIA (Prompt 4)
Take the top 3 prioritized features from [2C].
For each feature write:
• 2–3 Agile user stories (As a / I want / So that)
• 3–5 acceptance criteria per story (specific + testable)
• Definition of Done
• Any dependencies or blockers to flag

---

[3B] UNIT TEST CASES (Prompt 12)
For the #1 user story from [3A], write a complete test suite:

| Test ID | Test Name | Preconditions | Steps | Expected Result | Type | Priority |
|---------|-----------|---------------|-------|-----------------|------|----------|

Cover ALL of:
• Happy path (valid inputs, expected flow)
• Boundary values (min/max edge of inputs)
• Negative cases (wrong/missing inputs)
• Edge cases (race conditions, empty states, timeouts)
• Security checks (unauthorized access, injections)

Minimum 10 test cases. Format ready for Jira or TestRail.

---

[3C] SPRINT PLAN (Prompt 15)
Plan the first sprint:
• Sprint goal (one sentence the whole team rallies around)
• Story point estimates for each user story (Fibonacci)
• Recommended sprint composition for a team of 3–4 engineers
• Highest-risk item and how to de-risk it before day 3
• Definition of "sprint success"

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 4 — SHIP
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[4A] GO-TO-MARKET PLAN (Prompt 13)
Write the full launch plan:
• Launch goals — 30 / 60 / 90 day targets (specific numbers)
• Target segment to launch to first — and why
• Messaging framework: headline + subheadline + 3 key benefits
• Channel strategy — which 3 channels, in what order, why
• Pre-launch checklist — 8 things that must be true before we ship
• Launch day playbook — what happens hour by hour on day 1
• Kill criteria — what signal makes us pause the launch

---

[4B] A/B TEST PLAN (Prompt 8)
Design 3 experiments to run at launch:
For each:
• Hypothesis ("We believe X will cause Y because Z")
• Control (A) vs Variant (B)
• Primary metric + guardrail metric
• Minimum sample size and why
• Expected lift
• Risk if the test goes wrong

---

[4C] STAKEHOLDER UPDATE (Prompt 11)
Write a launch-week stakeholder update (assume status: ON TRACK):
• TL;DR — one sentence
• Status: GREEN / AMBER / RED with reasoning
• Key wins this week (3 bullets)
• Risks on radar (2 items, each with owner + ETA)
• What I need from leadership (specific ask)
• Next milestone: date + what it unlocks

---

[4D] PRICING STRATEGY (Prompt 16)
Recommend a pricing model:
• Recommended model (per seat / usage / flat / freemium / hybrid) — with reasoning
• 3-tier structure: names, price points, what's included
• Value metric (the axis we charge on and why)
• Freemium vs free trial — which and why
• Middle-tier anchoring strategy
• First 90-day pricing experiment

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
PHASE 5 — LEARN
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

[5A] CHURN & RETENTION DIAGNOSIS (Prompt 17)
Assume it's 30 days post-launch. Retention is below target.
Diagnose and prescribe:
• 3 most likely root causes (ranked by probability)
• Aha moment audit — is the user reaching core value fast enough?
• 5 retention experiments ranked by expected impact
• Lifecycle message strategy — what to send at day 1, 3, 7, 14, 30
• Leading indicator we'll track to know it's improving

---

[5B] TRADE-OFF DECISION (Prompt 18)
At day 45 post-launch, engineering says: "We can either fix performance bugs OR ship the #2 feature on the roadmap. Not both this sprint."

Frame this decision:
• Option A: Fix bugs first
• Option B: Ship new feature first
• For each: what we gain, what we give up, reversibility, risk level
• Your recommendation and the reasoning
• One-paragraph decision memo ready to send to the CEO

---

[5C] 6-MONTH ROADMAP (Prompt 10)
Build the full roadmap:

Phase 1 — Month 1–2: Foundation
• Features list + rationale
• Success metric + target
• Risk + mitigation

Phase 2 — Month 3–4: Growth
• Features list + rationale
• Success metric + target
• Risk + mitigation

Phase 3 — Month 5–6: Retention & Monetization
• Features list + rationale
• Success metric + target
• Risk + mitigation

North Star for the 6-month period: [state it]
What gets cut if the timeline slips: [be specific]

---

[5D] POST-MORTEM TEMPLATE (Prompt 20)
Assume one thing went wrong in the first 60 days (you choose what — make it realistic for this type of product). Write the blameless post-mortem:
• Executive summary (3 sentences, facts only)
• Root cause using 5 Whys
• 2 contributing factors
• What the team did well
• 5 action items (specific, time-bound, role-assigned)
• One process change that prevents this class of failure
• User communication template

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
FINAL DELIVERABLE — THE ONE-PAGE BRIEF
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

After completing all phases above, write a One-Page Product Brief that a founder, investor, or new team member could read in 3 minutes and understand:

• The problem (1 sentence)
• The solution (1 sentence)
• The user (1 sentence)
• The market gap (1 sentence)
• North Star Metric and current target
• Top 3 features in priority order
• 6-month roadmap summary (3 bullets)
• Biggest risk and how we're mitigating it
• What success looks like at month 6

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

RULES FOR YOUR RESPONSE:
1. Complete every section. Do not skip or summarize phases.
2. Be specific to MY product — no generic examples.
3. Use real numbers, real metrics, real test cases.
4. Every recommendation must have a reason.
5. Write it so a new engineer, designer, and investor could each pick up their relevant section and immediately know what to do.
6. If you need to make an assumption, state it clearly before using it.
```

## How To Use This Mega Prompt

1. Copy the entire block above.
2. Replace the 4 placeholder fields at the top:
   - `MY PRODUCT / IDEA:`
   - `MY TARGET USER:`
   - `MY MARKET:`
   - `MY STAGE:`
3. Paste it into Claude, ChatGPT, or Gemini.
