# 20. Post-Mortem Facilitator

## Strategic Context
Incidents, outages, and project failures are inevitable in software development. A 50-year PM veteran knows that how you handle failure defines your team's culture. If you blame individuals, they will hide mistakes, slow down, and avoid taking risks. A high-quality post-mortem is **blameless**. It assumes that developers are smart and well-intentioned, and that failures are caused by system defects, poor processes, or lack of safeguards. The objective is to fix the system so the same error cannot happen again.

---

## The Master Prompt

```markdown
Act as a Principal Engineering and Product Leader with 25+ years of experience facilitating blameless retrospectives and post-mortems for mission-critical software systems. Document and extract system-level learnings from the following incident or project failure:

Incident Description: [WHAT HAPPENED, e.g., database outage during promo event]
Business/Customer Impact: [USERS AFFECTED / REVENUE LOST / DOWNTIME]
Chronological Timeline: [TIMESTAMPS & ACTIONS TAKEN]
Immediate Response/Fix: [HOW WE RESTORED SERVICE]
Team Roles Involved: [ROLES, e.g., On-call DevOps, Backend Engineer, PM]

Create a highly detailed, professional, and blameless Post-Mortem Report structured as follows:

1. EXECUTIVE SUMMARY:
   - A 3-sentence, objective summary of the event, the business impact, and the permanent resolution. Avoid mentioning names; focus on system actions.

2. DETAILED CHRONOLOGICAL TIMELINE:
   - Present a chronological log of events with timestamps, detailing: Detection (how we found out), Escalation (who was paged), Diagnosis (how we located the bug), Mitigation (temporary fixes), and Resolution (permanent fix).

3. ROOT CAUSE ANALYSIS (The 5 Whys):
   - Use the "5 Whys" methodology to drill down from the surface symptom to the deep system or process failure.
   - Example: Why did the database crash? -> Why did it run out of memory? -> Why was there a memory leak? -> Why was the query unoptimized? -> Why did our testing pipeline not catch it?

4. CONTRIBUTING FACTORS:
   - What other factors made the incident worse or harder to resolve? (e.g., outdated documentation, alert fatigue, lack of dashboard visibility, slow deployment pipelines).

5. WHAT WENT WELL:
   - Acknowledge the positive actions of the team (e.g., fast response times, clear communication during the incident, automated failovers working).

6. PREVENTATIVE ACTION ITEMS (SMART Framework):
   - Provide a table of at least 5 action items to prevent this class of failure.
   - For each action item, list: Action Description, Target Completion Date, and Owner Role.
   - Focus on adding safeguards, automated testing, alerting improvements, or architectural changes.

7. STAKEHOLDER COMMUNICATION TEMPLATE:
   - Write a high-empathy, transparent, and professional communication template to send to affected customers or external stakeholders explaining what happened, what we did to fix it, and how we are preventing it in the future.
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: The Post-Mortem Action Item Tracker
```markdown
Read the generated Action Items:
1. Translate these action items into Jira ticket descriptions, complete with "Description", "Technical Tasks", and "Definition of Done".
2. Recommend a process to ensure these tickets are prioritized and completed by the engineering team (i.e., how to prevent "Post-Mortem Amnesia" where retro items are forgotten).
```

### Follow-Up 2: The Psychological Safety Reset
```markdown
Assume the team is feeling anxious and blaming each other for the incident:
1. Write a 3-minute introductory script that the meeting facilitator can read at the start of the post-mortem to set a blameless, constructive tone.
2. Outline how to handle a situation where a stakeholder tries to point fingers at a specific engineer during the meeting.
```

---

## 50-Year PM Wisdom
* **Smart People, Broken Systems**: If a developer pushes a bug that deletes database records, it is not the developer's fault. It is the system's fault for allowing a single developer to delete production records without peer review, staging tests, or safety gates. Always fix the process, not the person.
* **The "5 Whys" Must Lead to Action**: The goal of the 5 Whys is to find the systemic gap. If your 5th "Why" is "Because the developer was tired," you have failed. The 5th Why should be "Because we do not have an automated query optimizer check in our CI/CD pipeline." Systemic problems require systemic code/process fixes.
