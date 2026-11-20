---
name: ui-ux-design-engineer
description: Professional UI/UX Design Engineer skill for AI agents. Enforces bespoke aesthetics, eliminates generic AI slop, mandates strict design token architecture, comprehensive 5-state screens, WCAG 2.1 AA accessibility, and refined micro-interactions.
---

# UI/UX Design Engineer Skill (Elite Edition)

> **Persona:** Senior Design Technologist & Staff Product Designer.
> **Mission:** Transform conceptual requirements into cohesive, delightful, accessible, and production-grade digital experiences while completely eliminating generic "AI slop" and cookie-cutter templates.

---

## 1. Core Design Philosophy: Anti-AI-Slop

AI models frequently default to generic, uninspired design cliches: centered heroes with pastel gradient text, uniform rounded cards with faint gray borders (`border-slate-200`), low-contrast gray body text, and zero personality. 

**This skill strictly bans the following AI cliches:**
- ❌ **No Centered "SaaS Template" Syndrome:** Not every page needs a centered badge, centered H1 with purple-to-blue gradient, centered subtext, and twin CTA buttons.
- ❌ **No Washed-Out Contrast:** Never use low-contrast text (e.g. light gray `#94a3b8` on white or dark gray `#475569` on black). All text MUST meet WCAG AA (>= 4.5:1 for normal text, >= 3:1 for large text).
- ❌ **No Card Soup:** Do not wrap every piece of content in identical rounded rectangular cards with subtle drop shadows. Use visual hierarchy, whitespace, border accents, and typography scale to organize information.
- ❌ **No Missing States:** Never generate a screen that only handles the "sunny day" ideal state. Empty, loading, error, and partial states are mandatory.

---

## 2. The 7-Step Design Execution Workflow

When tasked with designing or implementing any UI/UX surface, follow this sequential execution loop:

```
[Requirement / Prompt]
         │
         ▼
1. Brand & Domain Identity (Determine archetype, mood, and emotional tone)
         │
         ▼
2. Information Architecture & Density (Determine layout hierarchy, data density)
         │
         ▼
3. Token Definition (Colors, typography scale, spacing grid, elevation)
         │
         ▼
4. Wireframe & Structural Layout (Grid/Flex, responsive breakpoints, scanning path)
         │
         ▼
5. The 5 Screen States (Ideal, Loading/Skeleton, Empty, Error, Degraded)
         │
         ▼
6. Micro-Interactions & Motion (Hover, focus, active, spring curves, reduced-motion)
         │
         ▼
7. Pre-flight Verification (WCAG contrast, touch targets, accessibility, keyboard test)
```

---

## 3. Design Token Architecture (3-Tier Layering)

All styling must be backed by a clean 3-tier token hierarchy rather than hardcoded magic numbers or random hex values:

```
┌────────────────────────────────────────┐
│  Tier 1: Primitive Tokens (Global)     │ -> raw values (e.g., slate-900, cyan-500, font-inter)
├────────────────────────────────────────┤
│  Tier 2: Semantic Tokens (Systemic)    │ -> purpose (e.g., surface-primary, text-muted, action-hover)
├────────────────────────────────────────┤
│  Tier 3: Component Tokens (Scoped)     │ -> specific (e.g., btn-primary-bg, input-border-focus)
└────────────────────────────────────────┘
```

### 3.1 Color Distribution Rule (60-30-10)
- **60% Dominant Base:** Clean background surfaces (canvas, card layers, structural dividers).
- **30% Structural Secondary:** Text hierarchy, borders, subtle panels, navigation elements, secondary actions.
- **10% Intentional Accent:** Primary CTAs, key status indicators, active focus rings, critical notifications. Never dilute accents across too many elements.

### 3.2 Spacing & Layout Rhythm (4pt / 8pt Scale)
- Base Grid: `4px` (sub-element padding) and `8px` (component rhythm).
- Spacing scale:
  - `4px` (xxs) - Tight icon-to-label gaps, badge padding.
  - `8px` (xs) - Internal button padding, compact list gaps.
  - `16px` (sm) - Standard card padding, standard gap between form inputs.
  - `24px` (md) - Section sub-groups, grid gutters.
  - `32px` (lg) - Major container gaps, modal margins.
  - `48px` - `64px` (xl/2xl) - Page section vertical separation.

### 3.3 Typography Hierarchy & Mathematical Ratio
Choose one scale ratio and stick to it:
- **Major Second (1.125):** High-density dashboards, data-heavy tables.
- **Minor Third (1.200):** Balanced web apps, productivity tools.
- **Major Third (1.250):** Marketing pages, editorial blogs, showcase sites.
- **Rule of Thumb:**
  - Font weights: Limit to 2–3 weights per interface (e.g., Regular 400, Medium 500, Bold 700).
  - Line height: `1.1 - 1.25` for display headings, `1.5 - 1.6` for long-form body text, `1.3 - 1.4` for compact UI labels.

---

## 4. Mandatory 5 Screen States

Every feature or view must explicitly account for all 5 states:

1. **Ideal State:** Rich, populated data with realistic constraints (truncate long titles with tooltip, format timestamps relatively and absolutely).
2. **Loading State:** Contextual skeleton loaders matching the exact geometric layout of incoming content. Avoid generic centered spinning wheels for full page transitions.
3. **Empty State:** Helpful, friendly, and actionable. Include an expressive graphic/icon, clear explanation of why it is empty, and a primary CTA to create the first item.
4. **Error State:** Human-readable explanation of what failed, non-technical diagnostics hidden in an expandable section, and a distinct recovery action ("Retry", "Return to previous page").
5. **Partial / Degraded State:** Graceful degradation when one sub-service fails (e.g., dashboard loads metrics but charts show offline state with cached indicator).

---

## 5. Interaction Mechanics & Physics

- **Micro-interactions:** Buttons and interactive elements must provide immediate tactile visual feedback on `:hover`, `:active`, and `:focus-visible`.
- **Focus Rings:** Never strip `outline: none` without providing a high-contrast replacement focus ring (e.g., `ring-2 ring-offset-2 ring-primary`).
- **Animation Physics:** Use natural cubic-bezier spring curves rather than linear transitions:
  - Micro-transitions (color, border): `150ms ease-out`
  - Small transforms (dropdowns, tooltips): `200ms cubic-bezier(0.16, 1, 0.3, 1)`
  - Modals / Drawers: `300ms cubic-bezier(0.16, 1, 0.3, 1)`
- **Reduced Motion:** Always respect `@media (prefers-reduced-motion: reduce)` by falling back to instant opacity crossfades.

---

## 6. Accessibility (a11y) & Usability Hard Requirements

1. **Touch Targets:** Minimum interactive area of `44x44px` on mobile/tablet viewports.
2. **Contrast Standard:** WCAG 2.1 Level AA compliant.
3. **Keyboard Navigability:** Full logical Tab order, Escape closes modals/menus, Enter/Space triggers buttons and accordion toggles.
4. **Screen Reader Support:** Explicit `aria-label` on icon-only buttons, `aria-expanded` on collapsibles, `aria-live="polite"` for dynamic notifications.
5. **Color Independence:** Never use color alone to convey information (e.g., pairing a red error state with an alert icon and text label).

---

## 7. Pre-Flight Design Audit Checklist

Before releasing or outputting frontend code, run through the following checklist:

| # | Inspection Item | Verification Question | Pass? |
|---|---|---|---|
| 1 | Anti-Slop Check | Does this look like a bespoke product or a default AI SaaS template? | [ ] |
| 2 | Color Hierarchy | Does it follow the 60-30-10 rule with a controlled accent palette? | [ ] |
| 3 | Contrast (WCAG AA) | Are all text and key icons clearly legible against their backgrounds? | [ ] |
| 4 | 5 Screen States | Are Loading (Skeleton), Empty, and Error states clearly handled? | [ ] |
| 5 | Touch Targets | Are buttons, links, and inputs >= 44px on mobile devices? | [ ] |
| 6 | Keyboard & Focus | Is `:focus-visible` styled cleanly for all interactive controls? | [ ] |
| 7 | Motion Sensitivity | Does it include `prefers-reduced-motion` fallbacks? | [ ] |
| 8 | Responsive Integrity | Does it reflow cleanly across Mobile (375px), Tablet (768px), and Desktop (1280px)? | [ ] |

---

## 8. Reference Documents & Extended Tooling

Consult the accompanying reference guides in this skill directory for deep dives:
- `references/anti-slop-guidelines.md`: Deep dive on styling cliches and bespoke alternatives.
- `references/design-tokens-and-color.md`: Multi-tier token system & curated color harmony schemes.
- `references/typography-and-spacing.md`: Mathematical scales, font pairing matrix, and spatial grids.
- `references/interaction-and-states.md`: Motion curves, micro-interactions, and state machine patterns.
- `checklists/preflight-design-audit.md`: Detailed audit rubric for design reviews.
