# 14. Design QA Checklist Generator
**Category:** QA & Handoff · 🔀 Mix (Web + Phone)
**Phase:** Handoff — immediately before design files are handed to development
**Where:** Review in Figma at correct canvas sizes (390 pt mobile / 1280 px desktop)

---

## Strategic Context

Design QA is the last checkpoint between a carefully crafted user experience and what actually gets shipped. When it is skipped or rushed, the gap between the Figma file and the production build is where user experience quietly erodes. The button is 2 pixels off. The font-weight is 400 instead of 600. The error state was never specced, so the developer invented one. Individually these seem small. Collectively they make the difference between a product that feels polished and one that feels "off" in a way users cannot articulate.

The root cause of most QA failures is not carelessness — it is **ambiguity in the handoff file**. When a developer opens Figma and sees three different shades of gray text across 10 screens, they do not know if these are intentional semantic variations or inconsistencies. A rigorous QA checklist resolves ambiguity before it becomes a bug.

Senior design teams run QA at three levels:
1. **Design file audit** (before handoff): check Figma for spec completeness, naming conventions, component usage, and explicit states
2. **Developer handoff review** (at handoff): walk developers through the file, explicitly flag every non-obvious interaction and every screen state
3. **Implementation review** (after build): compare the live build to the Figma spec on a real device — never just on a screen share

The most common handoff failures, by frequency:
1. Missing screen states (hover, pressed, loading, error, empty, disabled)
2. Inconsistent spacing (designer eyeballed it — developer picks a round number)
3. Missing responsive behavior specs (what happens when content is longer than expected?)
4. Wrong font weight (400 vs 500 is nearly invisible in Figma, obvious in production)
5. Missing safe area handling (bottom fixed buttons overlapping the home indicator)

---

## Relevant Dimensions

**Mobile canvas review sizes:**
- Default: **390 × 844 pt/dp**
- Stress test: **320 × 568 pt/dp** — always check this size for overflow
- Review on a physical device whenever possible

**Web canvas review sizes:**
- Desktop: **1280 × 800 px**
- Laptop: **1024 × 768 px**
- Tablet: **768 × 1024 px**
- Mobile (if responsive): **390 × 844 px** (Chrome DevTools)

**Spacing QA — valid values only (8pt grid):**
4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 80 · 96 pt/px/dp
*Any other value is a mistake — track down and correct before handoff.*

**Touch target QA:**
- iOS: minimum **44 × 44 pt** (visual OR invisible padding)
- Android: minimum **48 × 48 dp**
- Minimum gap: **8 pt/dp** between adjacent targets

**Typography QA — compare spec vs implementation:**
- Font family: exact match required
- Font weight: 100 · 200 · 300 · 400 · 500 · 600 · 700 · 800 · 900 (check the exact number)
- Line-height: check px/pt unit — not relative em values
- Letter-spacing: check pt/px — commonly incorrect in implementation

---

## The Master Prompt

```markdown
You are a Senior Design QA Lead and Handoff Specialist. You have reviewed and signed off on design handoffs for products used by millions of users.

Product: [DESCRIBE YOUR PRODUCT]
Platform: [iOS / Android / Web / All three]
Design tool: [Figma]
Handoff method: [Figma Dev Mode / Zeplin / Manual inspection]

Generate a comprehensive Design QA checklist organized in the following 8 categories.
For each item: write the check, the tool to use, and what a failure looks like.

CATEGORY 1 — FILE ORGANIZATION & NAMING:
  - All frames named with [screen name] + [state] convention
  - All components use library components (no detached local copies)
  - All text layers use text styles (no hardcoded font overrides)
  - All color fills use color styles or tokens (no hardcoded hex)
  - Layers are named meaningfully (no "Rectangle 47" or "Group 23")
  - Pages organized by: user flows / component library / archived explorations

CATEGORY 2 — SCREEN STATES COMPLETENESS:
  For every interactive component, verify ALL states exist:
  - Default (idle)
  - Hover (web only)
  - Pressed / Active
  - Loading (for any action > 0.5 seconds)
  - Success
  - Error
  - Empty (for any list, table, or feed)
  - Disabled
  Flag: any state documented only in a comment, not as a designed variant

CATEGORY 3 — SPACING & LAYOUT (8pt grid):
  - Every margin and padding is on the 8pt grid (valid: 4, 8, 12, 16, 24, 32, 48, 64, 80)
  - Side margins: 16 pt (mobile) / 80 px (desktop)
  - Component internal padding: documented in spec notes or annotations
  - Column gutters: 16 pt (mobile) / 24–32 px (desktop)

CATEGORY 4 — TYPOGRAPHY:
  - Every text layer uses a named text style
  - No text style name differs from the design system definition
  - No orphan font weights (e.g., weight 450 which does not exist in the font family)
  - Line heights are absolute values (pt or px) — not relative (em)
  - Maximum 3 different text sizes per screen — verify this

CATEGORY 5 — TOUCH TARGETS & INTERACTIVE ELEMENTS (mobile):
  - Every button, link, and icon-button meets 44 × 44 pt (iOS) / 48 × 48 dp (Android)
  - Every adjacent interactive element is separated by ≥ 8 pt
  - Every destructive action button is visually distinct and has a confirmation step
  - Keyboard avoidance: every input field has a documented behavior when keyboard appears

CATEGORY 6 — SAFE AREAS & PLATFORM CONSTRAINTS:
  - No interactive elements inside top 44–60 pt (status bar + notch)
  - No interactive elements inside bottom 34 pt (home indicator)
  - Fixed bottom buttons include 34 pt bottom padding above home indicator
  - Tested at 320 × 568 pt (small canvas) — no overflow or collision

CATEGORY 7 — RESPONSIVE & EDGE CASES:
  - Long text: all text fields have been tested with strings 2× the design example
  - Localization: text containers allow 30–50% text expansion for translations
  - Empty states: every list, table, feed, and dashboard has a designed empty state
  - Error states: every form field has a designed error state with specific error message
  - Offline: documented behavior when the network is unavailable

CATEGORY 8 — ACCESSIBILITY:
  - Every color pair passes WCAG AA contrast (4.5:1 body, 3:1 large/UI)
  - No information is communicated by color alone (always paired with icon or text)
  - Every interactive element has an accessibility label documented in the spec
  - Reduce Motion: documented fallback for every animation
  - Focus order: documented tab/focus order for keyboard and switch navigation

Output format: a printable checklist with checkboxes — one row per item, organized under category headers.
Mark highest-risk items (CRITICAL) and moderate-risk items (IMPORTANT).
```

---

## Follow-Up Prompts

### Follow-Up 1: Handoff Annotation Template
```markdown
Generate a Figma annotation template for the handoff of [SCREEN OR FEATURE NAME].
Include annotation callouts for:
(1) Every spacing value that is not immediately obvious from the layout
(2) Every interactive element with its touch target size (including invisible padding)
(3) Every component state transition (what triggers it, what animates, how long it takes)
(4) Every placeholder text or dynamic content area (mark with [DYNAMIC — max X characters])
(5) Every safe area boundary with its exact reserved size
Format: I will add these as Figma annotation sticky notes using the standard callout format.
```

### Follow-Up 2: Developer Handoff Walk-Through Agenda
```markdown
Create a 45-minute developer handoff meeting agenda for the [FEATURE NAME] design.
Include:
(1) A 5-minute orientation: what the feature does and why (user problem + business goal)
(2) A 10-minute file walk: how the Figma file is organized and where to find what
(3) A 20-minute component-by-component review: the 5 most complex or novel components
    For each: states, animations, edge cases, accessibility requirements
(4) A 5-minute Q&A with pre-written prompt questions the designer should ask the engineer
(5) A 5-minute action list: open items, decisions needed, agreed implementation notes
Output: a meeting agenda with time blocks + speaker notes for the designer-presenter.
```

---

## Designer Wisdom

- **Run QA on a physical device, not on a screen share.** Colors look different on different screens. Touch targets feel different on a physical device. Typography rendering varies between operating systems. Never sign off on a design review conducted exclusively in Figma on a shared screen.
- **Make error states your first review priority.** Error states are the most commonly skipped and the most commonly implemented incorrectly. If the developer never sees an error state design, they will invent one. And it will almost certainly be a generic red toast notification with "Something went wrong."

**Tools that pair with this prompt:**
- **Figma Dev Mode** — built-in handoff layer with auto-measured spacing and token inspection
- **Zeplin** — standalone handoff platform with style guide export
- **Lingo** — asset management and design system documentation
- **BrowserStack** — real device testing for web across hundreds of browsers and devices
