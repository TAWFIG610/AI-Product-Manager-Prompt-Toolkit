# 18. Negotiation & Trade-off Facilitator

## Strategic Context
Product management is the art of saying "no." You are constantly caught between engineering (who wants to build robust architecture), sales (who wants custom features for their next deal), and design (who wants perfect user flows). A 50-year PM veteran knows that conflict is healthy, but indecision is fatal. The secret to resolving trade-offs is classifying decisions as **Type 1 (irreversible)** or **Type 2 (reversible)** and framing the options in terms of business impact and trade-offs.

---

## The Master Prompt

```markdown
Act as a veteran Chief Product Officer (CPO) and Conflict Mediator with 25+ years of experience navigating boardroom and engineering standoffs. Help me evaluate and communicate a critical product decision:

Decision to Make: [DESCRIBE THE DECISION, e.g., Rewrite core backend or launch feature Y]
Option A: [DESCRIBE OPTION A]
Option B: [DESCRIBE OPTION B]
Option C (if any): [DESCRIBE OPTION C]
Stakeholders Involved: [e.g., VP of Sales, Head of Engineering, CFO]
Deadline for Decision: [DATE OR TIME PRESSURE]
Key Constraints: [e.g., budget limits, developer bandwidth, customer commitments]

Deliver a structured decision framework containing:

1. STRATEGIC OPTIONS ANALYSIS MATRIX:
   - For each option, provide:
     - Gained Value: What does the business and customer win?
     - Sacrificed Value: What is the opportunity cost? What are we giving up? (Be brutally honest).
     - Stakeholder Alignment: Which team wins, and which team is disappointed?
     - Reversibility Check: Is this a Type 1 decision (one-way door, highly irreversible, costly to change) or a Type 2 decision (two-way door, easy to roll back)?
     - Risk Score: Low / Medium / High with a 1-sentence engineering/business explanation.

2. CPO RECOMMENDATION & RATIONALE:
   - Make a clear, definitive recommendation on which option we should choose.
   - Explain the strategic reason why this choice maximizes long-term value, even if it creates short-term friction.

3. THE DECISION MEMO (Stakeholder Copy):
   - Write a 200-word Decision Memo tailored for the executive sponsor (CEO/Board) explaining the decision, the options weighed, the chosen path, and the trade-offs we have explicitly accepted.

4. THE RED-LINE TRIGGER:
   - What is the single metric, milestone slip, or customer reaction that would prove our decision was wrong and require us to pivot immediately?

5. OBJECTION HANDLING SCRIPTS:
   - Write a short conversation script helping me respond to the top objection from the most vocal dissenting stakeholder.
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: Decision Matrix Classifier
```markdown
Here are 5 upcoming product decisions we need to make:
[LIST 5 PRODUCT DECISIONS]
1. Classify each decision as Type 1 (irreversible, high cost) or Type 2 (reversible, fast to undo).
2. For the Type 2 decisions, outline a "Fast Track" process to decide and execute them within 48 hours without stakeholder committee approval.
```

### Follow-Up 2: Pre-Mortem Risk Workshop
```markdown
Assume we have chosen the recommended option. Write a facilitation plan for a 45-minute Pre-Mortem session with the cross-functional team:
1. Explain how to set up the prompt: "Imagine it is 6 months from now, and this choice has failed catastrophically. How did it happen?"
2. Outline how to categorize the failure risks (technical, market, operational) and rank them to build a risk monitoring plan.
```

---

## 50-Year PM Wisdom
* **Disagree and Commit**: You will never get 100% agreement on hard decisions. Your goal is not consensus; it is alignment. Once the decision is made, every member of the team must "disagree and commit." If they undermine the decision after the meeting, it is a management failure.
* **Focus on the Opportunity Cost**: When stakeholders argue for Option A, they are looking at the benefit of Option A. Your job as a PM is to remind them of the opportunity cost—what we *cannot* build because we chose Option A. Every choice is a trade-off.
