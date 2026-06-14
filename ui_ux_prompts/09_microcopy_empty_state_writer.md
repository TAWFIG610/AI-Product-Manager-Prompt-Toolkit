# 09. Microcopy & Empty State Writer
**Category:** UX Writing · 🔀 Mix (Web + Phone)
**Phase:** Handoff — just before developer handoff when all screen states must be documented
**Where:** Applies to all platforms — every screen with text

---

## Strategic Context

Microcopy is the smallest text in an interface that carries the biggest influence on user behavior. A button label, an error message, a placeholder in a form field — each is a micro-decision point where a user either continues or hesitates. Poor microcopy creates anxiety. Great microcopy creates confidence.

The most neglected microcopy in most products is the **empty state**. Empty states are screens that appear when there is no content yet — a first-time user's empty dashboard, a search with no results, an empty inbox. Most teams treat empty states as edge cases and ship them with placeholder text like "No results found" or leave them completely blank. This is a critical failure: empty states are often the *first* screens new users see, and a blank screen communicates "this product isn't working" rather than "here's what to do next."

The three elements every great empty state needs:
1. **An explanation** — what is this space for? (one sentence, non-technical)
2. **An instruction** — what should the user do to fill it? (one specific action)
3. **An affordance** — a button or link that makes taking that action effortless

**Brand voice discipline:** Microcopy is where brand voice is most tested. The gap between a brand that sounds "friendly" and one that sounds "patronizing" is a single word. Rule: read every piece of microcopy aloud. If you would not say it to a customer's face, don't write it in the UI.

---

## Relevant Dimensions

**Typography for microcopy states:**
- Empty state headline: **Title Small (20 pt / H5 20 px)**, weight 600
- Empty state body: **Body (17 pt / 16 px)**, weight 400, line-height 1.5
- CTA button label: **Headline (17 pt / 16 px)**, weight 600
- Error message text: **Body Small (15 pt / 14 px)**, weight 400
- Placeholder/hint text: **Body (17 pt / 16 px)**, weight 400, opacity 0.5

**Empty state illustration sizing (if used):**
- Mobile: **120–160 pt** wide (centered in 390 pt canvas with 16 pt margins)
- Web: **160–200 px** wide (centered within content column)

**Text length constraints:**
- Headline: max **6 words**
- Body: max **20 words** (2 short sentences maximum)
- CTA label: max **3 words**
- Error message: max **25 words** — name the problem, name the solution, that's it

**Color for microcopy states:**
- Empty state headline: `--color-text-primary` (#2C2C2A light / #F1EFE8 dark)
- Empty state body: `--color-text-secondary` (#5F5E5A light / #B4B2A9 dark)
- Error text: `--color-text-danger` (#791F1F light / #F7C1C1 dark)
- Error background: `--color-bg-danger` (#FCEBEB light) with `--color-border-danger` (#A32D2D)

---

## The Master Prompt

```markdown
You are a Principal UX Writer with 15+ years of experience writing microcopy for high-growth digital products. You understand that every word in a UI is a design decision with measurable impact on user behavior.

App name: [APP NAME]
Brand voice: [DESCRIBE IN 3–5 ADJECTIVES — e.g., "confident, warm, direct, never condescending, slightly playful"]
Platform: [Mobile / Web / Both]

Write microcopy for the following 8 UI states:

STATE 1 — EMPTY SEARCH RESULTS:
Context: User searched for "[EXAMPLE QUERY]" but nothing was found.
Rules: Acknowledge the lack of results, explain why (if inferrable), give a next step.

STATE 2 — 404 / PAGE NOT FOUND:
Context: User navigated to a URL that does not exist.
Rules: Do not apologize. Explain what happened. Give 1–2 paths forward.

STATE 3 — FORM SUBMISSION SUCCESS:
Context: User just submitted [FORM TYPE — e.g., "a contact form" / "a payment" / "a support ticket"].
Rules: Confirm what happened, set expectations for what comes next, include a time estimate if relevant.

STATE 4 — NETWORK / CONNECTION ERROR:
Context: User attempted an action but the server is unreachable.
Rules: Tell them what they were trying to do is not lost. Give them an action (retry / check connection).

STATE 5 — FIRST-TIME EMPTY DASHBOARD:
Context: New user just signed up and their workspace is empty.
Rules: Explain what this space is for. Give the single most important first action. Make it feel welcoming, not clinical.

STATE 6 — PERMISSION DENIED (mobile):
Context: User tried to take a photo/access location but has not granted permission.
Rules: Explain the benefit of granting permission (not just that it is required). Give a direct path to Settings.

STATE 7 — LOADING STATE (long operation > 2 seconds):
Context: User clicked a button that triggers a slow operation (e.g., "Analyzing report" / "Generating PDF").
Rules: Show progress. Manage expectation with a realistic time estimate. Optional: show what is happening.

STATE 8 — DESTRUCTIVE ACTION CONFIRMATION:
Context: User clicked "Delete account" / "Delete all files" / similar irreversible action.
Rules: Name the specific consequence. Use plain language. Make the cancel path visually dominant. Do not use "Are you sure?"

For every state deliver:
  - Headline: max 6 words
  - Body: max 20 words
  - CTA label: max 3 words
  - Secondary CTA (if applicable): max 3 words

Typography: headline renders at Title Small (20 pt / H5 20 px), body at Body (17 pt / 16 px).
Banned openers: "Oops", "Uh oh", "Whoops", "Something went wrong", "Sorry about that".
```

---

## Follow-Up Prompts

### Follow-Up 1: Tone Calibration Matrix
```markdown
The [APP NAME] microcopy above needs to be calibrated for 3 different user emotional contexts.
Create a tone calibration matrix for the error and empty states.
For each state, write 3 versions:
  - Version A: user is stressed / time-pressured (make it fast and action-oriented)
  - Version B: user is confused / first-time (make it educational and reassuring)
  - Version C: user is frustrated / returning after a failure (acknowledge the difficulty, prioritize resolution)
Output: a table with 3 columns (A/B/C) and one row per state. This becomes the copywriter's tonal range guide.
```

### Follow-Up 2: Microcopy Localization Brief
```markdown
The microcopy above will be translated into [TARGET LANGUAGES — e.g., "Arabic, French, Spanish"].
Write a localization brief for each state that includes:
(1) The intent and emotional tone of each line (what feeling should it create? — not just what it says)
(2) Cultural notes: are there phrases that are idiomatic in English but may not translate directly?
(3) Text expansion: which strings are likely to expand by 30–50% in translation and need layout flexibility?
(4) Character limits: flag any CTA label with a character limit that must be enforced in translations
Output: localization brief table ready to hand to translators alongside the English source strings.
```

---

## Designer Wisdom

- **Write for the worst moment.** Your error messages and empty states are read when something has gone wrong. This is the moment users are most likely to leave your product permanently. Treat these strings with more care than your headline copy — not less.
- **Test microcopy with the 5-second rule.** Show a user the empty state or error for 5 seconds, then hide it. Ask: "What did it say?" and "What would you do next?" If they cannot answer both correctly, the copy is not working.

**Tools that pair with this prompt:**
- **Hemingway Editor** — checks for complex sentences and passive voice
- **Writer.com** — AI writing assistant with brand voice enforcement
- **Figma** — always render microcopy at the correct type size to catch overflow before handoff
- **Crowdin / Phrase** — localization management platforms for the localization brief
