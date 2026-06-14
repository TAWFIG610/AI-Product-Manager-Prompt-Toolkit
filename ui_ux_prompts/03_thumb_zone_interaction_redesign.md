# 03. Thumb-Zone Interaction Redesign
**Category:** Mobile UX · 📱 Phone Only
**Phase:** Design or Iteration — when CTA tap rates are low or analytics show missed taps
**Where:** Phone — design at 390 × 844 pt/dp (medium canvas)

---

## Strategic Context

The thumb zone is one of the most researched — and most ignored — principles in mobile design. Steven Hoober's 2013 study of 1,334 smartphone users showed that 49% hold their phone with one hand and use their thumb to interact. Yet most mobile screens are designed from the top down, placing the most important actions near the top of the screen where the thumb cannot reach comfortably.

The critical insight: **the thumb is not a stylus.** It is a blunt, arc-shaped tool with a natural reach that swings from the bottom center toward the top-right corner (for right-handed users). Every millimeter further from the natural resting position requires additional cognitive and physical effort. This effort adds up — and it kills CTA conversion rates on mobile.

Senior mobile designers solve this by designing **bottom-up**: start by placing your primary CTA at the bottom, then work upward with secondary and informational elements. The visual hierarchy and thumb hierarchy should always agree.

---

## Relevant Dimensions

**Design canvas (medium — your default):**
- Canvas: **390 × 844 pt/dp**
- Test at: **320 × 568** (small) and **430 × 932** (large)

**Safe areas:**
- Top (with notch/island): **44–60 pt** clearance
- Top (no notch): **20 pt** clearance
- Bottom (gesture navigation): **34 pt** clearance
- Side margins: **16 pt** left and right

**Thumb zone pixel boundaries (on 390 × 844 canvas):**
- Natural reach zone: **y = 591–844 pt** (bottom 253 pt / ~30%)
- Stretch zone: **y = 296–591 pt** (middle 295 pt / ~35%)
- Hard reach zone: **y = 0–296 pt** (top 296 pt / ~35%)

**Touch targets:**
- iOS minimum: **44 × 44 pt** | Recommended: **48 × 48 pt**
- Android minimum: **48 × 48 dp** | Recommended: **56 × 56 dp**
- Gap between adjacent targets: **8 pt/dp minimum**

**Primary CTA (in natural reach zone):**
- Button height: **50–56 pt/dp**
- Full-width CTA: **390 − (16 × 2) = 358 pt/dp** wide
- Bottom padding above home indicator: **34 pt + 16 pt = 50 pt total**

---

## The Master Prompt

```markdown
You are a Senior Mobile UX Designer specializing in one-handed interaction patterns and thumb ergonomics.

Design canvas: 390 × 844 pt/dp (medium phone — test at 320 small and 430 large).
Safe areas: reserve top 44–60 pt (status bar + possible cutout) and bottom 34 pt (home gesture area).

Thumb zone map (apply strictly):
  Natural reach  (bottom 30%: y=591–844)  → Primary CTAs, tab bar, FAB
  Stretch zone   (middle 35%: y=296–591)  → Secondary actions, scrollable content
  Hard reach     (top 35%: y=0–296)       → Information display only — no interactive elements

My screen description:
[DESCRIBE THE SCREEN: what elements are on it, what is the primary CTA, what is the current layout top-to-bottom]

Problem: [DESCRIBE THE ISSUE — e.g., "Users are missing the primary CTA because it sits near the top"]

Redesign the layout using the thumb-zone map above. Provide:

(1) REVISED LAYOUT SPECIFICATION:
   - List each UI element with its new position (zone it sits in + approximate y-coordinate range)
   - Explain which zone each element moved to and why

(2) GESTURE SHORTCUT RECOMMENDATIONS:
   - Suggest 2–3 swipe or long-press gestures that can replace hard-reach taps
   - Specify: gesture type, trigger element, resulting action

(3) TOUCH TARGET COMPLIANCE CHECKLIST:
   - Verify every interactive element meets minimum touch target sizes
   - Flag any element that requires padding to meet the minimum (44 × 44 pt iOS / 48 × 48 dp Android)

(4) SAFE AREA COMPLIANCE:
   - Confirm no interactive elements are placed within the top 44–60 pt or bottom 34 pt safe areas

(5) ONE-HANDED vs TWO-HANDED CONSIDERATION:
   - Note if any secondary action is only reachable two-handed and recommend an accommodation
```

---

## Follow-Up Prompts

### Follow-Up 1: Gesture Shortcut Spec Sheet
```markdown
For the gesture shortcuts recommended in the thumb-zone redesign above, write a developer-ready gesture specification.
For each gesture, provide:
(1) Gesture type: swipe direction / long-press / double-tap / pinch
(2) Trigger area: exact element or region on screen
(3) Threshold: distance in pt/dp before gesture is recognized (e.g., 10 pt minimum swipe)
(4) Visual feedback: what the UI shows during the gesture (e.g., drag handle appears, element scales)
(5) Completion action: what happens when the gesture completes
(6) Cancel behavior: what happens if the gesture is interrupted mid-way
Format: one table row per gesture. Ready for developer implementation in SwiftUI / Jetpack Compose / React Native.
```

### Follow-Up 2: Figma Auto Layout Annotation Guide
```markdown
Translate the thumb-zone redesign above into Figma Auto Layout annotations.
For each major section of the screen, specify:
(1) Figma frame name
(2) Direction: Vertical / Horizontal
(3) Spacing: exact value in pt (must be on 8pt grid — valid values: 8, 16, 24, 32)
(4) Padding: top / bottom / left / right values
(5) Alignment: Left / Center / Right / Fill
(6) Resizing behavior: Fixed / Hug / Fill Container
Output: a table of Auto Layout specs I can follow in Figma without needing to think about spacing.
```

---

## Designer Wisdom

- **Design bottom-up, not top-down.** Open a blank mobile frame and ask: what is the single thing I need the user to do? Place that action at the bottom first. Then stack informational content above it. You will naturally end up with a thumb-friendly layout.
- **Check your work physically.** After placing your CTA in Figma, hold your phone with one hand and try to reach that position. If your thumb feels any strain, your users will feel it too. No usability study required — just your own hand.

**Tools that pair with this prompt:**
- **Figma** — design and test layouts at correct canvas sizes
- **Apple Human Interface Guidelines** — official safe area and touch target rules
- **Material Design 3** — Android touch target and spacing guidelines
- **UX Metrics** — measure tap accuracy rates in live products
