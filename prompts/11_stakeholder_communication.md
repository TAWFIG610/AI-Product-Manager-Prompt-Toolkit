# 11. Stakeholder Communication

## Strategic Context
Stakeholders are busy, easily distracted, and have different priorities. Executives care about revenue and timelines; developers care about architectural complexity; sales cares about customer commitments. A 50-year PM veteran knows that sending a single, generic update to everyone is a waste of time. You must tailor the message to the audience, lead with the TL;DR, and always bring a clear recommendation when asking for a decision.

---

## The Master Prompt

```markdown
Act as a Principal Product Leader who excels at high-stakes stakeholder management. Help me write a concise, professional stakeholder update.

Product/Feature: [PRODUCT OR FEATURE NAME]
Audience: [TARGET AUDIENCE, e.g., CEO/Board vs. Engineering vs. Sales/Support]
Current RAG Status: [RED / AMBER / GREEN] with brief reasoning
Key Update/Incident: [WHAT HAPPENED AND WHY]
Decision Needed: [SPECIFIC DECISION OR RESOURCES NEEDED]

Structure the update as follows:

1. THE TL;DR (Executive Summary):
   - A single, high-impact sentence summarizing the current status, progress, and immediate action required from the reader.

2. STATUS SNAPSHOT:
   - RAG Status (Red, Amber, Green) with a 1-sentence explanation of what the status means for the launch timeline.

3. KEY PROGRESS (Max 3 Bullet Points):
   - Major milestones achieved since the last update. Focus on outcomes and metrics, not activities (e.g., "API integrated and latency reduced by 20%" rather than "Worked on API integration").

4. CRITICAL RISKS, BLOCKERS & MITIGATIONS:
   - List the top blockers. For each blocker, provide:
     - The issue and its impact on scope/timeline.
     - Owner: Who is responsible for resolving it?
     - Mitigation: What are we doing to unblock it?
     - Resolution ETA: Specific target date.

5. THE ASK / DECISION (If applicable):
   - Frame the decision clearly. Present the choices (Option A, B, or C) with the trade-offs of each (Time vs. Cost vs. Quality).
   - Provide a clear recommendation on which option we should take and why.

6. AUDIENCE-SPECIFIC TRANSLATION:
   - Provide three brief variations of this update tailored for:
     1. Executive Team: Focus on business outcomes, revenue, and timeline impact.
     2. Engineering Team: Focus on technical blockers, architecture, and task priorities.
     3. Sales/Customer Support: Focus on customer impact, feature availability, and customer messaging.
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: Delivering Bad News (The Delay Memo)
```markdown
Assume the project status has slipped to RED due to unforeseen technical debt, pushing the launch date back by 4 weeks. Write a high-empathy, professional delay memo to the executive team:
1. Explain what happened without making excuses or blaming individuals.
2. Outline the immediate recovery plan (how we will use the 4 weeks to ensure a flawless launch).
3. Detail the impact (or lack thereof) on the quarterly business targets.
```

### Follow-Up 2: The Critical Q&A Trainer
```markdown
Identify the top 3 most difficult, critical questions or objections the CEO/Board will ask after reading the update generated above. 
- For each question, draft a clear, confident, and data-backed response that de-escalates concerns and shows control.
```

---

## 50-Year PM Wisdom
* **No Surprises, Ever**: The worst thing a PM can do is surprise a stakeholder. If a project is slipping, flag it as Amber early. It is much easier to explain why a project might be late two months in advance than to explain why it is late on the day of the planned launch.
* **Format for Scanners**: Stakeholders scan updates on their phones during meetings. Use bold text, bullet points, short paragraphs, and clear headers. If they have to scroll more than two screens, they won't read it.
