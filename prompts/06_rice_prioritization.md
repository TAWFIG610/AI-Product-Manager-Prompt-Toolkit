# 06. RICE Prioritization

## Strategic Context
The RICE (Reach, Impact, Confidence, Effort) model is a powerful framework, but it is often abused. Teams will inflate Reach or Impact numbers to push their favorite features through. A 50-year PM veteran knows that **Confidence** is the most important factor in the equation—it acts as the filter that punishes speculative ideas and rewards data-backed insights. 

---

## The Master Prompt

```markdown
Act as a Senior Director of Product with 25+ years of experience facilitating portfolio prioritization for high-growth tech companies. Evaluate and prioritize the following feature ideas using a highly disciplined RICE framework:

Features for Prioritization:
[LIST FEATURES WITH BRIEF DESCRIPTION OF EACH]

For each feature, calculate and justify each parameter based on these strict definitions:

1. REACH (Monthly Active Users Affected):
   - Estimate the number of unique users who will use this feature in a 30-day period.
   - Justify this estimate using user segments, adoption assumptions, or historical features.

2. IMPACT (User Value Multiplier):
   - Assign one of the standard scoring values:
     - 3.0 = Massive Impact (game-changer, solves top pain point, major retention driver)
     - 2.0 = High Impact (improves core workflow significantly)
     - 1.0 = Medium Impact (nice-to-have, improves daily usability)
     - 0.5 = Low Impact (minor quality-of-life update)
     - 0.25 = Minimal Impact (imperceptible to most users)
   - Provide a 2-sentence rationale for this score.

3. CONFIDENCE (The Truth Filter):
   - Score strictly based on data evidence:
     - 100% = High Confidence: Backed by direct user analytics, multiple interviews, AND competitor proof.
     - 80% = Medium Confidence: Backed by customer feedback requests and qualitative user surveys.
     - 50% = Low Confidence: Expert guess, limited qualitative signal, high technical risk.
     - 20% = Speculative: Pure gut feeling, no data or customer verification.
   - Justify the confidence percentage.

4. EFFORT (Person-Weeks or Sprints):
   - Estimate the engineering effort (including frontend, backend, QA, and design) in person-weeks or sprints.
   - Note any specialized engineering skills required (e.g., DevOps, Security, Machine Learning).

5. RICE SCORE CALCULATION:
   - Apply the formula: RICE Score = (Reach × Impact × Confidence) / Effort
   - Present the output as a Markdown table sorted in descending order of RICE Score.

6. STEERING RECOMMENDATION:
   - Recommend the top 3 features to pull into the next planning cycle.
   - Identify which feature should be deprioritized immediately and explain why.
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: The Bottleneck Adjuster
```markdown
Assume we have severe resource constraints: our backend team has full capacity, but our frontend/mobile team has a bottleneck (only 1 developer available for the next 2 sprints). 
1. Re-evaluate the Effort scores for the features listed above, factoring in this specific bottleneck.
2. Produce an adjusted RICE table and explain how the team alignment must change as a result.
```

### Follow-Up 2: Cost of Delay (CD3) Analysis
```markdown
For the top 3 features in the RICE table:
1. Estimate the "Cost of Delay" (estimated revenue lost, customer churn, or competitive ground lost) for every month we delay shipping them.
2. Calculate the CD3 Score (Cost of Delay divided by Duration/Effort).
3. Compare the CD3 ranking with the RICE ranking and explain any differences.
```

---

## 50-Year PM Wisdom
* **Kill the Gut-Feeling Inflation**: When a stakeholder claims a feature is "critical" but has no data, drop their confidence score to 20%. Watch how fast their pet project drops to the bottom of the list. RICE forces people to speak in data or admit they are guessing.
* **The Effort is Always Underestimated**: Developers are optimists by nature. When they estimate effort, double it to account for testing, documentation, rollout prep, and bug fixes.
