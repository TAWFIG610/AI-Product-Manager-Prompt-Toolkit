# 12. Dark Mode Token Generator
**Category:** Design Systems · 🔀 Mix (Web + Phone)
**Phase:** Design System Build — when adding dark mode to an existing light-mode system
**Where:** Outputs CSS tokens usable in any framework (Web, React Native, Flutter, SwiftUI)

---

## Strategic Context

Dark mode is not a light mode with inverted colors. This is the most common and most costly mistake teams make when implementing it. True dark mode involves three separate challenges that naive inversion fails to handle:

1. **Depth reversal**: In light mode, elevated surfaces (cards, modals, dialogs) are *lighter* than the base page. In dark mode, elevated surfaces must be *lighter* than the dark base — but they use a layered white overlay approach (Material Design's "elevation overlays") or carefully calibrated gray stops, not simple inversion of light-mode colors.

2. **Saturation desaturation**: Brand colors that are vivid and energetic in light mode (e.g., a deep coral or electric blue) appear "neon" and visually aggressive in dark mode because the high luminance differential is exaggerated. Senior designers manually reduce saturation by 10–20% for brand colors in dark mode.

3. **Semantic color independence**: The semantic tokens (error, warning, success, info) must be independently audited for dark mode. A red background at `#FCEBEB` (light danger bg) works on a white page. On a dark `#1A1A18` page, it creates a jarring, high-contrast blob. The dark mode equivalent must be a much deeper shade (closer to Red-900 `#501313`) as the background, with lighter text.

The correct approach: **never invert raw hex values**. Always remap values through perceived lightness (OKLCH or HSL-based calculations) and validate every pairing against WCAG AA contrast before deploying.

---

## Relevant Dimensions

**Color ramp stop mapping (light → dark mode):**
| Role | Light Mode Stop | Dark Mode Stop |
|------|----------------|----------------|
| Fill / Background | 50 | 800 |
| Stroke / Border | 600 | 200 |
| Title text | 800 | 100 |
| Subtitle text | 600 | 200 |
| Mid-tone icon | 400 | 400 (review manually) |

**Elevation overlays in dark mode (Material Design 3 standard):**
| Elevation Level | White overlay opacity |
|----------------|----------------------|
| Level 0 (base surface) | 0% |
| Level 1 (card) | 5% |
| Level 2 (modal header) | 8% |
| Level 3 (navigation drawer) | 11% |
| Level 4 (app bar) | 12% |
| Level 5 (dialog) | 14% |

**WCAG contrast requirements (same as light mode):**
- Body text: **4.5:1** minimum
- Large text / UI components: **3.0:1** minimum
- AAA body text: **7.0:1**

**Platform implementation:**
- Web: CSS custom properties with `[data-theme="dark"]` selector
- iOS: `UIColor` with dynamic providers (light/dark trait collections)
- Android: `values-night/colors.xml` resource folder
- React Native: `useColorScheme()` hook + separate token objects
- Flutter: `ThemeData.dark()` with `ColorScheme`

---

## The Master Prompt

```markdown
You are a Principal Design Systems Engineer and Token Architect with 15+ years of experience building and maintaining multi-platform design systems. You specialize in semantic token systems that support light/dark mode without duplication.

My light-mode token set:
[PASTE YOUR CURRENT LIGHT-MODE CSS TOKENS OR TOKEN LIST]

Convert this light-mode token set to a complete semantic dark-mode system using the following rules:

RULE 1 — RAMP MAPPING:
Apply the standard stop remapping:
  Light: stop 50 fill + stop 600 stroke + stop 800 title + stop 600 subtitle
  Dark:  stop 800 fill + stop 200 stroke + stop 100 title + stop 200 subtitle

Do NOT simply invert hex values. If a stop is not available in the ramp, calculate the equivalent perceived lightness value.

RULE 2 — SURFACE ELEVATION (Dark Mode):
Generate 5 surface elevation levels using white overlay opacity on the base dark background:
  Level 0: base (#1A1A18 equivalent — 0% overlay)
  Level 1: 5% white overlay
  Level 2: 8% white overlay
  Level 3: 11% white overlay
  Level 4: 14% white overlay
Provide the resulting blended hex value for each level.

RULE 3 — BRAND COLOR ADJUSTMENT:
For each brand/accent color:
  (1) Test it at its light-mode value against the dark background — calculate contrast ratio
  (2) If the color appears "neon" or excessively vibrant (saturation > 70% in HSL), reduce saturation by 15%
  (3) Provide the adjusted dark-mode variant and explain the adjustment

RULE 4 — SEMANTIC COLOR REMAPPING:
For error, warning, success, and info states:
  (1) Dark background fill: use stop 900 from the semantic ramp
  (2) Dark border: use stop 400 from the semantic ramp
  (3) Dark text on dark bg: use stop 100 from the semantic ramp
  Verify all combinations pass WCAG AA (4.5:1 for text, 3:1 for UI components)

RULE 5 — WCAG VERIFICATION:
For every dark-mode text/background pairing, calculate the contrast ratio.
Flag any pair below 4.5:1 (body text) or 3:1 (UI components).
Suggest the minimum lightness adjustment to reach compliance.

OUTPUT FORMAT:
(a) CSS custom properties: :root {} for light, [data-theme="dark"] {} for dark
(b) Add a one-line comment on every non-obvious token swap explaining the remapping rationale
(c) A contrast audit table: every foreground/background pair + its dark mode ratio + pass/fail
(d) A list of tokens that required manual review with a flag for the design team
```

---

## Follow-Up Prompts

### Follow-Up 1: Platform-Specific Token Export
```markdown
Convert the dark mode CSS token set above into platform-specific formats:
(1) iOS Swift: UIColor extensions with dynamic light/dark trait collection providers
(2) Android XML: values/colors.xml (light) + values-night/colors.xml (dark)
(3) React Native: a TypeScript token object using useColorScheme() for automatic switching
(4) Flutter: a ThemeData extension with ColorScheme.fromSeed() overrides for dark mode
Add comments in each file explaining the semantic intent of each token.
```

### Follow-Up 2: Token Documentation Template
```markdown
Generate a token documentation page in Markdown for every semantic token in the system.
For each token:
  | Token name | Light value | Dark value | Usage | Do | Don't |
Where:
  - Usage: 1 sentence describing where this token appears in the UI
  - Do: correct usage example (2–3 words)
  - Don't: most common incorrect usage (2–3 words)
This becomes the living reference page in the team's design system documentation site.
```

---

## Designer Wisdom

- **Semantic tokens are the only scalable solution.** If your codebase contains `color: #2C2C2A` (a hardcoded hex), you will have to update hundreds of files to add dark mode. If it contains `color: var(--color-text-primary)`, you update one file. Build the semantic token layer before you design a single dark screen.
- **Test dark mode in outdoor sunlight.** Most dark mode designs are tested on a dim screen in a dark room. The real use case for dark mode on a phone is often outdoors at night or in a dimly lit room. Turn your device brightness to maximum and test your dark mode design. If high-contrast bright elements (like white text on dark surfaces) cause glare, you need to reduce luminance on your darkest-mode fills.

**Tools that pair with this prompt:**
- **Figma Token Studio** — connects design tokens to Figma components with light/dark sync
- **Style Dictionary (Amazon)** — compiles design tokens into platform-specific formats
- **Theo (Salesforce)** — design token transformation and platform export tool
- **OKLCH Color Picker** — perceptually uniform color space for accurate lightness mapping
