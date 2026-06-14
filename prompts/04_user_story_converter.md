# 04. User Story Converter

## Strategic Context
Many agile user stories are poorly written, representing horizontal slices (e.g., "Create database schema" or "Design UI screen") rather than vertical, value-delivering slices of functionality. A 50-year PM veteran knows that stories must be written so that they can be developed, tested, and potentially shipped independently. Using the Gherkin syntax (Given-When-Then) for acceptance criteria ensures zero ambiguity between PMs, developers, and QA.

---

## The Master Prompt

```markdown
Act as a veteran Agile Scrum Master and Technical Product Manager. Convert the following feature description into a structured backlog of production-ready Agile user stories.

Feature Description: [FEATURE DESCRIPTION OR SPECIFICATION]
Technical Context/Stack (if known): [TECH CONTEXT]

Deliver your response in the following format:

1. EPIC LEVEL MAP:
   - Group the user stories under logical Epics.
   - Outline the dependency map between these Epics (e.g., Epic B depends on Epic A).

2. USER STORIES (Prioritized by User Value):
   For each user story, provide:
   - Story ID (e.g., US-101) & Descriptive Title.
   - Story Statement: "As a [user persona], I want [action/capability] so that [underlying value/benefit]."
   - Technical & Business Context: A brief explanation of the "why" and any implementation notes.
   - Acceptance Criteria (Gherkin Syntax): Provide at least 3-5 scenarios structured as:
     - Given [precondition or system state]
     - When [action taken by user or system trigger]
     - Then [expected outcome, UI update, or database change]
   - Dependencies: Mention other stories, APIs, or design assets required.
   - Story Splitting Advice: If this story is too large (more than 5-8 story points), how can it be split into smaller, independent vertical slices?

3. DEFINITION OF DONE (DoD):
   - Provide a checklist of what constitutes "Done" for these stories (e.g., code review, test coverage, accessibility, instrumentation).

Make the acceptance criteria strict, testable, and free of vague terminology.
```

---

## Follow-Up / Deep-Dive Prompts

### Follow-Up 1: Technical Spike Creation
```markdown
Identify the most complex or high-risk user story from the list above. Write a Technical Spike ticket for engineering:
1. Goal: What technical unknown are we trying to resolve? (e.g., performance bottlenecks, API compatibility).
2. Timebox: Recommended timeframe (e.g., 2 days).
3. Deliverables: What code sample, documentation, or architecture diagram must the developer produce to mark the spike complete?
```

### Follow-Up 2: Sprint Planning Capacity Check
```markdown
Assume we have a sprint capacity of 30 story points and a team of 4 developers.
1. Suggest a sprint payload using the user stories generated above.
2. Outline how to handle testing resource bottlenecks during the last 3 days of the sprint for these specific stories.
```

---

## 50-Year PM Wisdom
* **Slice Vertically**: A user story should represent a vertical slice of the stack. A database change alone does not deliver value. A UI button alone does not deliver value. A user story should deliver a working slice, no matter how small, that can be clicked, tested, and shipped.
* **Avoid the "And" in Stories**: If a user story has "and" in the title or description (e.g., "As a user I want to log in AND edit my profile..."), it is almost always two separate stories. Split it to keep velocity predictable.
