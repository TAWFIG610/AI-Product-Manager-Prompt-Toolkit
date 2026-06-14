# 07. Customer Feedback Analyzer

## Strategic Context
Analyzing customer feedback is not about counting keywords like "fast" or "bug". Users are not software designers; they often express their pain points by requesting specific features (e.g., "I need an export button"). A 50-year PM veteran knows to look past the *stated request* to identify the *underlying friction*. The objective is to categorize feedback based on the severity of the user's emotional frustration and blockages.

---

## The Master Prompt

```markdown
Act as a Principal User Researcher and Customer Analytics Lead with 20+ years of experience. Analyze the following raw customer feedback, support tickets, or app store reviews and extract structured, actionable intelligence:

Feedback Data:
[PASTE 20-50 CUSTOMER REVIEWS OR FEEDBACK ENTRIES HERE]

Deliver a comprehensive report structured as follows:

1. COGNITIVE CATEGORIZATION MATRIX:
   - Categorize the feedback into 5 clear buckets: Functional Bugs, Usability/UX Friction, Feature Requests, Performance/Speed Issues, and Pricing/Billing.
   - Show the percentage breakdown of the feedback across these buckets.

2. TOP 5 ACUTE CUSTOMER PAIN POINTS:
   - Rank the pain points by a combination of frequency and severity (e.g., Blocked workflow vs. minor annoyance).
   - For each pain point, provide:
     - Root Cause: What is actually causing this pain?
     - Emotional Impact: User sentiment (frustration, confusion, anger).
     - Representative Quote: Direct quote from the feedback.
     - Severity Score: High (causes churn/blocks work), Medium (creates friction), Low (annoyance).

3. TOP 5 FEATURE REQUESTS & JTBD ALIGNMENT:
   - Extract the top requested features.
   - For each feature, decode the "Job-To-Be-Done": What outcome is the user actually trying to achieve by requesting this feature? What is a better way we might solve this without building their exact request?
   - Direct quote supporting the request.

4. SENTIMENT & EMOTIONAL INTENSITY RADAR:
   - A breakdown of sentiment (Positive, Neutral, Negative).
   - Emotional intensity analysis: Where are users showing the highest urgency or distress?

5. ACTIONABLE RECOMMENDATIONS (Immediate vs. Strategic):
   - Quick Wins (Fixes that take < 3 days and resolve major complaints).
   - Roadmap Candidates (Valuable feature requests to plan for).
   - Research Spikes (Areas where user feedback is confusing and needs deeper interviews).
   - Proposed Metrics: What metrics (e.g., CSAT, support ticket volume, time-on-task) will prove we resolved these issues?
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: The Support Recovery & Response Kit
```markdown
Based on the Top 1 Pain Point identified in the feedback analysis:
1. Write an empathetic, clear response template that our support team can use to reply to affected customers.
2. Outline an internal Slack alert message to the engineering team that clearly explains the bug/friction, its business impact (potential churn), and the steps to reproduce it.
```

### Follow-Up 2: The Customer Interview Guide
```markdown
For the pain point or feature request that had the most emotional intensity:
1. Write a 5-question interview guide to use with customers during follow-up discovery calls.
2. Focus on asking open-ended questions that uncover their workflow, rather than asking if they like our proposed solution.
```

---

## 50-Year PM Wisdom
* **Ignore the Solution, Study the Pain**: When customers ask for a feature, they are proposing a solution. They are not product designers. Your job is to ignore their solution temporarily, drill deep into their pain, and figure out if there is a simpler, more elegant way to solve it that fits your system architecture.
* **Filter out the Loud Minority**: Sometimes, 5% of your power users will scream loudly about a advanced feature they want. Do not rewrite your roadmap for them if it makes the product harder to use for the remaining 95% of your customer base.
