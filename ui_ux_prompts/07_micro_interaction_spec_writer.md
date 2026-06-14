# 07. Micro-Interaction Spec Writer
**Category:** Motion & Interaction · 📱 Phone Only
**Phase:** Handoff — when developers need exact animation specs to implement interactions
**Where:** Phone — works for iOS (SwiftUI), Android (Jetpack Compose), and cross-platform (React Native, Flutter)

---

## Strategic Context

Micro-interactions are the difference between a product that feels alive and one that feels like a form. They are the small, functional animations that respond to user actions — the button press, the loading state, the success confirmation. When they are done right, users never consciously notice them. When they are done wrong (too slow, too aggressive, or missing entirely), the product feels broken.

The foundational work on micro-interactions comes from Dan Saffer's book of the same name. His key insight: every micro-interaction has four components — **trigger** (what starts it), **rules** (what it does), **feedback** (how it communicates), and **loops & modes** (how it runs over time). Most development handoffs specify only the visual end state. They omit the trigger, the intermediate states, and the timing — which is why developers often implement animations that feel wrong even when the visual spec was correct.

Two additional elements make mobile interactions feel premium:
- **Haptic feedback**: the physical sensation that confirms an action. Apple's Taptic Engine and Android's vibration API support different intensities (light, medium, heavy, rigid, soft). The right haptic at the right moment makes interactions feel tangible.
- **Easing curves**: all animations should ease in or out — never move at constant velocity (linear). Ease-in for elements entering the screen, ease-out for elements leaving, ease-in-out for state changes.

---

## Relevant Dimensions

**Touch targets (required for all interactive components):**
- iOS minimum: **44 × 44 pt** | Recommended: **48 × 48 pt**
- Android minimum: **48 × 48 dp** | Recommended: **56 × 56 dp**
- Gap between adjacent interactive elements: **8 pt/dp minimum**

**Animation timing reference:**
- Instant feedback (pressed state): **0–50 ms** — imperceptible delay
- Short transitions (state changes): **100–200 ms** — snappy, responsive
- Standard transitions (screen changes): **250–350 ms** — purposeful, smooth
- Slow transitions (complex reveals): **400–500 ms** — use sparingly
- Never exceed **500 ms** for any UI interaction (feels sluggish above this)

**Standard easing curves:**
- Enter screen: `ease-out` (starts fast, slows at destination) — cubic-bezier(0.0, 0.0, 0.2, 1)
- Exit screen: `ease-in` (starts slow, exits fast) — cubic-bezier(0.4, 0.0, 1, 1)
- State change: `ease-in-out` — cubic-bezier(0.4, 0.0, 0.2, 1)
- Spring/bounce: use spring physics with stiffness and damping instead of bezier curves

**Scale animation values:**
- Pressed state: scale to **0.94–0.96** (subtle shrink)
- Success bounce: scale to **1.05** then back to **1.0**
- Error shake: translateX ±**4–6 pt**, 3 cycles at **80 ms** each

---

## The Master Prompt

```markdown
You are a Senior Mobile Interaction Designer and Motion Specialist. You write developer-ready micro-interaction specs for iOS (SwiftUI), Android (Jetpack Compose), and cross-platform frameworks (React Native, Flutter).

Component to spec: [NAME THE COMPONENT — e.g., "Like button", "Submit form button", "Bookmark icon"]
Platform: [iOS / Android / React Native / Flutter / All]
Touch target: minimum 44 × 44 pt (iOS) / 48 × 48 dp (Android)

Write a complete micro-interaction specification using the Dan Saffer 4-part model:

PART 1 — TRIGGER:
- What is the exact user action that initiates this interaction?
  (e.g., tap, long press, swipe, double-tap, force touch)
- Is there a secondary trigger (system-initiated, timer-based, or conditional)?
- What is the minimum gesture threshold? (e.g., 10 pt swipe distance before activation begins)

PART 2 — STATE MACHINE:
Define all states this component can be in, in order:
  idle → [INTERMEDIATE STATES] → final state → (error state if applicable)
For each state:
  - Visual properties: what changes (color, scale, opacity, shape, icon)
  - Duration: time in milliseconds to reach this state
  - Easing: specify the exact curve (ease-in / ease-out / ease-in-out / spring)
  - Property animated: which CSS/SwiftUI/Compose property is changing

PART 3 — FEEDBACK (Visual + Haptic):
Visual feedback:
  - What the UI shows immediately on touch (< 50 ms)
  - What the UI shows at the mid-point of the animation
  - What the UI shows at the end state
  - Error state visual: what shows when the action fails

Haptic feedback (mobile only):
  - Trigger point: at what moment in the animation does haptic fire?
  - Intensity: Light / Medium / Heavy / Rigid / Soft (iOS UIFeedbackGenerator)
  - Android equivalent: VibrationEffect.createOneShot() or EFFECT_CLICK / EFFECT_HEAVY_CLICK

PART 4 — LOOPS & MODES:
  - Does the animation loop? (e.g., loading spinners)
  - Loop condition: what makes it stop?
  - End state: what does the component look like after all animation is complete?
  - Reset behavior: does it return to idle automatically or require another trigger?

DEVELOPER OUTPUT:
Translate the above into:
- SwiftUI code snippet (iOS)
- Jetpack Compose code snippet (Android)
- React Native Animated API snippet (cross-platform)
Add comments explaining each non-obvious value.
```

---

## Follow-Up Prompts

### Follow-Up 1: Full Component State Sheet
```markdown
Based on the micro-interaction spec above, create a complete component state sheet for Figma documentation.
For the [COMPONENT NAME], list all states:
  default / hover (web only) / pressed / loading / success / error / disabled

For each state:
(1) Visual specification: background color (use token name, not hex), border, icon, text, opacity
(2) Figma variant name (exact string to use in the Figma component)
(3) When this state is triggered
(4) When this state transitions to the next state and what triggers the transition

Format: a table with one row per state. Ready to implement as Figma component variants.
```

### Follow-Up 2: Accessibility Compliance Check
```markdown
Review the micro-interaction spec above for accessibility compliance.
Check against:
(1) WCAG 2.1 Success Criterion 2.3.3 — Animation from Interactions:
   Does the animation respect the user's "Reduce Motion" setting?
   What is the fallback behavior when Reduce Motion is enabled?
(2) Focus visibility: is there a visible focus ring for keyboard/switch navigation?
   Minimum contrast ratio for focus ring: 3:1 against adjacent colors
(3) Time-based interactions: if any state has a time limit (e.g., auto-dismiss),
   is there a way for users with motor disabilities to extend it?
(4) Screen reader announcement: what does VoiceOver (iOS) / TalkBack (Android) announce
   when each state changes?
Output: compliance checklist + specific code additions needed for full accessibility.
```

---

## Designer Wisdom

- **Match the physics of the real world.** Objects in the physical world have weight and momentum. UI elements should feel like they have these qualities too. A notification card that slides in should ease-out (decelerates as it arrives, like a physical object stopping). A dismissed card should ease-in (accelerates as it leaves, like a thrown object). When animations violate physical intuition, they feel wrong — even if users cannot articulate why.
- **Test on a real device, not in a prototype tool.** Framer and Figma prototypes run at 60fps on a powerful laptop. Your animation spec will run on a 3-year-old mid-range Android device. Test every animation at the minimum spec device before signing off.

**Tools that pair with this prompt:**
- **Rive** — vector animation tool with state machines built in
- **Lottie by Airbnb** — export animations from After Effects to run natively on mobile
- **SwiftUI Animations** — Apple's native animation system with spring physics support
- **Jetpack Compose animations** — Android's declarative animation API
