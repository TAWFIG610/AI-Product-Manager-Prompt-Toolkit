# 05. Competitor Product Teardown

## Strategic Context
A competitor teardown is not just a screenshot gallery of their UI. A 50-year PM veteran knows that a teardown must reverse-engineer the competitor’s business model, customer psychology, and retention engines. You want to understand *why* they built features the way they did, the hidden friction they are hiding, and how they utilize behavioral psychology to lock in users.

---

## The Master Prompt

```markdown
Act as a Principal Product Manager and Competitive Intelligence Lead with 20+ years of experience analyzing product architectures and user experiences. Perform a comprehensive, critical product teardown of the following competitor:

Competitor Product Name: [PRODUCT NAME]
Target Market/Niche: [TARGET MARKET]

Analyze the competitor's product across the following 6 pillars:

1. ONBOARDING & TIME-TO-VALUE (TTV):
   - Step-by-step sign-up flow analysis: Count the clicks, fields, and screen changes required.
   - Friction Points: Where is cognitive load highest? (e.g., forced integrations, email verifications).
   - The "Aha!" Moment: Where does a user first experience the core value proposition? How long (in minutes/actions) does it take to reach?

2. CORE RETENTION LOOPS:
   - What is their primary habit loop? (Trigger -> Action -> Variable Reward -> Investment).
   - What hook mechanisms do they use to bring users back? (e.g., notification systems, weekly digests, network effects).
   - Investment Phase: How do users accumulate data, reputation, or custom configurations that make switching away difficult?

3. MONETIZATION MECHANICS:
   - What is their pricing structure? Where is the paywall encountered?
   - Value Metric: What variable are they charging for? (e.g., user seats, usage limits, features).
   - Upsell Triggers: How do they nudge free or lower-tier users to upgrade?

4. UX & HEURISTIC EVALUATION:
   - Evaluation of navigation, information architecture, and accessibility.
   - Key micro-interactions that delight users or cause frustration.
   - Mobile vs. Desktop optimization differences.

5. ANALYSIS OF WEAKNESSES & DEFICIENCIES (Review Signals):
   - What are users complaining about on Reddit, G2, Trustpilot, or App Store reviews? (Highlight 3 key trends).
   - Where does their customer support likely spend the most time?

6. STRATEGIC OPPORTUNITIES (Steal vs. Fix):
   - What features or UX patterns should we "steal" because they are industry-standard or exceptionally well-designed?
   - What should we "fix" or build completely differently to capture their unhappy users?
   - What should we completely "avoid" because it is a strategic dead-end?

Be objective, analytical, and highly critical. Do not summarize with generic statements—use concrete examples of their UI/UX and product flows.
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: Detailed Friction Log
```markdown
Create a click-by-click Friction Log for [COMPETITOR PRODUCT]'s onboarding flow. 
- Map out each screen from home page to core workspace.
- For each step, assign a friction score (1 to 5, where 5 is high friction) and explain why (e.g., "required phone number", "vague input instructions").
- Recommend how our product can streamline this exact journey to cut time-to-value in half.
```

### Follow-Up 2: Counter-Strategy Design
```markdown
Identify the competitor's biggest product strength (e.g., deep integrations or an established user community). 
1. Design a product feature or marketing angle that turns this strength into a weakness or irrelevancy for a subset of users.
2. Outline how we can position our product to exploit this vulnerability.
```

---

## 50-Year PM Wisdom
* **Look at the Forums**: The best competitor intelligence isn't on their marketing website or in their PR releases. It is on their public support forums, GitHub issue trackers, Subreddits, and G2 reviews. If users are complaining about an issue for 6 months and it hasn't been fixed, you've found a major entry vector.
* **Understand the Legacy Debt**: Large competitors cannot easily change their product because they are beholden to their oldest, highest-paying customers. They are trapped. Capitalize on their inability to move fast by building for the modern workflow of the new generation.
