# 02. User Persona Generator

## Strategic Context
Most user personas are superficial archetypes (e.g., "Marketing Mary, age 32, likes coffee"). They focus on demographics rather than behaviors, motivations, and the structural friction that prevents users from getting their job done. A seasoned PM knows that the most valuable part of a persona is understanding their **current workarounds**—what spreadsheets, manual hacks, or duct-tape solutions they are using right now. If they aren't trying to solve the problem today, the pain isn't deep enough.

---

## The Master Prompt

```markdown
Act as a veteran UX researcher and behavioral psychologist with 20+ years of experience in user-centered product design. Build 3 distinct, highly detailed, and research-backed user personas for the following product:

Product Description: [PRODUCT DESCRIPTION]
Target Audience: [TARGET AUDIENCE OR KEY SEGMENTS]

For each persona, deliver a deep-dive profile containing:

1. DEMOGRAPHIC & CONTEXTUAL PROFILE:
   - Full Name, Age, Occupation, Company Size/Industry, Income/Salary Bracket.
   - Professional background, career goals, and where they sit in their organization's hierarchy.

2. THE "JOB-TO-BE-DONE" (JTBD):
   - What is the core progress they are trying to make in their work or life?
   - What triggers their search for a solution?

3. CURRENT SYSTEM & DUCT-TAPE WORKAROUNDS:
   - What software, spreadsheets, physical files, or manual hacks do they currently use to solve this problem?
   - What are the costs (time, money, emotional fatigue) of maintaining this workaround?

4. TOP 3 PAIN POINTS & FRUSTRATIONS:
   - Specific, acute pain points (not generic ones) with current solutions.
   - Financial, cognitive, or time-wasting impacts of these frustrations.

5. PSYCHOGRAPHIC & BEHAVIORAL TRIGGERS:
   - Core motivations: What makes them feel successful or recognized?
   - Cognitive Load & Tech Literacy: Are they tech-savvy power users, or do they get overwhelmed by complex interfaces?
   - Preferred channels, devices, and platforms they use daily.

6. DECISION-MAKING & TRUST TRIGGERS:
   - Who influences their buying decision? Who has veto power over their choice?
   - What trust markers do they require before trying or buying new software?

7. REAL-WORLD REPRESENTATION:
   - A direct, raw quote they would say when explaining their problem to a colleague.
   - A typical 1-sentence objection they would raise during a sales call or product tour.

Ensure these personas feel like complex, real human beings with conflicting pressures, not idealized archetypes.
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: The "Day-in-the-Life" Journey Map
```markdown
Choose Persona [NAME] from the personas generated above. Write a chronological "Day-in-the-Life" narrative showing:
1. When the problem first manifests during their day.
2. How they interact with their current workaround.
3. The exact emotional state (stressed, bored, rushed) at the moment they would ideally open our product.
4. How our product can deliver an "Aha!" moment in less than 60 seconds during this flow.
```

### Follow-Up 2: The Anti-Persona
```markdown
Define the "Anti-Persona" for this product—the user profile who looks like a potential buyer on paper, but in reality consumes excessive support resources, churns quickly, and has a low lifetime value. Detail:
1. Why they are a bad fit.
2. How to identify and filter them out during onboarding or sales qualifying.
```

---

## 50-Year PM Wisdom
* **Focus on the Workaround**: If a user has a problem but hasn't spent time or money trying to hack together a workaround (even a messy excel sheet), they will not buy your product. The existence of a workaround is the ultimate validation of market demand.
* **Demographics are Noise, Behavior is Signal**: Age and income are rarely the reasons someone uses a B2B SaaS tool. Focus on their tools, their level of autonomy, their anxiety points, and who blames them when things go wrong.
