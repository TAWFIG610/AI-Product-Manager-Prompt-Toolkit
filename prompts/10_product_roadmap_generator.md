# 10. Product Roadmap Generator

## Strategic Context
A roadmap is a strategic tool, not a list of features with dates. A 50-year PM veteran knows that committing to dates 6 months out is a recipe for failure. Instead, a great roadmap focuses on **outcomes**—what problems we are solving in which order, and what success looks like. The roadmap should build on itself: Phase 1 provides the foundation, Phase 2 drives usage, and Phase 3 extracts business value.

---

## The Master Prompt

```markdown
Act as a Chief Product Officer (CPO) and VP of Product with 25+ years of experience managing product portfolios. Build a highly structured, strategic 6-month product roadmap for the following product:

Product Description: [PRODUCT DESCRIPTION]
Target Business Objective: [PRIMARY OBJECTIVE, e.g., Achieve Product-Market Fit, or Scale Revenue]
Resource Assumptions: [TEAM SIZE & BUDGET, e.g., 4 developers, 1 designer, 1 PM]

Structure the roadmap into three distinct, logical phases:

1. PHASE 1 (Months 1-2) — FOUNDATION & CORE VALUE:
   - Objective: What is the primary customer pain we are resolving to achieve core retention?
   - Focus Features: Feature list with clear strategic and customer rationale.
   - Success Metrics: Specific KPIs with baselines and target numbers.
   - Core Dependencies: Key API integrations, infrastructure setups, or database designs.

2. PHASE 2 (Months 3-4) — GROWTH & ENGAGEMENT:
   - Objective: How do we activate users faster and spark organic distribution loops?
   - Focus Features: Engagement and sharing features.
   - Success Metrics: Acquisition, referral, and time-to-value KPIs.
   - Core Dependencies: Marketing setup, notifications, or performance optimization.

3. PHASE 3 (Months 5-6) — RETENTION & MONETIZATION:
   - Objective: How do we prevent churn and unlock revenue opportunities?
   - Focus Features: Advanced tiers, paywalls, admin controls, or integrations.
   - Success Metrics: MRR/ARR, churn rates, and upgrade conversion rates.
   - Core Dependencies: Billing system integrations, compliance reviews, or enterprise security.

4. RISK & RESILIENCY PLANNING:
   - For each phase, identify the #1 risk (e.g., technical debt, adoption failure, timeline slip).
   - Mitigation: Specific actions to de-risk.
   - The Cut List: Which features in each phase will be cut first if the timeline slips?

5. THE NORTH STAR:
   - Define the single, high-leverage metric that aligns the entire team over the 6-month period.
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: The Competitor Interruption Pivot
```markdown
Assume we are at Month 2 of the roadmap. A major competitor launches an AI-powered version of our core feature, threatening our beachhead segment.
1. Outline how we should adjust our roadmap: What gets shifted, what gets cancelled, and what remains unchanged?
2. Write a memo to the engineering team explaining the pivot, the strategic rationale, and how we will maintain morale.
```

### Follow-Up 2: Roadmap Alignment Review
```markdown
Read the generated roadmap. 
1. Evaluate it from the perspective of an Engineering Lead: What infrastructure bottlenecks or architectural decisions must be made in Phase 1 to support the features planned in Phase 3?
2. Detail how we should structure our technical debt allocation during the 6-month period.
```

---

## 50-Year PM Wisdom
* **Commit to Problems, Not Solutions**: When you present a roadmap, never present it as "We will build Feature X on October 12th." Instead, present it as "In Q4, we are focusing on solving user friction in the checkout process, and our target is to reduce checkout drop-off by 15%." This gives your team the freedom to pivot the solution when they discover technical constraints.
* **The "Cut List" is Mandatory**: Every roadmap must have a pre-approved cut list. If you don't decide what to drop before you are late, you will make rushed, low-quality cuts when you are under pressure.
