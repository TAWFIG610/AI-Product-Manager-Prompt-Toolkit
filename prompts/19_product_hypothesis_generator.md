# 19. Product Hypothesis Generator

## Strategic Context
The most expensive way to validate a product idea is to write code. A 50-year PM veteran knows that engineering time is precious, and building a feature that nobody wants is the ultimate waste of resources. The objective of product discovery is to separate **opinions** from **behaviors**. You must frame your ideas as testable, falsifiable hypotheses, identify the riskiest assumptions, and run low-fidelity experiments to validate demand before committing a single developer.

---

## The Master Prompt

```markdown
Act as a Principal Product Discovery Coach and Innovation Strategist with 20+ years of experience leading lean discovery cycles. Help me validate a product/feature idea before committing engineering resources:

Product/Feature Idea: [DESCRIBE THE FEATURE OR PRODUCT IDEA]
Assumed Customer Problem: [WHAT SPECIFIC PROBLEM DOES IT SOLVE]
Assumed Target User: [WHO IS THIS FOR]
Proposed Solution: [HOW THE SOLUTION WORKS]

Deliver a structured validation blueprint covering:

1. THE FALSIFIABLE HYPOTHESIS:
   - Formulate a strict, scientific hypothesis:
     "We believe that [target user] has an acute problem with [assumed problem]. We will know this is true when we observe [quantitative, behavior-based metric/signal] in response to [our experiment/intervention] within [timeframe]."

2. RISKIEST ASSUMPTIONS MATRIX:
   - Identify and prioritize the assumptions underlying this idea. Categorize them into:
     - Desirability: Do customers actually care about this problem? Will they pay for it?
     - Feasibility: Can we technically build this with our current stack?
     - Viability: Does this fit our business model, legal constraints, and margins?
     - Usability: Can users understand how to use the solution?
   - Identify the top 3 assumptions that, if false, will kill the project.

3. LOW-FIDELITY EXPERIMENT DESIGN (Cheap & Fast):
   - Suggest 3 distinct, scrappy experiments to test the top assumptions (e.g., Fake Door Test, Landing Page Test, Concierge MVP, Wizard of Oz Prototype).
   - For each experiment, specify:
     - Setup: How to build it in under 3 days using no-code or mockups.
     - Cost: Target budget (aim for < $100).
     - Timeline: How long to run the test.
     - Metric: What event will we measure?

4. THE GO/NO-GO DECISION MATRIX:
   - Kill Criteria: Specific negative metrics (e.g., click rate < 2%, zero conversion, user confusion) that will cause us to abandon the idea.
   - Green Light Criteria: Positive metrics that will justify moving this feature into the engineering backlog.
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: Landing Page (Fake Door) Setup
```markdown
For the Landing Page Test proposed:
1. Write the copywriting framework: Headline, sub-headline, and description of the feature.
2. Design the Call-to-Action (CTA) button copy (e.g., "Join Beta" or "Upgrade Now").
3. Write the "Feature Coming Soon" modal copy that appears after they click, thanking them, explaining that we are prioritizing development, and asking for their feedback via a 2-question survey.
```

### Follow-Up 2: The Concierge MVP Script
```markdown
Assume we want to run a Concierge MVP where we manually perform the service for 10 clients:
1. Write the step-by-step workflow: What parts of the process are done by the user, what parts are done manually by us behind the scenes, and what is delivered to the customer?
2. Design the onboarding script to recruit these 10 pilot users.
```

---

## 50-Year PM Wisdom
* **Behavior Over Opinions**: Never ask a user, "Would you use this feature?" They will always say "yes" to be polite or because they imagine an idealized version of themselves. Instead, ask them to take action: click a button, give you their email, or perform a manual task. If they won't pay with their time or money, they don't actually want the feature.
* **Fall in Love with the Problem, Not the Solution**: If your validation test fails, it doesn't mean the customer doesn't have a problem; it means your solution was wrong. Pivot the solution, but keep studying the problem. If you fall in love with your code, you will build a monument to your own ego that nobody uses.
