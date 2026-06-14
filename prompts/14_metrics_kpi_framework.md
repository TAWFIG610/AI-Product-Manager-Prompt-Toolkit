# 14. Metrics & KPI Framework

## Strategic Context
If you measure everything, you measure nothing. A 50-year PM veteran knows that a great metrics framework starts with a single **North Star Metric** that represents the actual *value* delivered to the customer, not the business. For example, Facebook's early North Star wasn't "Page Views" (vanity metric); it was "Users adding 10 friends in 14 days" (retention driver). The metrics framework must map how your daily input actions drive this North Star.

---

## The Master Prompt

```markdown
Act as a Chief Data Officer (CDO) and VP of Product Analytics with 20+ years of experience building data cultures at market-leading tech companies. Build a comprehensive metrics and telemetry framework for the following product:

Product Name & Description: [PRODUCT NAME & DESCRIPTION]
Current Stage: [PRE-LAUNCH / MVP / GROWTH / SCALE]
Business Model: [SUBSCRIPTION / MARKETPLACE / TRANSACTIONAL / AD-SUPPORTED]

Deliver a data strategy report containing:

1. THE NORTH STAR METRIC (NSM):
   - What is the single metric that best captures the value the product delivers to the customer?
   - Rationale: Why was this chosen over other candidates? How does it correlate with retention?
   - How does this metric align the product, engineering, and marketing teams?

2. THE INPUT METRIC TREE:
   - Identify 3-5 leading indicators (input metrics) that directly drive the North Star Metric.
   - Categorize these input metrics by stage:
     - Acquisition/Sign-up.
     - Activation (The moment they first experience the NSM).
     - Engagement (Frequency and depth of usage).
     - Retention (Return rate).
   - Draw a text-based hierarchy showing how these input metrics roll up to the NSM.

3. HEALTH & GUARDRAIL METRICS:
   - What system, operational, or business metrics must we monitor to ensure our growth isn't breaking the product? (e.g., page load latency, support ticket volume, user deletion rate).

4. VANITY METRICS TO AVOID:
   - Identify 3 metrics that the executive team might want to track but are vanity metrics that do not predict retention or business health. Explain why they are dangerous.

5. INSTRUMENTATION CHECKLIST:
   - Provide a table of the top 5 critical user events we must track. For each event, list: Event Name, User Action that triggers it, and the Contextual Properties to log (e.g., user_type, device_os, time_taken).

6. PM WEEKLY DASHBOARD LAYOUT:
   - Outline the visual layout of a dashboard for the PM. What 6 charts/widgets must be on the screen every Monday morning?
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: Retention Cohort Analysis Plan
```markdown
Assume we have launched and are tracking user cohorts by signup month:
1. Explain how to design a Cohort Retention Table (using monthly cohorts) to track if our retention curve is flattening.
2. What does a "declining cohort curve" vs. a "flattening cohort curve" tell us about Product-Market Fit, and how should a PM respond to each scenario?
```

### Follow-Up 2: Amplitude/Segment Tracking Plan Schema
```markdown
Based on the Instrumentation Checklist:
- Generate a JSON schema of the tracking plan for an analytics platform (like Segment or Amplitude).
- Include types, descriptions, and required/optional properties for the top 3 events.
```

---

## 50-Year PM Wisdom
* **Measure Value Delivered, Not Value Captured**: A common mistake is using "Monthly Recurring Revenue" (MRR) or "Signups" as a North Star Metric. These are business values (captured value). Your North Star should be a customer value (delivered value), like "Successful rides completed" (Uber) or "Files shared with at least 2 people" (Dropbox). If you deliver customer value, business value will follow.
* **If it Doesn't Inform a Decision, Don't Track It**: Data storage is cheap, but cognitive load is expensive. If you add 100 events to your dashboard, you will get lost in the noise. Only track metrics that, if they change, will force you to make a product or business decision.
