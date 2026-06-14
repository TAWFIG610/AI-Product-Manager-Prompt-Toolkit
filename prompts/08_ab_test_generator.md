# 08. A/B Test Generator

## Strategic Context
A/B testing is often run poorly, resulting in statistical noise, p-hacking, and false positives. A 50-year PM veteran knows that an experiment is only as good as its **Guardrail Metrics** and its statistical design. If your variant increases sign-ups by 5% but degrades long-term retention or increases customer support tickets, the experiment is a failure.

---

## The Master Prompt

```markdown
Act as a Lead Growth Product Manager and Experimentation Statistician with 15+ years of experience designing high-scale product experiments. Suggest 5 high-impact A/B tests to optimize the following product metric and flow:

Target Metric to Optimize: [METRIC, e.g., Onboarding Conversion Rate]
Target Flow/Page: [FLOW/PAGE DESCRIPTION]
Current Monthly Active Traffic: [TRAFFIC VOLUME, e.g., 100,000 monthly unique visitors]

For each proposed test, provide:

1. SCIENTIFIC HYPOTHESIS:
   - "We believe that [specific change to variant] for [target audience] will cause [expected outcome] because [psychological or functional reasoning]."

2. VARIANT SPECIFICATION (Control A vs. Variant B):
   - Control (A): Detailed description of the current experience (copy, layout, behavior).
   - Variant (B): Detailed description of the proposed experience (what changes visually, copy-wise, and functionally).

3. METRICS FRAMEWORK:
   - Primary Metric: The exact event and formula we are measuring to determine success.
   - Secondary Metrics: Supporting metrics showing *how* the behavior changes.
   - Guardrail Metrics: Safety metrics that must NOT degrade (e.g., checkout page speed, churn rate, user complaints).

4. EXPERIMENT DESIGN & CALCULATIONS:
   - Estimated Sample Size: Estimate the number of users required per variant using a standard Minimum Detectable Effect (MDE) of [MDE, e.g., 5%] at 80% statistical power and 5% significance level.
   - Duration: How many days/weeks must the test run to reach sample size (incorporating weekly cycles and seasonality)?

5. BIAS & VALIDATION CHECKS:
   - How will we detect and prevent Sample Ratio Mismatch (SRM)?
   - What risks could skew the results (e.g., novelty effect, cookie deletion, marketing campaigns running concurrently)?

Rank the 5 tests in a table by: Expected Impact (1-5) × Ease of Implementation (1-5) to identify the "low-hanging fruit" experiment.
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: SRM (Sample Ratio Mismatch) Debugger
```markdown
Assume we ran Test #1 for 5 days. The traffic split was configured for 50/50, but the actual sample count is 10,250 in Control and 9,750 in the Variant. 
1. Perform an SRM chi-square test calculation or explain the steps to verify if this discrepancy is statistically significant.
2. Outline the 3 most likely technical reasons for this split mismatch (e.g., tracking script issues, bot traffic, latency in assignment) and how to debug them.
```

### Follow-Up 2: The "Winner's Curse" & Rollout Strategy
```markdown
Assume Test #2 was a statistically significant winner (e.g., 4% lift in checkouts). 
1. Explain the "Winner's Curse" and why the actual lift might drop after a full rollout.
2. Design a phased rollout strategy (e.g., 10% -> 25% -> 50% -> 100%) and telemetry logging plan to monitor the real-world impact post-launch.
```

---

## 50-Year PM Wisdom
* **A/B Testing is for Tuning, Not Finding**: You cannot optimize a bad product concept with A/B testing. If your value proposition is wrong, no button optimization will save you. A/B testing is for tuning a working machine, not building one from scratch.
* **Always Run an A/A Test**: Before running your first A/B test, run an A/A test (splitting traffic 50/50 with identical experiences). If your system shows a statistically significant winner in an A/A test, your tracking or splitting mechanism is broken.
