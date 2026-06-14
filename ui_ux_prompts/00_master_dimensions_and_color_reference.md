# 00. Master Dimensions & Color Reference
> Your single source of truth for every design number.
> All values are production-ready. Never guess — look it up here first.

---

# SECTION 1 — PHONE DIMENSIONS

## Design Units

Design in **points (pt)** on iOS and **density-independent pixels (dp)** on Android.
Never design in raw pixels. The operating system handles pixel scaling automatically.

---

## Phone Canvas Sizes

| Size Class | Width | Height | When to Use |
|------------|-------|--------|-------------|
| Small (stress test) | 320 pt/dp | 568 pt/dp | Oldest/smallest supported size. Always test here. |
| Standard | 375 pt/dp | 667 pt/dp | Safe default. iPhone SE, mid-range Android. |
| **Medium (your default)** | **390 pt/dp** | **844 pt/dp** | **Most common modern phone. Design here.** |
| Large | 430 pt/dp | 932 pt/dp | iPhone Plus/Max, large Android flagships. |
| Android minimum | 360 dp | 640 dp | Smallest Android still in active use. |

> **Rule:** Design at **390 × 844**. Test at **320** (small) and **430** (large). If it works at both extremes, it works on every phone.

---

## Phone Screen Areas & Safe Zones

```
┌─────────────────────────────┐
│  STATUS BAR  ~20–60 pt      │  ← System only. Clocks, battery, signal.
│  (notch / island / none)    │     Minimum 44 pt clearance always.
├─────────────────────────────┤
│  APP BAR  44 pt             │  ← Your navigation header.
├─────────────────────────────┤
│                             │
│        CONTENT AREA         │  ← Your main design canvas.
│   Left/Right margin: 16 pt  │     All interactive elements live here.
│                             │
│                             │
├─────────────────────────────┤
│  BOTTOM NAV  49–80 pt       │  ← Tab bar or bottom navigation.
├─────────────────────────────┤
│  HOME INDICATOR  ~34 pt     │  ← System only. Never place content here.
└─────────────────────────────┘
```

| Safe Area | Reserve | Why |
|-----------|---------|-----|
| Top (with notch/island) | 44–60 pt | Dynamic Island / notch / camera cutout |
| Top (no notch) | 20 pt | Status bar |
| Bottom (gesture navigation) | 34 pt | Home indicator swipe area |
| Left / Right | 16 pt margin | Standard side padding |

> **Implementation:** Always use platform safe area APIs (`SafeAreaInsets` on iOS, `WindowInsets` on Android) so layouts adapt automatically.

---

## Thumb Zone Map

```
Any phone — held in one hand:

┌──────────────────────┐
│  ░░░░░░░░░░░░░░░░░░  │  Top 35% — HARD REACH ZONE 🔴
│  ░░░░░░░░░░░░░░░░░░  │  → Information display only.
│  ░░░░░░░░░░░░░░░░░░  │    Never place interactive elements here.
├──────────────────────┤
│  ▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒  │  Middle 35% — STRETCH ZONE 🟡
│  ▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒  │  → Secondary actions.
│  ▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒  │    Scrollable content. Navigation links.
├──────────────────────┤
│  ████████████████████  │  Bottom 30% — NATURAL REACH 🟢
│  ████████████████████  │  → Primary CTAs. Tab bar. FAB.
│  ████████████████████  │    All key actions live here.
├──────────────────────┤
│  [ home indicator ]    │  ← System reserved. Leave clear.
└──────────────────────┘

Right-handed: thumb arc swings bottom-left → top-right.
Left-handed: mirror. Design primary CTAs bottom-center for ambidextrous reach.
```

---

## Touch Target Sizes

| Platform | Minimum | Recommended | Gap Between Targets |
|----------|---------|-------------|---------------------|
| iOS | 44 × 44 pt | 48 × 48 pt | 8 pt min |
| Android | 48 × 48 dp | 56 × 56 dp | 8 dp min |
| Web | 44 × 44 px | 48 × 48 px | 8 px min |
| Physical (any device) | 9 × 9 mm | 10 × 10 mm | — |

> **Rule:** The *visible* element can be smaller — but the *tappable hit area* must always meet minimum. Use invisible padding to extend the hit area.

---

## Standard Component Heights

| Component | Phone (pt/dp) | Web (px) |
|-----------|--------------|----------|
| App Bar / Navigation Bar | 44–56 | 56–64 |
| Tab Bar / Bottom Nav | 49–80 | 48–56 |
| Search Bar | 36–56 | 44–56 |
| Button — Standard | 44–48 | 40–48 |
| Button — Large/Primary CTA | 50–56 | 52–56 |
| Input Field | 44–56 | 44–56 |
| List Row — Compact | 44–48 | 44–48 |
| List Row — Standard | 56–64 | 56–64 |
| Card — Minimum Height | 80 | 80 |
| FAB — Standard | 56 | 56 |
| FAB — Mini | 40 | 40 |
| Bottom Sheet Drag Handle | 32 (drag area) | — |
| Chip / Tag | 32 | 32 |
| Icon — Inline | 20–24 | 20–24 |
| Icon — Standalone | 24–32 | 24–32 |

---

# SECTION 2 — WEB DIMENSIONS

## Breakpoint System

| Name | Width Range | Layout | Columns |
|------|------------|--------|---------|
| Mobile S | < 360 px | Single column | 4 |
| Mobile | 360–767 px | Single column | 4 |
| Tablet | 768–1023 px | Two column | 8 |
| Laptop | 1024–1279 px | Multi-column | 12 |
| Desktop | 1280–1535 px | Full layout | 12 |
| Desktop L | 1536 px+ | Full layout, centered | 12 |

## Content Area Width (with standard margins)

| Breakpoint | Page Width | L/R Margin | Content Width | Column Gutter |
|------------|-----------|------------|---------------|---------------|
| Mobile | 360 px | 16 px | 328 px | 16 px |
| Tablet | 768 px | 32 px | 704 px | 24 px |
| Laptop | 1024 px | 48 px | 928 px | 24 px |
| Desktop | 1280 px | 80 px | 1120 px | 32 px |
| Desktop L | 1440 px | 160 px | 1120 px | 32 px |
| **Max container** | **any** | **auto center** | **1280 px max** | **32 px** |

> **Rule:** Never let content exceed **1280 px** wide. Center it with auto margins on larger screens.

## Web Viewport Areas

```
┌────────────────────────────────────────┐
│  HEADER / TOP NAV  56–80 px            │  ← Fixed or sticky.
├────────────────────────────────────────┤
│  HERO / ABOVE THE FOLD  600–900 px     │  ← Primary message + main CTA.
├────────────────────────────────────────┤
│  MAIN CONTENT AREA  1280 px max        │  ← Fluid. Section padding: 80–120 px vertical.
├────────────────────────────────────────┤
│  FOOTER  120–300 px                    │  ← Links, legal, socials.
└────────────────────────────────────────┘
```

---

# SECTION 3 — SPACING SCALE (8-Point Grid)

> **The rule:** Every spacing value must be a multiple of **8**. Use **4** only for micro-gaps (icon-to-label, badge padding).

| Token | Value | Typical Use |
|-------|-------|-------------|
| `space-xs` | 4 px/pt/dp | Icon-to-label gap, badge padding |
| `space-sm` | 8 | Tight internal padding, small gaps |
| `space-md` | 16 | Standard padding, mobile column gutter |
| `space-lg` | 24 | Card padding, section sub-gap |
| `space-xl` | 32 | Between components |
| `space-2xl` | 48 | Between sections (mobile) |
| `space-3xl` | 64 | Between sections (desktop) |
| `space-4xl` | 80 | Page section gap |
| `space-5xl` | 96–120 | Hero spacing, top-of-page breathing room |

**Valid values only:** 4 · 8 · 12 · 16 · 24 · 32 · 48 · 64 · 80 · 96 px/pt/dp

---

# SECTION 4 — TYPOGRAPHY SCALE

## Mobile Scale (pt on iOS / sp on Android)

| Role | Size | Weight | Line Height |
|------|------|--------|-------------|
| Display / Hero | 34 pt | 700 | 1.2 |
| Title Large | 28 pt | 700 | 1.25 |
| Title | 22 pt | 700 | 1.3 |
| Title Small | 20 pt | 600 | 1.3 |
| Headline | 17 pt | 600 | 1.4 |
| Body | 17 pt | 400 | 1.5 |
| Body Small | 15 pt | 400 | 1.5 |
| Caption | 13 pt | 400 | 1.4 |
| Label / Overline | 11 pt | 500 | 1.3 |

## Web Scale (px)

| Role | Size | Weight | Line Height |
|------|------|--------|-------------|
| Display XL | 72 px | 700 | 1.1 |
| Display | 56 px | 700 | 1.1 |
| H1 | 48 px | 700 | 1.15 |
| H2 | 36 px | 600 | 1.2 |
| H3 | 30 px | 600 | 1.25 |
| H4 | 24 px | 600 | 1.3 |
| H5 | 20 px | 500 | 1.35 |
| H6 | 16 px | 500 | 1.4 |
| Body Large | 18 px | 400 | 1.7 |
| Body | 16 px | 400 | 1.7 |
| Body Small | 14 px | 400 | 1.6 |
| Caption | 12 px | 400 | 1.5 |
| Label / Overline | 11 px | 500 | 1.4 |

> **Rules:** Never go below **11 px/pt** for any visible text. Never use more than **3 type sizes** on a single screen.

---

# SECTION 5 — COLOR SYSTEM

## Color Assignment Priority Order

```
PRIORITY 1 — SEMANTIC (universal meaning — always consistent)
  Red    → Error / Danger / Destructive
  Amber  → Warning / Caution
  Green  → Success / Confirmed / Positive
  Blue   → Info / Neutral action / Links

PRIORITY 2 — BRAND (your product identity)
  Primary   → Main brand color (buttons, key highlights)
  Secondary → Accent / supporting brand color
  Tertiary  → Subtle tint, decorative use only

PRIORITY 3 — NEUTRAL (structure, text, surfaces)
  Near-black  → Primary text / headings
  Mid-gray    → Secondary text / labels
  Light gray  → Placeholder / hint / disabled
  Subtle gray → Borders / dividers
  Off-white   → Surface / card background
  White       → Page background

PRIORITY 4 — CATEGORICAL (data viz & multi-item UI only)
  Category A → Purple or Blue
  Category B → Teal or Green
  Category C → Coral or Orange
  Category D → Pink or Amber
  Category E → Gray (neutral / "other")
```

## The 60–30–10 Rule

| Layer | % of Screen | What Goes Here |
|-------|------------|----------------|
| Neutral / Background | 60% | Page bg, large surfaces, text |
| Secondary / Surface | 30% | Cards, panels, secondary elements |
| Accent | 10% | CTAs, links, icons, badges, highlights |

---

## Full Color Ramp System — 9 Ramps × 7 Stops

**Stop usage guide:**
- `50–200` → Background fills, hover states, subtle tints
- `400` → Mid-tone icons, illustrations
- `600` → Borders, strong accents, strokes
- `800–900` → Text on light backgrounds, headings

### Purple
| 50 | 100 | 200 | 400 | 600 | 800 | 900 |
|----|-----|-----|-----|-----|-----|-----|
| `#EEEDFE` | `#CECBF6` | `#AFA9EC` | `#7F77DD` | `#534AB7` | `#3C3489` | `#26215C` |

### Teal
| 50 | 100 | 200 | 400 | 600 | 800 | 900 |
|----|-----|-----|-----|-----|-----|-----|
| `#E1F5EE` | `#9FE1CB` | `#5DCAA5` | `#1D9E75` | `#0F6E56` | `#085041` | `#04342C` |

### Coral
| 50 | 100 | 200 | 400 | 600 | 800 | 900 |
|----|-----|-----|-----|-----|-----|-----|
| `#FAECE7` | `#F5C4B3` | `#F0997B` | `#D85A30` | `#993C1D` | `#712B13` | `#4A1B0C` |

### Pink
| 50 | 100 | 200 | 400 | 600 | 800 | 900 |
|----|-----|-----|-----|-----|-----|-----|
| `#FBEAF0` | `#F4C0D1` | `#ED93B1` | `#D4537E` | `#993556` | `#72243E` | `#4B1528` |

### Gray (Neutral)
| 50 | 100 | 200 | 400 | 600 | 800 | 900 |
|----|-----|-----|-----|-----|-----|-----|
| `#F1EFE8` | `#D3D1C7` | `#B4B2A9` | `#888780` | `#5F5E5A` | `#444441` | `#2C2C2A` |

### Blue (Info)
| 50 | 100 | 200 | 400 | 600 | 800 | 900 |
|----|-----|-----|-----|-----|-----|-----|
| `#E6F1FB` | `#B5D4F4` | `#85B7EB` | `#378ADD` | `#185FA5` | `#0C447C` | `#042C53` |

### Green (Success)
| 50 | 100 | 200 | 400 | 600 | 800 | 900 |
|----|-----|-----|-----|-----|-----|-----|
| `#EAF3DE` | `#C0DD97` | `#97C459` | `#639922` | `#3B6D11` | `#27500A` | `#173404` |

### Amber (Warning)
| 50 | 100 | 200 | 400 | 600 | 800 | 900 |
|----|-----|-----|-----|-----|-----|-----|
| `#FAEEDA` | `#FAC775` | `#EF9F27` | `#BA7517` | `#854F0B` | `#633806` | `#412402` |

### Red (Danger / Error)
| 50 | 100 | 200 | 400 | 600 | 800 | 900 |
|----|-----|-----|-----|-----|-----|-----|
| `#FCEBEB` | `#F7C1C1` | `#F09595` | `#E24B4A` | `#A32D2D` | `#791F1F` | `#501313` |

---

## Light vs Dark Mode — Stop Mapping

| Mode | Fill | Stroke/Border | Title Text | Subtitle Text |
|------|------|--------------|------------|---------------|
| Light | Stop 50 | Stop 600 | Stop 800 | Stop 600 |
| Dark | Stop 800 | Stop 200 | Stop 100 | Stop 200 |

> **Text on colored backgrounds:** Always use stop **800 or 900** from the same ramp as the fill. Never use plain black or generic gray on a colored fill.

---

## Ready-to-Use CSS Variables

```css
:root {
  /* Backgrounds */
  --color-bg-primary:   #FFFFFF;
  --color-bg-secondary: #F8F8F7;
  --color-bg-tertiary:  #F1EFE8;
  --color-bg-info:      #E6F1FB;
  --color-bg-success:   #EAF3DE;
  --color-bg-warning:   #FAEEDA;
  --color-bg-danger:    #FCEBEB;

  /* Text */
  --color-text-primary:   #2C2C2A;
  --color-text-secondary: #5F5E5A;
  --color-text-tertiary:  #888780;
  --color-text-info:      #0C447C;
  --color-text-success:   #27500A;
  --color-text-warning:   #633806;
  --color-text-danger:    #791F1F;

  /* Borders */
  --color-border-subtle:  rgba(0,0,0,0.10);
  --color-border-default: rgba(0,0,0,0.18);
  --color-border-strong:  rgba(0,0,0,0.30);
  --color-border-info:    #185FA5;
  --color-border-success: #3B6D11;
  --color-border-warning: #854F0B;
  --color-border-danger:  #A32D2D;
}

[data-theme="dark"] {
  --color-bg-primary:     #1A1A18;
  --color-bg-secondary:   #242422;
  --color-bg-tertiary:    #2C2C2A;
  --color-text-primary:   #F1EFE8;
  --color-text-secondary: #B4B2A9;
  --color-text-tertiary:  #888780;
}
```

---

## Token Naming Convention

```
color / {ramp} / {stop}
  e.g.  color/purple/50   →  #EEEDFE
        color/red/600     →  #A32D2D

semantic / {role} / {state}
  e.g.  semantic/text/primary
        semantic/background/danger
        semantic/border/info
        semantic/action/primary-hover
```

---

## WCAG Contrast Rules

| Standard | Ratio | When It Applies |
|----------|-------|----------------|
| AA — Body text (< 18 px / 14 px bold) | **4.5 : 1** | All normal-sized text |
| AA — Large text (≥ 18 px or ≥ 14 px bold) | **3.0 : 1** | Headings, large labels |
| AA — UI Components & Icons | **3.0 : 1** | Borders, icons, input fields |
| AAA — Body text | **7.0 : 1** | Highest accessibility level |

---

# SECTION 6 — UNIVERSAL CHEAT SHEET

| What | Value |
|------|-------|
| Phone design unit | pt (iOS) · dp (Android) |
| **Default canvas** | **390 × 844 pt/dp** |
| Safe area top (notch/island) | 44–60 pt/dp |
| Safe area top (no notch) | 20 pt/dp |
| Safe area bottom | 34 pt/dp |
| Side margin — mobile | 16 pt/dp |
| Asset export | @1x · @2x · @3x (+ @4x for top Android) |
| Min touch target — iOS | 44 × 44 pt |
| Min touch target — Android | 48 × 48 dp |
| Min touch target — Web | 44 × 44 px |
| Min gap between targets | 8 pt/dp/px |
| Spacing grid base | 8 pt/dp/px |
| Max content width — Web | 1280 px |
| WCAG AA body text | 4.5 : 1 |
| WCAG AA large text / UI | 3.0 : 1 |
| WCAG AAA body text | 7.0 : 1 |
| Thumb zone — natural reach | Bottom 30% → Primary CTAs |
| Thumb zone — stretch | Middle 35% → Secondary actions |
| Thumb zone — hard reach | Top 35% → Information only |
