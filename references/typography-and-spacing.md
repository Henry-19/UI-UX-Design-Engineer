# Typography Scale & Spacing System

## 1. Mathematical Typography Scales

Never guess font sizes arbitrarily (e.g. jumping randomly between 15px, 21px, 27px). Stick strictly to a geometric typographic scale based on a constant ratio ($r$).

### 1.1 The Minor Third Scale (Ratio: 1.200) - Recommended for Applications
Best for web apps, productivity tools, and control panels where space efficiency and clean hierarchy are vital:

| Token Name | Size (px) | Size (rem) | Typical Usage | Line Height | Letter Spacing |
|---|---|---|---|---|---|
| `text-caption` | 11.1px / 11px | 0.694rem | Timestamps, badge labels, legal microcopy | 1.35 | +0.02em |
| `text-sm` | 13.3px / 13px | 0.833rem | Secondary labels, table data cells, tooltips | 1.45 | 0 |
| `text-base` | 16.0px / 16px | 1.000rem | Primary body text, input fields, standard buttons | 1.55 | -0.011em |
| `text-md` | 19.2px / 19px | 1.200rem | Card titles, modal headers, subsection headers | 1.35 | -0.015em |
| `text-lg` | 23.0px / 23px | 1.440rem | Major section title (H3), dialog headers | 1.25 | -0.020em |
| `text-xl` | 27.6px / 28px | 1.728rem | Page headers (H2), dashboard view titles | 1.20 | -0.022em |
| `text-2xl` | 33.2px / 33px | 2.074rem | Main page title (H1), primary hero title | 1.15 | -0.025em |

---

## 2. Professional Font Pairings Matrix

Pair a distinctive heading font with an ultra-legible workhorse body font:

| Style / Persona | Heading Font | Body Font | Monospace Font | Why It Works |
|---|---|---|---|---|
| **Clean Tech & Product** | Inter / Geist | Inter / Geist | JetBrains Mono | Unified optical weights, tall x-height, neutral tone |
| **Editorial & Deep Work** | Newsreader / Fraunces | Plus Jakarta Sans | Fira Code | Warm serif elegance paired with contemporary legible sans |
| **High Precision / Modern** | Plus Jakarta Sans | Source Sans 3 | IBM Plex Mono | High clarity in dense tabular layouts and numerical data |
| **Friendly & Human** | Outfit / Manrope | DM Sans | Space Mono | Rounded geometric structure without feeling childish |

---

## 3. Spatial System: 8-Point Grid with 4-Point Subgrid

Interfaces should be built on an 8pt spatial grid to ensure mathematical alignment across varied screen sizes and densities.

### 3.1 Spacing Scale Reference
```
4px   (space-1): Micro-gaps (badge padding, icon-text gap)
8px   (space-2): Compact padding (small buttons, table cell vertical padding)
12px  (space-3): Balanced gaps (tight list items, form field label offset)
16px  (space-4): Standard baseline (card inner padding, horizontal input padding)
24px  (space-6): Component grouping (gap between form groups, card grid gap)
32px  (space-8): Structural separation (sidebar padding, modal margins)
48px  (space-12): Section vertical spacing on tablets
64px  (space-16): Major page section breaks on desktop
```

### 3.2 Responsive Breakpoints & Gutters
- **Mobile (< 640px):** Single column, 16px outer margin, touch target >= 44x44px.
- **Tablet (640px - 1024px):** 2-column or collapsable side nav, 24px outer margin.
- **Desktop (>= 1024px):** Fixed or responsive side navigation, max-width container (`1200px` - `1440px`), 32px outer margin.
- **Ultra-wide (> 1536px):** Constrain readable content width to prevent endless line lengths (maximum 75-80 characters per line).
