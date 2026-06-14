# 03. PRD Writer (Product Requirements Document)

## Strategic Context
A poorly written PRD leads to scope creep, engineering delays, and misaligned expectations. A 50-year PM veteran knows that the secret to a great PRD is defining **Non-Goals** and **Edge Cases** with absolute clarity. It should act as a single source of truth that allows design, engineering, and QA to work autonomously without constant clarification meetings.

---

## The Master Prompt

```markdown
Act as a Principal Product Manager with 20+ years of experience launching scale systems at top-tier tech companies. Write a comprehensive, development-ready Product Requirements Document (PRD) for the following feature/product:

Feature/Product Name: [FEATURE NAME]
Core Value Proposition: [ONE-SENTENCE VALUE PROP]
Target User Persona: [PERSONA NAME OR TARGET AUDIENCE]

Structure the PRD exactly as follows:

1. EXECUTIVE SUMMARY & PROBLEM STATEMENT:
   - What is the acute customer problem?
   - What is the business opportunity or competitive risk if we don't build this?
   - How does this align with our overall product strategy?

2. PRODUCT GOALS & NON-GOALS:
   - Goals: What MUST this feature achieve? (Limit to 3 core goals).
   - Non-Goals: What is explicitly out of scope for this version? (Crucial for preventing scope creep).

3. SUCCESS METRICS & TELEMETRY:
   - Primary KPI (North Star for this feature).
   - Secondary KPIs (Input metrics like activation, adoption, speed).
   - Guardrail Metrics (Metrics that must NOT degrade, e.g., page load time, churn, customer support tickets).

4. USER STORIES & FUNCTIONAL REQUIREMENTS:
   - Provide a table with: Story ID, User Story ("As a... I want... So that..."), Priority (P0/P1/P2), and detailed Acceptance Criteria.
   - Acceptance Criteria must be testable, covering UI behaviors, API payloads, and state changes.

5. SYSTEM CONSTRAINTS & TECHNICAL CONSIDERATIONS:
   - Platform/Device compatibility requirements.
   - Data privacy, compliance (e.g., GDPR, SOC2), and security requirements.
   - Performance SLAs (e.g., maximum latency, offline behavior, sync frequencies).

6. EDGE CASES, ERROR HANDLING & EXTREME STATES:
   - Detail at least 5 edge cases (e.g., concurrent edits, slow network speeds, extreme inputs, empty states, zero-result states).
   - Specify the exact system behavior and copy for error states or failure modes.

7. OPEN QUESTIONS & DEPENDENCIES:
   - Internal dependencies (other teams, shared services).
   - External dependencies (third-party APIs, vendor tools).
   - Unresolved questions that need engineering spikes or user research to close.

Write this document in a precise, structured, and engineering-friendly tone. Avoid vague descriptors like "simple", "fast", or "intuitive"—specify the exact behavior.
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: The Engineering Grilling Session
```markdown
Read the generated PRD. Act as a cynical Tech Lead who wants to build this efficiently but is worried about legacy integration, API rate limits, and technical debt. 
1. List 5 critical questions or potential engineering blockers in this PRD that need clarification.
2. Provide draft answers to each question that resolve the technical ambiguity while protecting the core user experience.
```

### Follow-Up 2: The UX/Design Brief
```markdown
Based on the PRD requirements, write a Design Brief for the UX/UI designer:
1. Outline the recommended user flow steps.
2. Describe the information architecture of the main interface (what elements are prominent, what is secondary).
3. Detail the micro-interactions and animations that will make this feature feel responsive and premium.
```

---

## 50-Year PM Wisdom
* **Own the Non-Goals**: If you don't define what you are *not* building, engineering will build what they find interesting, design will design what looks pretty, and you will miss your launch date. Non-goals are the shield that protects your team's velocity.
* **Write for the QA Engineer**: When writing acceptance criteria, imagine yourself testing the app. If a requirement cannot be written as a binary pass/fail test case, it is too vague.
