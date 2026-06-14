# 04. Visual Hierarchy Score & Fix
**Category:** Visual Design · 🔀 Mix (Web + Phone)
**Phase:** Design Review or Iteration — when users skip key content or report feeling lost
**Where:** Mobile: 4-column, 16 pt margin · Web: 12-column, 80 px margin, 1120 px max-width

---

## Strategic Context

Visual hierarchy is the designer's primary tool for controlling attention. It determines what a user's eye lands on first, second, and third — and it is built entirely from three variables: **size, contrast, and space**. The mistake most junior designers make is adding more visual elements to draw attention. Senior designers do the opposite: they remove everything that competes with the primary focus.

Two eye-tracking patterns are universally documented across Western-language interfaces:
- **F-Pattern** (text-heavy content): The eye scans left-to-right across the top, then jumps down and scans left-to-right again, creating an F-shape. This means the most important information must sit in the top-left and the left edge of each row.
- **Z-Pattern** (marketing/landing pages): The eye travels top-left → top-right → diagonal to bottom-left → bottom-right, following the shape of a Z. The primary CTA should sit at the bottom-right anchor.

The most common hierarchy violation is **contrast inversion**: a designer who loves a subtle aesthetic makes everything low-contrast, which means nothing stands out — so nothing is read. WCAG AA ratios exist not just for accessibility, but for usability of all users.

---

## Relevant Dimensions

**Web:**
- Content area: **1120 px max-width**, 12-column grid, 32 px gutter
- Desktop margins: **80 px** left and right
- Section vertical padding: **80–120 px**

**Mobile:**
- Content area: **328 pt** (390 − 32 pt margins)
- Grid: **4 columns**, 16 pt gutter
- Side margins: **16 pt** left and right

**Typography contrast thresholds:**
- Body text (< 18 px / 14 px bold): minimum **4.5:1** contrast ratio
- Large text (≥ 18 px or ≥ 14 px bold): minimum **3:1** contrast ratio
- UI components (borders, icons): minimum **3:1** contrast ratio

**Standard type scale (never deviate from these sizes):**
- Mobile: 11 / 13 / 15 / 17 / 20 / 22 / 28 / 34 pt
- Web: 12 / 14 / 16 / 18 / 20 / 24 / 30 / 36 / 48 px

**8-point spacing grid — valid values only:**
4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 80 · 96 px/pt/dp

---

## The Master Prompt

```markdown
You are a Senior Visual Designer and Design Systems Lead with 15+ years of experience evaluating and rebuilding visual hierarchy for high-traffic digital products.

Platform: [Web / Mobile]
Grid: [12-column 1120 px content area / 4-column 328 pt content area]
Reading pattern to apply: [F-Pattern for text-heavy content / Z-Pattern for marketing/landing pages]

Layout description:
[DESCRIBE YOUR LAYOUT IN DETAIL — list every visible element from top to bottom, including approximate sizes, colors, and text content]

Score this layout's visual hierarchy from 1–10 using the following rubric:
  10 = The user's eye is immediately drawn to exactly the right element in the right order
  7–9 = Minor improvements needed
  4–6 = Significant hierarchy problems — user must work to find key content
  1–3 = No clear hierarchy — everything competes equally

Then identify:

(1) FIRST-FIXATION ANALYSIS:
   - What element does the eye land on first? (Apply F/Z pattern)
   - What SHOULD it land on first? (Define the #1 priority element)
   - Gap between actual and desired: describe it precisely

(2) CONTRAST VIOLATIONS (flag every one):
   - Text below 4.5:1 ratio on its background (body text)
   - Text below 3:1 ratio (large text / headings)
   - UI components (borders, icons) below 3:1

(3) SPACING VIOLATIONS (8pt grid audit):
   - Every spacing value that is NOT on the 8pt grid
   - Valid values: 4, 8, 12, 16, 24, 32, 48, 64, 80, 96

(4) TYPE SCALE MISUSE:
   - Every text size that does not appear in the standard scale
   - Mobile scale: 11/13/15/17/20/22/28/34 pt
   - Web scale: 12/14/16/18/20/24/30/36/48 px
   - Flag: more than 3 different sizes used on a single screen

(5) PRIORITIZED FIX LIST:
   - Must fix (affects conversion or comprehension)
   - Should fix (reduces cognitive load)
   - Nice to fix (polish)
   - For each fix: describe the before state, the after state, and the expected user impact.

Output: Hierarchy score with reasoning + element-by-element fix table.
```

---

## Follow-Up Prompts

### Follow-Up 1: Squint Test Simulation
```markdown
Apply the squint test to the layout described above.
When you blur your vision and look at the layout at 30%:
(1) What 3 visual elements still read clearly (high contrast, large size)?
(2) What elements disappear into the background (low contrast, small size)?
(3) Does the primary CTA read clearly at 30% blur? If not, what must change?
(4) Does the brand name / logo read clearly? If not, what must change?
Output: a ranked list of what passes and fails the squint test + specific color/size adjustments needed.
```

### Follow-Up 2: Visual Weight Redistribution Map
```markdown
Rewrite the layout description above as a Visual Weight Map.
Assign a visual weight score (1–5) to every element, where:
  5 = Maximum weight (primary heading, hero image, primary CTA)
  3 = Medium weight (subheadings, supporting visuals)
  1 = Minimum weight (captions, legal text, dividers)

Then:
(1) Verify that only 1–2 elements have a weight of 5 (if more, the hierarchy is broken)
(2) Propose a redistribution plan: which elements to increase weight, which to reduce
(3) Translate the weight changes into concrete design decisions (font-size, color stop, spacing, whitespace)
```

---

## Designer Wisdom

- **Remove before you add.** When a layout lacks visual hierarchy, the instinct is to make the important thing bigger or bolder. The better move is to reduce the visual weight of everything else. Hierarchy is relative — it only exists when some elements outweigh others.
- **Three sizes maximum.** If you can count more than three different text sizes on a single screen, the hierarchy is broken. Every size should serve a distinct role: primary information, secondary information, and metadata. Beyond three, users stop discerning levels.

**Tools that pair with this prompt:**
- **Stark** (Figma plugin) — live contrast ratio checker
- **Colour Contrast** (macOS app / browser extension) — WCAG checker
- **Attention Insight** — AI-predicted attention heatmaps for your mockups
- **Figma** — use Blur effect at 30% opacity to simulate squint test in-tool
