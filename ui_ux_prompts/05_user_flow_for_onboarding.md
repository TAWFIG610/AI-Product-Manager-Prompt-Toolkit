# 05. User Flow for Onboarding
**Category:** Flow Design · 🔀 Mix (Web + Phone)
**Phase:** Design or Optimization — when onboarding drop-off exceeds 40% at any step
**Where:** Mobile: 4-column grid, 16 pt margins · Web: 12-column grid, 80 px margins

---

## Strategic Context

Onboarding is the most consequential flow in any digital product. It is the moment when a stranger decides whether to become a user. The failure mode that kills most onboarding flows is not technical — it is philosophical. Teams design onboarding to collect everything they want from the user (profile photo, preferences, payment info, permissions) before the user has received any value. This is backwards.

Samuel Hulick (of UserOnboard.com) articulated this perfectly: "People don't buy products. They buy better versions of themselves." Your onboarding flow's only job is to get users to their first moment of real, felt value — the **Aha! moment** — as fast as possible. Everything that delays that moment should be either removed or deferred.

The three principles senior product designers apply to onboarding:
1. **Progressive onboarding**: defer non-essential setup to the moment it becomes contextually relevant (e.g., ask for notification permission when the user takes an action that would benefit from it — not on screen 2 of signup).
2. **Contextual tooltips**: replace tutorial screens with subtle callouts triggered by real user actions.
3. **The 3-screen rule**: the Aha! moment should be reachable within 3 screens from signup.

---

## Relevant Dimensions

**Mobile onboarding canvas:**
- Canvas: **390 × 844 pt/dp** (medium phone — test at 320 and 430)
- Content safe area: y = **60–810 pt** (accounting for status bar + home indicator)
- Side margins: **16 pt** each side
- Primary CTA button: **50–56 pt** height, full-width (358 pt)
- Progress indicator dots: **8 pt** diameter, **8 pt** gap between dots

**Web onboarding canvas:**
- Onboarding modal / card width: **480–640 px** centered
- Content area: **400–560 px** (modal width minus padding)
- Vertical padding inside modal: **32–48 px** top and bottom
- Primary CTA: **52–56 px** height, full-width within modal

**Typography for onboarding:**
- Mobile screen title: **Title (22 pt)** or **Title Large (28 pt)**, weight 700
- Mobile body description: **Body (17 pt)**, weight 400, line-height 1.5
- CTA button label: **Headline (17 pt)**, weight 600
- Step count / progress text: **Caption (13 pt)**, weight 400

---

## The Master Prompt

```markdown
You are a Senior Product Designer and Onboarding Specialist with expertise in activation optimization and user habit formation. You have diagnosed and improved onboarding flows for B2B SaaS, consumer apps, and marketplace products.

App type: [DESCRIBE YOUR APP — e.g., "task management tool for remote teams"]
Target user persona: [DESCRIBE THE USER — e.g., "team leads at companies of 10–50 people"]
Platform: [Mobile / Web / Both]
Current onboarding steps: [LIST EVERY CURRENT STEP IN ORDER]
Current drop-off rate: [% of users who abandon before completing onboarding, if known]
Aha moment (current): [DESCRIBE WHEN USERS FIRST FEEL VALUE, if known]

Apply progressive onboarding principles to redesign this flow:

STEP 1 — AHA MOMENT AUDIT:
- What is the earliest moment a user could feel the product's core value?
- How many steps currently separate signup from that moment?
- What are the 3 biggest delays between signup and the Aha moment?

STEP 2 — STEP CLASSIFICATION:
Classify every current step as:
  - ESSENTIAL (must happen before core value can be delivered)
  - DEFERRABLE (can happen after first value is experienced, triggered contextually)
  - REMOVABLE (asks for information the product can infer or doesn't need)

STEP 3 — REDESIGNED FLOW:
- Produce the optimized flow: only ESSENTIAL steps before the Aha moment
- For each DEFERRABLE step: specify exactly when and how it should be triggered contextually
- For each screen: write the headline, body text (max 20 words), and CTA label (max 3 words)
- Drop-off risk rating per step: Low / Medium / High

STEP 4 — CONTEXTUAL TOOLTIP PLAN:
- List 3 features that should use contextual tooltips instead of tutorial screens
- For each tooltip: trigger condition (user action that fires it), copy (max 15 words), and dismiss method

STEP 5 — PERMISSION REQUEST STRATEGY:
- List every permission the app needs (notifications, camera, location, contacts, etc.)
- For each permission: recommend the exact contextual moment to request it (not upfront)
- Write the rationale copy to show users before the system permission dialog appears

Output: Redesigned flow with step-by-step screen specs + tooltip plan + permission strategy.
```

---

## Follow-Up Prompts

### Follow-Up 1: Drop-Off Recovery Email Sequence
```markdown
For the redesigned onboarding flow above, write a re-engagement email sequence targeting users who dropped off at each major step.
For each drop-off point:
(1) Subject line (max 8 words, no clickbait)
(2) Email body: 3 sentences maximum — what they are missing, what to do, one-line CTA
(3) CTA link destination (which screen should the deep link land on?)
(4) Timing: how many hours/days after drop-off to send
Write in [BRAND VOICE — e.g., "friendly and direct, never pushy"].
```

### Follow-Up 2: Onboarding A/B Test Design
```markdown
Identify the single highest drop-off step in the redesigned onboarding flow.
Design an A/B test to optimize this step:
(1) Hypothesis: "We believe [change] will increase completion of [step] because [reasoning]"
(2) Control (A): describe the current step experience
(3) Variant (B): describe the proposed change
(4) Primary metric: exact event name and calculation
(5) Guardrail metric: what must not degrade (e.g., downstream 7-day retention)
(6) Minimum sample size: estimate using 80% power, 5% significance, 5% MDE
(7) Duration: how many days to run, accounting for weekly seasonality
```

---

## Designer Wisdom

- **Ask for nothing before you give something.** If your first screen asks for a profile photo or detailed preferences, you are asking for trust you haven't earned. The rule: your first screen should deliver value, not collect information.
- **Measure completion per step, not just total completion.** A 60% overall onboarding completion rate can hide a single step killing 50% of users. Instrument every step individually. The step with the biggest drop is always obvious once you look.

**Tools that pair with this prompt:**
- **Mixpanel / Amplitude** — funnel analysis to measure step-by-step drop-off
- **Appcues / Userflow** — no-code contextual tooltip and onboarding builder
- **Figma** — prototype and test onboarding flow before building
- **UserOnboard.com** — teardowns of top product onboarding flows for inspiration
