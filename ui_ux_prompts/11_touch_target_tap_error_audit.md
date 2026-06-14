# 11. Touch Target & Tap Error Audit
**Category:** Mobile Usability · 📱 Phone
**Phase:** QA Phase or Post-Launch — when analytics show high tap error rates or user complaints
**Where:** Phone — audit at small (320 pt/dp) AND medium (390 pt/dp) canvas sizes

---

## Strategic Context

Tap errors are the silent killer of mobile conversion rates. A user who mis-taps a button — activating the wrong element, or tapping in empty space — does not always try again. In high-stakes flows (checkout, form submission, destructive actions), a single mis-tap can cause immediate abandonment. And unlike visual design errors, tap errors are nearly invisible in design reviews because mockup tools do not simulate the imprecision of a human finger on a touchscreen.

The minimum touch target sizes specified by Apple (44 × 44 pt) and Google (48 × 48 dp) are based on research into human finger contact areas. The average adult fingertip contact area is approximately 10–11 mm. On a standard modern phone at 390 pt canvas, 44 pt ≈ 9.5 mm — just at the minimum for reliable targeting. Anything smaller is betting that your users have smaller-than-average fingers, are using their phone in ideal conditions, and are fully focused on your app.

The most common touch target failures in real products:
1. **Icon-only buttons** that are visually 20–24 pt but have no padding to extend the hit area
2. **Dense list rows** where adjacent rows are less than 8 pt apart (the gap shrinks the effective target)
3. **Destructive actions** (delete, sign out, cancel subscription) that are placed immediately adjacent to primary actions without a confirmation step or adequate spacing
4. **Small (320 pt) canvas failures** — elements that pass on 390 pt but overflow or collide at 320 pt

---

## Relevant Dimensions

**Minimum touch target sizes:**
| Platform | Minimum | Recommended | Physical equivalent |
|----------|---------|-------------|---------------------|
| iOS | 44 × 44 pt | 48 × 48 pt | ~9.5 × 9.5 mm |
| Android | 48 × 48 dp | 56 × 56 dp | ~10.5 × 10.5 mm |
| Web | 44 × 44 px | 48 × 48 px | — |
| Physical minimum (any) | — | — | 9 × 9 mm |

**Minimum gap between adjacent touch targets:**
- iOS / Android: **8 pt/dp** minimum
- Physical: **2 mm** minimum between distinct targets

**Canvas sizes to audit (always test both):**
- Small: **320 × 568 pt/dp** (stress test)
- Medium: **390 × 844 pt/dp** (standard)

**Safe areas (no interactive elements inside):**
- Top: **44–60 pt** (status bar + notch/island)
- Bottom: **34 pt** (home indicator)
- Sides: **16 pt** margin (content boundary)

**Destructive action spacing rule:**
- Destructive buttons must be separated from primary CTAs by a minimum of **32 pt/dp**
- Destructive actions must show a confirmation dialog before execution
- Confirmation dialog must make the cancel/dismiss path visually dominant

---

## The Master Prompt

```markdown
You are a Senior Mobile QA Designer and Accessibility Auditor specializing in touch target compliance across iOS and Android devices.

Platform: [iOS / Android / Both]
Screen description: [DESCRIBE EVERY INTERACTIVE ELEMENT ON THE SCREEN — list each button, link, icon, input field, and list row with its approximate visual size]

Audit at TWO canvas sizes:
  Canvas A — Small: 320 × 568 pt/dp
  Canvas B — Medium: 390 × 844 pt/dp

For each interactive element, check against:
  iOS minimum: 44 × 44 pt (visible OR hit area including invisible padding)
  Android minimum: 48 × 48 dp
  Minimum gap between adjacent targets: 8 pt/dp
  Physical minimum: 9 × 9 mm on any screen density

STEP 1 — ELEMENT-BY-ELEMENT AUDIT TABLE:
For every interactive element, produce a table row with:
  | Element Name | Visual Size | Hit Area (with padding) | iOS Pass? | Android Pass? | Gap to Nearest Element | Gap Pass? |

STEP 2 — FAILURE CATALOG:
For every element that fails:
  (1) State exact current size vs. required size
  (2) Recommended fix: specific padding to add (in pt/dp, on 8pt grid)
  (3) Severity: Critical (blocks task completion) / Major (causes errors) / Minor (friction)

STEP 3 — DESTRUCTIVE ACTION AUDIT:
  List every button that triggers an irreversible action (delete, logout, cancel subscription, clear all).
  For each:
  (1) Is it separated from primary actions by ≥ 32 pt/dp?
  (2) Does it show a confirmation dialog before execution?
  (3) In the confirmation dialog: is the cancel/dismiss path visually dominant?

STEP 4 — SMALL CANVAS (320 pt) FAILURE ANALYSIS:
  At 320 pt wide (content area = 288 pt):
  (1) Which elements overflow their container?
  (2) Which adjacent elements collide (gap < 8 pt)?
  (3) What layout adjustments are needed for this canvas?

STEP 5 — PRIORITY FIX LIST:
  Rank all failures by severity × frequency of this element being interacted with.
  Output: ordered fix list with before/after size specs and implementation notes.
```

---

## Follow-Up Prompts

### Follow-Up 1: Annotated Figma Redline Spec
```markdown
Convert the touch target audit above into a Figma redline annotation spec.
For every failing element:
(1) Annotation label: current hit area size
(2) Correction arrow: required padding to add (top/bottom/left/right separately)
(3) Annotation note: severity + reasoning in one sentence
Format: a list I can use to add annotations in Figma's measurement overlay.
Provide padding values on the 8pt grid only (valid: 4, 8, 12, 16, 24 pt/dp).
```

### Follow-Up 2: Automated Test Specification
```markdown
Based on the touch target audit, write automated test specifications for:
  Platform: [iOS XCUITest / Android Espresso / React Native Detox]
For each critical failure found:
(1) Test name: descriptive, format "should_have_minimum_touch_target_[element_name]"
(2) Element identifier: accessibility ID or test ID to target in code
(3) Test assertion: verify the tap area width ≥ 44 pt (iOS) / 48 dp (Android)
(4) Test for minimum gap: verify distance to adjacent element ≥ 8 pt/dp
These tests should run in the CI/CD pipeline on every PR that touches layout files.
```

---

## Designer Wisdom

- **Invisible padding is your friend.** The visible element does not need to be large — the tappable area does. A 20 pt icon can have 12 pt padding on all sides, making the hit area 44 pt without changing the visual design. This is the correct solution — not enlarging every icon.
- **Test on a real device at the real size.** Tap targets that feel correct at 390 pt in Figma often fail on a physical device at 320 pt when you are holding the phone naturally. Print your screens at physical size and try tapping with your non-dominant hand. You will find failures in 30 seconds that your design review missed entirely.

**Tools that pair with this prompt:**
- **Figma** — use measure overlays to audit spacing between elements
- **Reveal** (iOS) — inspect live running apps to see actual touch target areas
- **Android Accessibility Scanner** — on-device audit tool that flags touch target failures
- **Appium** — cross-platform test automation for touch target compliance tests
