# Elite UX & UI Design Prompt Toolkit

> **15 production-ready design prompts** — each expanded with strategic context, dimension references, follow-up drills, and senior designer wisdom.
> Built for UX researchers, product designers, and front-end teams.

---

## About This Toolkit

This directory is a **standalone UX/UI resource** — completely separate from the AI PM Prompt Toolkit in `/prompts/`. You do not need to use both together. This toolkit is self-contained.

Each file contains:
1. **Strategic Context** — the design principle behind the prompt and why it matters
2. **Relevant Dimensions** — only the canvas sizes, safe zones, and color stops needed for *this specific prompt*
3. **The Enhanced Master Prompt** — ready to copy and paste into Claude, ChatGPT, or Gemini
4. **Follow-Up Prompts** — 2 drill-down prompts to push the output further
5. **Designer Wisdom** — tactical tips and tool recommendations from senior design practice

---

## Platform Key

| Tag | Meaning |
|-----|---------|
| 🖥️ Web | Desktop & laptop browsers |
| 📱 Phone | iOS & Android native apps |
| 🔀 Mix | Both platforms — platform-specific notes inside |

---

## Prompt Index

### 📐 Master Reference
| File | What's Inside |
|------|--------------|
| [00_master_dimensions_and_color_reference.md](./00_master_dimensions_and_color_reference.md) | Complete phone & web canvas sizes, safe areas, touch targets, spacing scale, typography scale, full 9-ramp color system, CSS tokens, thumb zone map, WCAG rules |

### 🔬 Research Prompts
| # | File | Category | Platform |
|---|------|----------|----------|
| 1 | [01_deep_user_interview_debrief.md](./01_deep_user_interview_debrief.md) | User Research | 🔀 Mix |
| 6 | [06_competitive_ux_teardown.md](./06_competitive_ux_teardown.md) | Competitive Analysis | 🔀 Mix |
| 13 | [13_usability_test_script_builder.md](./13_usability_test_script_builder.md) | User Testing | 🔀 Mix |

### 🗺️ Information Architecture & Flow
| # | File | Category | Platform |
|---|------|----------|----------|
| 2 | [02_sitemap_navigation_audit.md](./02_sitemap_navigation_audit.md) | IA | 🖥️ Web |
| 5 | [05_user_flow_for_onboarding.md](./05_user_flow_for_onboarding.md) | Flow Design | 🔀 Mix |
| 10 | [10_jobs_to_be_done_feature_map.md](./10_jobs_to_be_done_feature_map.md) | Product Strategy | 🔀 Mix |

### 📱 Mobile-First
| # | File | Category | Platform |
|---|------|----------|----------|
| 3 | [03_thumb_zone_interaction_redesign.md](./03_thumb_zone_interaction_redesign.md) | Mobile UX | 📱 Phone |
| 7 | [07_micro_interaction_spec_writer.md](./07_micro_interaction_spec_writer.md) | Motion & Interaction | 📱 Phone |
| 11 | [11_touch_target_tap_error_audit.md](./11_touch_target_tap_error_audit.md) | Mobile Usability | 📱 Phone |

### 🎨 Visual Design
| # | File | Category | Platform |
|---|------|----------|----------|
| 4 | [04_visual_hierarchy_score_and_fix.md](./04_visual_hierarchy_score_and_fix.md) | Visual Design | 🔀 Mix |
| 8 | [08_colour_system_accessibility_audit.md](./08_colour_system_accessibility_audit.md) | Accessibility | 🔀 Mix |
| 12 | [12_dark_mode_token_generator.md](./12_dark_mode_token_generator.md) | Design Systems | 🔀 Mix |

### ✅ Polish & Handoff
| # | File | Category | Platform |
|---|------|----------|----------|
| 9 | [09_microcopy_empty_state_writer.md](./09_microcopy_empty_state_writer.md) | UX Writing | 🔀 Mix |
| 14 | [14_design_qa_checklist_generator.md](./14_design_qa_checklist_generator.md) | QA & Handoff | 🔀 Mix |
| 15 | [15_design_critique_facilitator.md](./15_design_critique_facilitator.md) | Team Collaboration | 🔀 Mix |

---

## Quick Start

1. Open the file for your current design task.
2. Read the **Relevant Dimensions** section to set your design frame correctly.
3. Copy the **Master Prompt**, replace `[BRACKETED]` placeholders, and paste into your LLM.
4. Use the **Follow-Up Prompts** to push the output into a developer-ready deliverable.
5. Reference [00_master_dimensions_and_color_reference.md](./00_master_dimensions_and_color_reference.md) as your single source of truth for all numbers.

---

## The 3 Golden Rules (Always Active)

1. **Design at 390 × 844 pt/dp.** Test at 320 (small) and 430 (large). If it works at both extremes, it works everywhere.
2. **Every spacing value is a multiple of 8.** Use 4 only for micro-gaps.
3. **Color encodes meaning, not sequence.** Red = Error. Amber = Warning. Green = Success. Blue = Info. Always. No exceptions.
