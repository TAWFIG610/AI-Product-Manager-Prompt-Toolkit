# 16. Pricing Strategy Designer

## Strategic Context
Pricing is the single most powerful lever for SaaS profitability, yet it is rarely optimized. A 50-year PM veteran knows that pricing is a product feature. It dictates who your customers are, how they use the product, and how they perceive your value. The key is finding the right **Value Metric**—the axis on which your price scales (e.g., per user, per gigabyte, per transaction) so that your revenue grows naturally as your customers get more value.

---

## The Master Prompt

```markdown
Act as a Principal Pricing Strategist, Monetization Economist, and Product Leader with 20+ years of experience designing SaaS revenue models. Design a comprehensive pricing and packaging strategy for the following product:

Product Name & Description: [PRODUCT NAME & DESCRIPTION]
Target Customer Segment: [SMB / MID-MARKET / ENTERPRISE / CONSUMER]
Current Revenue Stage: [PRE-REVENUE / EARLY SAAS / SCALING]
Key Competitors & Pricing: [LIST COMPETITORS & THEIR ESTIMATED PRICING]
Core Value Metric (if known): [e.g., seats, gigabytes, transactions]

Deliver a monetization blueprint structured as follows:

1. RECOMMENDED MONETIZATION MODEL:
   - Identify the model (e.g., Per-Seat, Usage-Based, Flat-Rate, Freemium, Free Trial, or Hybrid).
   - Rationale: Why does this model align customer value with our cost structure (margin protection)?

2. VALUE METRIC SELECTION:
   - What is the primary metric we will use to scale pricing? (e.g., API calls, active projects, seats).
   - Explain why this metric scales with customer success (i.e., as their business grows, they pay us more, happily).

3. TIER STRUCTURE & PACKAGING (The 3-Tier Model):
   - Tier 1: Entry level (Name, Price Point, Target Customer, Included Features, Limits).
   - Tier 2: Mid-tier (The Anchor) (Name, Price Point, Target Customer, Included Features, Limits).
   - Tier 3: High-end/Enterprise (Name, Price Point/Custom, Target Customer, Included Features, Limits).
   - Detail the feature gates: Why are certain features restricted to higher tiers?

4. FREE TRIAL VS. FREEMIUM RECOMMENDATION:
   - Make a clear recommendation with mathematical and behavioral justification.
   - Detail the limit thresholds (e.g., "Free up to 3 projects" or "14-day free trial with credit card required").

5. PSYCHOLOGICAL ANCHORING & COPYWRITING:
   - Describe the layout strategy for the pricing page to make the mid-tier option feel like the obvious choice.
   - Write the pricing page copy: Headline, Subheadline, and 2-sentence value statements for each tier.

6. 90-DAY PRICING EXPERIMENT PLAYBOOK:
   - How do we test this pricing with a small cohort of new users before rolling it out to 100% of traffic?
   - How do we grandfather existing customers to prevent backlash?
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: The Enterprise Upgrade Package
```markdown
For the Enterprise Tier (Tier 3) proposed:
1. Design the "Enterprise Gate" features (e.g., SAML SSO, Audit Logs, custom SLAs, dedicated database).
2. Write a negotiation sheet for our sales reps: What discounts are they authorized to give, and what commitment levels (e.g., 2-year contract) must they extract in return?
```

### Follow-Up 2: The Seat-to-Usage Migration Strategy
```markdown
Assume we currently charge per seat, but want to migrate to a usage-based pricing model to capture expansion revenue:
1. Outline the migration playbook: How do we calculate the impact on existing customer bills?
2. Write the customer announcement email explaining the transition in terms of fairness ("pay only for what you use").
3. Design a dashboard feature that helps customers monitor their usage to avoid "bill shock."
```

---

## 50-Year PM Wisdom
* **Charge for What Matters**: If you charge per user seat but your product is designed for a single administrator who generates value for the whole company, your revenue will flatline. Charge on the metric that directly corresponds to the value the user receives. If they get value from sending reports, charge per report sent.
* **SSO is an Enterprise Gate, Not a Tax**: While gating SAML/SSO is standard practice in B2B SaaS, be careful not to alienate your developer community. Gating compliance features (like audit logs, data residency, and dedicated support) is a safer way to segment enterprise buyers than restricting basic security controls.
