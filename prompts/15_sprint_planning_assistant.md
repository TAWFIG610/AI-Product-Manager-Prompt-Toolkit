# 15. Sprint Planning Assistant

## Strategic Context
Sprint planning is often treated as a tetris game of packing as many tickets as possible into a developer's schedule. A 50-year PM veteran knows that a sprint is about **focus and commitment**. If the team commits to too much, they will write low-quality code, skip testing, and suffer burnout. The key is to establish a singular Sprint Goal, balance the workload across frontend/backend, and de-risk the most complex task early in the cycle.

---

## The Master Prompt

```markdown
Act as an Agile Scrum Coach, Scrum Master, and Technical Product Manager with 15+ years of experience facilitating sprint execution for engineering teams. Help me plan and optimize the upcoming sprint:

Sprint Goal Objective: [WHAT BUSINESS OUTCOME ARE WE TARGETING]
Team Capacity: [NUMBER OF DEVELOPERS, QA, DESIGNERS & SPECIALISTS]
Sprint Length: [1 WEEK / 2 WEEKS]
Historical Velocity: [STORY POINTS COMPLETED IN LAST SPRINT]
Candidate Backlog Items:
[PASTE BACKLOG ITEMS, USER STORIES, OR BUG TICKETS HERE]

Analyze the backlog and team capacity to deliver a Sprint Plan covering:

1. REFINEMENT & STORY POINT ESTIMATION:
   - Review each backlog item. Rewrite any vague tickets into clear user stories with basic acceptance criteria.
   - Estimate story points using the Fibonacci sequence (1, 2, 3, 5, 8, 13). Justify each estimate based on complexity, uncertainty, and effort.

2. RESOURCE LOAD BALANCING & COMPOSITION:
   - Review the skills required for the estimated stories. Ensure the work is balanced (e.g., if we have 2 backend devs and 1 frontend dev, ensure we don't have 90% frontend work).
   - Recommend which stories to include in the sprint based on capacity and historical velocity.

3. DEPENDENCY & BLOCKER ANALYSIS:
   - Identify any sequencing dependencies between the selected stories (e.g., US-1 must be completed before US-2 can start).
   - Flag any external blockers (e.g., third-party API keys, design assets) that need to be resolved.

4. DE-RISKING PLAN FOR HIGH-COMPLEXITY ITEMS:
   - Identify the highest-risk/highest-point item in the sprint.
   - Outline a specific, step-by-step mitigation strategy for day 1-3 of the sprint to ensure it doesn't block the launch (e.g., run a mini-spike, mock APIs).

5. THE UNIFIED SPRINT GOAL:
   - Write a single, clear, business-focused sentence that summarizes the goal of this sprint. This is the goal the team will rally around.
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: Mid-Sprint Burndown Pivot
```markdown
Assume we are on Day 6 of a 10-day sprint. The Burndown Chart shows we are falling behind and will likely miss 30% of our committed story points.
1. Design a triage process to decide which stories to keep and which to push to the next sprint.
2. How do we adjust scope on the remaining stories to protect the core Sprint Goal?
3. Draft the Slack message to stakeholders communicating the adjustment without causing panic.
```

### Follow-Up 2: Sprint Retrospective Facilitator Guide
```markdown
Write a facilitation guide for our Sprint Retrospective:
1. Suggest a retro format (e.g., Start/Stop/Continue or Sailboat) suited for a team that struggled with velocity.
2. Write 3 open-ended prompts to get quiet engineers to share honest feedback about why tickets were blocked or estimated poorly.
```

---

## 50-Year PM Wisdom
* **Commit to the Goal, Not the Backlog**: The backlog is a list of tasks; the Sprint Goal is the commitment. If you get to Day 8 and realize you can't finish all 10 tickets, but you can finish the 3 tickets that satisfy the Sprint Goal, you have succeeded. Focus the team on the goal, not the ticketing system.
* **Under-commit and Over-deliver**: Developers are naturally optimistic during planning. They forget about meetings, sick days, code review latency, and deployment pipeline failures. Encourage your team to commit to 80% of their theoretical capacity. If they finish early, they can pull in more work. This builds momentum and pride, whereas missing commitments breeds fatigue.
