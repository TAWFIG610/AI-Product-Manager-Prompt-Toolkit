# 06. Competitive UX Teardown
**Category:** Competitive Analysis · 🖥️ Web · 🔀 Mix
**Phase:** Discovery — before kickoff, redesign, or pitch
**Where:** Evaluate competitors at standard desktop (1120 px content area) and mobile (390 × 844)

---

## Strategic Context

Most competitive analysis asks the wrong question: "What features do they have?" A UX teardown asks the right question: "How do they guide users toward behavior?" Features are visible and easy to copy. The behavioral architecture underneath — the sequence of decisions, the placement of friction, the moments of delight — is invisible to casual observation and extremely difficult to copy.

Senior designers approach competitive teardowns like a film critic analyzes a movie: they look past the surface (what it looks like) to the craft decisions (why it was built that way). Why did they put the upgrade prompt at that moment in the flow? Why did they use a modal here instead of an inline form? Every UX decision encodes a hypothesis about user behavior. Your job is to decode those hypotheses and evaluate whether they would work for your users.

The output you want is not a feature checklist — it is a **pattern map** that reveals where competitors are strong (so you can match or surpass them), where they are weak (your attack vectors), and what patterns are table stakes in this category (baseline quality your users expect from day one).

---

## Relevant Dimensions

**Desktop evaluation viewport:**
- Content area: **1120 px max-width**, 12-column grid
- Desktop margins: **80 px** each side
- Navigation evaluation: count clicks from homepage to core feature

**Mobile evaluation viewport:**
- Canvas: **390 × 844 pt/dp**
- Side margins: **16 pt**
- Bottom nav height: **49–80 pt**

**Timing benchmarks for competitor onboarding:**
- Time to first action (from landing page): target under **90 seconds**
- Time to Aha moment (from signup): target under **5 minutes**
- Screen count to Aha moment: target **3 screens or fewer**

**Touch/click target audit (for mobile competitors):**
- Minimum CTA button: **44 × 44 pt (iOS) / 48 × 48 dp (Android)**
- Minimum gap between targets: **8 pt/dp**

---

## The Master Prompt

```markdown
You are a Senior Product Designer and UX Strategist with 15+ years of experience conducting competitive analysis for venture-backed startups. You think like a product detective — looking past visual surface to underlying behavioral architecture.

Competitors to analyse: [NAME 3–5 COMPETITORS]
My product: [DESCRIBE YOUR PRODUCT IN 2 SENTENCES]
My target user: [DESCRIBE YOUR TARGET USER]

Conduct a rigorous UX teardown of each competitor across these 5 pillars:

PILLAR 1 — NAVIGATION & INFORMATION ARCHITECTURE:
- What is the top-level navigation structure? (list main nav items)
- What organizational principle is used: by feature / by user role / by task / by outcome?
- Click depth to the 3 most important features (count from homepage)
- Mobile: what sits in the bottom tab bar vs. the overflow menu?

PILLAR 2 — PRIMARY CTA STRATEGY & CONVERSION FUNNEL:
- What is the single primary CTA on the homepage / landing page?
- Where is it positioned? (header / hero / sticky bar / bottom)
- What is the signup/trial friction level? (email only / email+password / Google OAuth / credit card required)
- What is the estimated time from landing page to first value delivered?

PILLAR 3 — ONBOARDING FLOW ANALYSIS:
- How many steps from account creation to the Aha moment?
- What is deferred (asked after first value) vs. demanded upfront?
- Where does friction appear? (required fields, permission requests, forced tutorials)
- What is the Aha moment and when does it occur?

PILLAR 4 — RETENTION MECHANICS:
- What brings users back daily / weekly? (notifications, digests, streak mechanics, network effects)
- What investment does the product build up over time that makes switching painful?
- How does the product make the user feel successful or recognized?

PILLAR 5 — UX WEAKNESSES & EXPLOIT OPPORTUNITIES:
- Their biggest UX weakness (based on G2/App Store/Reddit signal if available)
- Where users most likely drop off based on UX analysis
- The specific pattern gap [MY PRODUCT] can exploit

SYNTHESIS:
- Comparison matrix: rate each competitor across all 5 pillars (1–5 scale)
- Pattern gaps: list UX patterns that no competitor does well — opportunity spaces
- Table stakes: list UX patterns every strong competitor does — baseline quality we must match
- Strategic opportunities: top 3 specific UX decisions [MY PRODUCT] should make differently

Format: pillar-by-pillar analysis per competitor + synthesis matrix + strategic opportunity list.
```

---

## Follow-Up Prompts

### Follow-Up 1: Anti-Pattern Library
```markdown
Based on the competitive teardown above, create an Anti-Pattern Library for [MY PRODUCT].
An anti-pattern is a UX decision used by competitors that users complain about or that data shows increases churn.
For each anti-pattern identified:
(1) Name the pattern (e.g., "Forced profile completion gate")
(2) Which competitor uses it
(3) Why it is harmful (user impact + business impact)
(4) The pattern [MY PRODUCT] should use instead
Output: A do/don't table with rationale per row. Maximum 10 anti-patterns.
```

### Follow-Up 2: First-90-Days Feature Catch-Up Plan
```markdown
Based on the "table stakes" section of the competitive teardown — the baseline UX patterns every strong competitor has — create a first-90-day feature catch-up plan.
For each table-stakes pattern [MY PRODUCT] currently lacks:
(1) Feature name and brief description
(2) Why it is table stakes (what user expectation it serves)
(3) Implementation complexity: Low / Medium / High
(4) Priority: must-have before launch / should-have within 30 days / can-defer to 90 days
Output: a table sorted by priority + implementation complexity for engineering planning.
```

---

## Designer Wisdom

- **Look at the reviews, not the marketing.** Competitors spend millions making their product look good on the surface. G2 reviews, App Store 1-star reviews, and Reddit threads show you what users actually experience. These are your most valuable research sources — and they are completely free.
- **Reverse-engineer their hypotheses.** For every UX decision you observe, ask: "What did they believe about their users when they built this?" That question reveals the strategic thinking behind the design — and often reveals where that thinking was wrong.

**Tools that pair with this prompt:**
- **Mobbin** — library of iOS and Android UX patterns from top apps
- **Screenlane** — curated UI screens for inspiration and competitive reference
- **G2 / Trustpilot / App Store** — real user complaints about competitor products
- **Wayback Machine** — historical screenshots to see how competitors' UX has evolved
