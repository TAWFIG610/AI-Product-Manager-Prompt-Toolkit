# 17. Churn Analysis & Retention Fix

## Strategic Context
Churn is the ultimate silent killer of SaaS businesses. You can have the best marketing engine in the world, but if your retention curve decays to zero, your business will eventually go bankrupt. A 50-year PM veteran knows that retention is won or lost in the **first 7 days**. If you don't get the user to their "Aha!" moment quickly, they will forget your product exists. You must classify churn into voluntary and involuntary and build targeted recovery playbooks for both.

---

## The Master Prompt

```markdown
Act as a Principal Retention PM and User Growth Strategist with 20+ years of experience fixing "leaky buckets" at top SaaS companies. Diagnose our churn problem and deliver a comprehensive retention playbook:

Product Name & Core Value: [PRODUCT NAME & CORE VALUE]
Current Churn Rate: [CHURN RATE, e.g., 8% monthly churn]
Target Segment Churning Most: [USER SEGMENT CHURNING MOST]
Raw Customer Exit Feedback: [PASTE OR DESCRIBE SURVEY DATA / FEEDBACK]
Current Retention Initiatives: [WHAT YOU ALREADY DO]

Deliver a retention diagnostic report and playbook structured as follows:

1. METRIC DIAGNOSIS & RETENTION CURVE ANALYTICS:
   - Identify the likely root causes of churn for [USER SEGMENT CHURNING MOST] based on their exit feedback and behavioral profiles.
   - Classify the churn into: Voluntary (user decided to leave), Involuntary (failed credit card payments), Early-Stage (within 7 days of signup), and Late-Stage (after 3+ months).

2. THE "AHA!" MOMENT & TIME-TO-VALUE (TTV) AUDIT:
   - Define the critical behavioral milestone that correlates with long-term retention (e.g., "created a dashboard and invited 1 team member").
   - Suggest 3 in-product UX changes to guide new users to this milestone in under 5 minutes.

3. 5 RETENTION EXPERIMENTS (60-Day Horizon):
   - Suggest 5 experiments to run to improve retention.
   - For each experiment, detail: The Hypothesis, UX Change, Expected Impact (1-5), and Effort.
   - Focus on onboarding, feature engagement, value reminders, and support interventions.

4. LIFECYCLE EMAIL/NOTIFICATION PLAN (First 30 Days):
   - Outline the messaging flow for a new user:
     - Day 1: Welcome & First Step.
     - Day 3: Feature Highlight based on inactive state.
     - Day 7: Value Realization.
     - Day 14: Social Proof / Case Study.
     - Day 30: Monthly ROI Digest (showing what value they received).

5. POWER USER CORRELATION STUDY:
   - Write a database/SQL audit query concept: What data points should we pull for users who have been active for 12+ months to identify their common behaviors?
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: Involuntary Churn Recovery (Dunning Playbook)
```markdown
Assume 30% of our churn is involuntary (credit card payment failures/expired cards):
1. Design a 4-step Dunning Email Sequence that balances empathy, brand voice, and urgency.
2. Outline the system logic: When do we retry the card, when do we send emails, when do we show in-app banners, and when do we lock the account (grace period)?
```

### Follow-Up 2: The Retention-First Cancellation Flow
```markdown
Design a Cancellation Flow that acts as a retention safety net:
1. Outline the steps when a user clicks "Cancel Subscription" (e.g., exit survey, offer a 1-month pause option, down-sell to a cheaper/free tier, talk to support).
2. Write the copy for the cancellation screen that makes them rethink their decision without using dark patterns.
```

---

## 50-Year PM Wisdom
* **Fix the Leak Before Pouring More Water**: If your monthly churn is above 5%, do not spend money on marketing. Every dollar you spend acquiring users is being thrown away. Focus your entire product team on activation and retention until the retention curve flattens.
* **The ROI Digest is King**: Users churn because they forget the value you deliver. If your product runs in the background, send a weekly or monthly "ROI Digest" email that shows them exactly what your product did for them (e.g., "This month, we saved you 14 hours of work and caught 3 critical errors"). Make it impossible for them to justify deleting your subscription.
