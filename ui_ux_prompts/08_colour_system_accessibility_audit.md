# 08. Colour System Accessibility Audit
**Category:** Accessibility · 🔀 Mix (Web + Phone)
**Phase:** Design System Sign-Off or after a WCAG audit failure
**Where:** Applies to every screen, every platform

---

## Strategic Context

Accessibility audits are often treated as a compliance checkbox — something to do before launch to avoid legal risk. Senior designers know this framing is wrong. WCAG contrast ratios are not arbitrary bureaucratic thresholds. They correspond to the actual luminance relationships that the human visual system needs to distinguish foreground from background. When text fails the 4.5:1 ratio, it is not just inaccessible to users with low vision — it is objectively harder to read for every user, in every light condition.

The most common accessibility failure in modern design systems is **brand color misuse**. A marketing team picks a bright, vivid primary color for energy and memorability. The design team applies that color to text, buttons, and UI components without checking contrast. The result: a brand that looks beautiful in a mockup and fails on a real screen in outdoor sunlight or for 8% of men who have some form of color vision deficiency.

The most critical insight for accessibility audits: **never audit colors in isolation**. A color is only accessible in the context of what it sits on. `#378ADD` (Blue/400) may pass on white (`#FFFFFF`) but fail on gray-50 (`#F1EFE8`). You must test every foreground-background combination that actually appears in your UI.

**Color blindness statistics (global):**
- Deuteranopia/Deuteranomaly (red-green): ~6% of men, 0.4% of women
- Protanopia/Protanomaly (red-blind): ~2% of men
- Tritanopia (blue-blind): ~0.01% of population

---

## Relevant Dimensions

**WCAG 2.1 Contrast Standards:**

| Standard | Ratio | Applies To |
|----------|-------|-----------|
| AA — Normal text (< 18 px / 14 px bold) | **4.5 : 1** | Body text, labels, captions |
| AA — Large text (≥ 18 px / ≥ 14 px bold) | **3.0 : 1** | Headings, large display text |
| AA — UI Components & Icons | **3.0 : 1** | Borders, icons, input field outlines |
| AAA — Normal text | **7.0 : 1** | Highest level — critical content |
| AAA — Large text | **4.5 : 1** | Maximum readability |

**Color ramp usage rules (from master reference):**
- Body text on light background: use Stop **800** or **900** (always passes)
- Body text on dark background: use Stop **50** or **100** (always passes)
- Border/stroke on light fill: Stop **600** typically passes 3:1 check
- Mid-tones (Stop 400): use only for decorative elements — never for text

**Platform-specific color considerations:**
- iOS: respect `UIColor.label` and `UIColor.secondaryLabel` for automatic dark mode adaptation
- Android: use Material Color System with `colorOnSurface` and `colorOnBackground` tokens
- Web: use CSS custom properties with `[data-theme="dark"]` override (see `00_master_dimensions_and_color_reference.md`)

---

## The Master Prompt

```markdown
You are a Senior Accessibility Designer and WCAG Compliance Expert. You have conducted WCAG audits for Fortune 500 products and design systems used by millions of users.

My colour palette:
  Primary color: [#HEX]
  Secondary color: [#HEX]
  Background (primary): [#HEX]
  Background (secondary / card): [#HEX]
  Text (primary): [#HEX]
  Text (secondary): [#HEX]
  Error: [#HEX]
  Warning: [#HEX]
  Success: [#HEX]
  Info: [#HEX]
  Border (default): [#HEX]

STEP 1 — CONTRAST MATRIX:
Test every foreground-background combination that actually appears in the UI.
For each combination, calculate the exact contrast ratio and provide a pass/fail verdict for:
  - WCAG AA Normal text (4.5:1)
  - WCAG AA Large text / UI (3.0:1)
  - WCAG AAA Normal text (7.0:1)
Output as a table: Foreground | Background | Ratio | AA Normal | AA Large | AAA

STEP 2 — FAILURE REMEDIATION (for every failing pair):
(1) State the exact contrast ratio and the gap to the nearest passing threshold
(2) Identify which property to adjust: lightness only — preserve hue and saturation
(3) Provide the corrected hex value that achieves AA compliance
(4) Provide the corrected hex value that achieves AAA compliance (if reasonably achievable)
(5) Flag if the correction significantly changes the brand appearance and recommend a review

STEP 3 — COLOR BLINDNESS SIMULATION:
Simulate the following deficiencies:
  - Deuteranopia (red-green — most common): describe which color pairs become indistinguishable
  - Protanopia (red-blind): describe which color pairs become indistinguishable
For any pair that becomes indistinguishable:
  - Flag which UI elements rely solely on that color distinction
  - Recommend a non-color signal to add (icon, pattern, label, shape change)

STEP 4 — DARK MODE AUDIT:
  - Test the same combinations using the dark mode palette
  - Flag any color that requires manual saturation adjustment in dark mode
    (colors that are vivid/saturated in light mode often look "neon" in dark backgrounds)

STEP 5 — CORRECTED PALETTE:
  Output the full corrected palette as:
  (a) A table of original vs corrected hex values with achieved ratios
  (b) CSS custom properties block for immediate implementation

Output: Full audit report + corrected palette + CSS variables.
```

---

## Follow-Up Prompts

### Follow-Up 1: ARIA & Semantic Color Labeling Spec
```markdown
For the corrected colour palette above, write the complete ARIA and semantic labeling specification.
For every semantic color state (error, warning, success, info):
(1) The ARIA role or aria-live attribute to announce state changes to screen readers
(2) The icon to pair with the color (so color-blind users get a non-color signal)
(3) The text label to always include alongside the color indicator
(4) The exact VoiceOver (iOS) / TalkBack (Android) announcement string
Rule: Never rely on color alone to communicate state. Every color state must have a text or icon equivalent.
```

### Follow-Up 2: Design Token Accessibility Lock
```markdown
Add accessibility enforcement rules to the design token system from the audit above.
For each token, specify:
(1) Permitted use cases: where this token CAN be applied
(2) Prohibited use cases: where this token MUST NOT be applied
(3) Required pairing: which background token(s) this token must always be paired with to maintain compliance
(4) Auto-failing combination: which background tokens would cause this token to fail WCAG AA
Format as a token governance table for use in Figma Token Studio or Style Dictionary.
```

---

## Designer Wisdom

- **Build a contrast checker into your design workflow, not your review process.** By the time a WCAG failure is caught in review, it has already propagated across 50 mockup screens. Use a Figma plugin like Stark or Able that flags contrast failures in real time as you design.
- **WCAG 3.0 is coming.** WCAG 3.0 replaces the contrast ratio formula with a new metric called APCA (Advanced Perceptual Contrast Algorithm) that is more accurate for modern screens. If you are building a long-lived design system, research APCA now. The 4.5:1 threshold in WCAG 2.1 will eventually be replaced.

**Tools that pair with this prompt:**
- **Stark** (Figma plugin) — live contrast checking and color blindness simulation
- **Colour Contrast Analyser** (Paciello Group) — desktop tool for any color pair
- **Coblis** — online color blindness simulator for screenshots
- **APCA Contrast Calculator** — WCAG 3.0 readiness checker
- **Figma Token Studio** — design token system with governance rules
