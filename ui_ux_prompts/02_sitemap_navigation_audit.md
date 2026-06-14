# 02. Sitemap & Navigation Audit
**Category:** Information Architecture · 🖥️ Web · 🔀 Mix
**Phase:** Discovery or Redesign — when bounce/exit rates are high or users report getting lost
**Where:** Web — standard content area, 12-column grid at 1120 px max-width

---

## Strategic Context

Navigation is the skeleton of your product. When it is poorly designed, users feel like they are wandering a building with no signs. The critical mistake most teams make is **designing navigation for how they think about their product** (by feature, by team, by technology) rather than for how users think about their tasks (by goal, by context, by frequency of use).

The two biggest navigation anti-patterns:
1. **Megamenus that expand into 40 links** — users scan for their target word, fail to find it, and leave.
2. **Deeply nested hierarchies** — users cannot hold more than 4 levels of hierarchy in short-term memory. If reaching content requires 4+ clicks, they abandon.

Senior IA designers use **card sorting** (open and closed) to validate navigation groupings before building. They use **tree testing** to validate that users can find content without any visual design in place. This prompt combines both into a structured audit output you can act on immediately.

---

## Relevant Dimensions

**Web canvas:**
- Content area: **1120 px max-width**, centered
- Desktop margin: **80 px** left and right
- Grid: **12 columns**, 32 px gutter
- Header/nav height: **56–80 px** (56 px compact, 80 px spacious)

**Mobile navigation:**
- Side margins: **16 pt/dp**
- Bottom nav bar: **49–80 pt/dp** height
- Tab bar icons: **24 pt/dp** with **44 × 44 pt/dp** touch targets
- Hamburger menu button: minimum **44 × 44 pt/dp** touch target

**Typography for navigation labels:**
- Desktop nav links: **Body (16 px)**, weight 500 or 600
- Mobile tab labels: **Label (11 pt)** below icon, weight 500
- Dropdown items: **Body small (14 px)**

---

## The Master Prompt

```markdown
You are a Principal Information Architect with 15+ years of experience designing navigation systems for large-scale web and mobile products.

Here is my current sitemap and navigation structure:
[PASTE YOUR SITEMAP — can be a text outline, bullet list, or description]

Users report they cannot find: [KEY FEATURE OR CONTENT USERS STRUGGLE TO LOCATE]

Perform a rigorous IA audit in the following order:

STEP 1 — COGNITIVE LOAD ANALYSIS:
- Identify any navigation sections with more than 7 items (Miller's Law violation).
- Flag any labels that are internal jargon, ambiguous, or non-task-oriented.
- Score the overall depth: how many clicks does the most important content require?

STEP 2 — PROGRESSIVE DISCLOSURE AUDIT:
- Is essential content discoverable within 2 clicks from the homepage?
- Are there any content types that are 4+ levels deep?
- Are there orphaned pages (no clear path from nav to that page)?

STEP 3 — REVISED SITEMAP RECOMMENDATION:
- Propose a restructured sitemap using progressive disclosure principles.
- Group items by user task / goal, not by internal company structure.
- Limit top-level items to 5–7.
- Provide the rationale for every structural change.

STEP 4 — CARD-SORT STUDY SCRIPT:
- Write an open card-sort script for 10 participants using the top 20 most important content items.
- Include: instructions to participants, the 20 items to sort, and the analysis questions to ask afterwards.

STEP 5 — TREE TEST SCRIPT:
- Write a tree test for the proposed new sitemap.
- Include 5 task-based questions that will validate whether users can find the 5 most critical content items.
- Format for use in Optimal Workshop or Maze.

Output: Full audit report + revised sitemap + card-sort script + tree test script.
```

---

## Follow-Up Prompts

### Follow-Up 1: Navigation Label Rewrite
```markdown
Based on the IA audit above, rewrite the navigation labels for the top-level menu and the first level of dropdowns.
Rules:
- Use verb phrases or goal-oriented nouns (what the user can DO or GET).
- Maximum 2 words per label.
- No internal jargon, acronyms, or product-team terminology.
- Test each label with this question: "Would a first-time user understand what clicking this shows them?"
Output: Original label → Proposed label → Rationale (one sentence per change).
```

### Follow-Up 2: Mobile Navigation Adaptation
```markdown
Adapt the revised sitemap from the audit above for a mobile bottom tab bar and hamburger overflow menu.
Rules:
- Bottom tab bar: maximum 5 items. Select the 5 most frequent user tasks.
- Overflow menu: everything else, organized by secondary priority.
- Each tab bar item: icon description + label (max 1 word).
- Touch target for every tab: minimum 44 × 44 pt (iOS) / 48 × 48 dp (Android).
Output: Bottom nav item list + overflow menu structure + rationale for what was cut.
```

---

## Designer Wisdom

- **Test navigation without visual design.** Run tree tests on a plain text version of your sitemap before any mockups exist. If users cannot find content in a text tree, they cannot find it in your designed interface either. Fancy UI does not fix broken IA.
- **Navigation labels are hypotheses.** Every label is a bet that users mentally categorize that content under that word. Run a 5-second test: show a user the nav, hide it after 5 seconds, and ask them to recall the items. If they cannot recall more than 3, your labels are not landing.

**Tools that pair with this prompt:**
- **Optimal Workshop** — tree testing and card sorting platform
- **Maze** — lightweight tree testing with quick recruitment
- **Whimsical** — fast sitemap diagramming
- **Figma** — building and presenting the revised navigation
