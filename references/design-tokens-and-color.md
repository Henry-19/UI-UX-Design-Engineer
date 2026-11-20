# Design Tokens & Color Harmony Matrix

## 1. Multi-Tier Token Architecture

A robust token architecture decouples design decisions from hardcoded markup, enabling seamless theming (Light/Dark mode) and consistency across platforms.

### 1.1 Tier 1: Primitive Tokens (Global)
Raw values defined once. They describe *what* the value is, not *how* it is used.
```css
/* Color Primitives */
--color-slate-50: #f8fafc;
--color-slate-100: #f1f5f9;
--color-slate-200: #e2e8f0;
--color-slate-700: #334155;
--color-slate-900: #0f172a;

--color-teal-500: #14b8a6;
--color-teal-600: #0d9488;
--color-teal-700: #0f766e;

--color-rose-500: #f43f5e;
--color-emerald-500: #10b981;
--color-amber-500: #f59e0b;
```

### 1.2 Tier 2: Semantic Tokens (Systemic)
Context-aware tokens that carry functional meaning. Used in application components.
```css
:root {
  /* Surfaces */
  --surface-canvas: var(--color-slate-50);
  --surface-raised: #ffffff;
  --surface-overlay: #ffffff;
  --surface-subtle: var(--color-slate-100);

  /* Text & Icons */
  --text-primary: var(--color-slate-900);
  --text-secondary: var(--color-slate-700);
  --text-muted: #64748b;
  --text-inverse: #ffffff;

  /* Borders */
  --border-subtle: var(--color-slate-200);
  --border-strong: #cbd5e1;
  --border-focus: var(--color-teal-600);

  /* Actions & Status */
  --action-primary: var(--color-teal-600);
  --action-primary-hover: var(--color-teal-700);
  --status-success: var(--color-emerald-500);
  --status-warning: var(--color-amber-500);
  --status-danger: var(--color-rose-500);
}

/* Dark Mode Overrides */
[data-theme="dark"] {
  --surface-canvas: #090d16;
  --surface-raised: #0f172a;
  --surface-overlay: #1e293b;
  --surface-subtle: #141e33;

  --text-primary: #f8fafc;
  --text-secondary: #94a3b8;
  --text-muted: #64748b;
  --text-inverse: #0f172a;

  --border-subtle: #1e293b;
  --border-strong: #334155;
  --border-focus: #2dd4bf;
}
```

---

## 2. Industry Color Harmony Palettes

Choose high-intention color pairings rather than default bootstrap colors:

| Domain | Base Background | Text Primary | Primary Accent | Secondary Neutral | Mood & Effect |
|---|---|---|---|---|---|
| **Education & Learning** | Soft Linen (`#FBFBFA`) | Deep Ink (`#1E2022`) | Teal / Cyan (`#0D9488`) | Warm Sand (`#F0EFEA`) | Inspiring, focused, calm, low eye strain |
| **Fintech & Security** | Cool Glacier (`#F8FAFC`) | Midnight Navy (`#0B132B`) | Deep Cobalt (`#1D4ED8`) | Slate Mist (`#E2E8F0`) | Authoritative, secure, dependable |
| **Developer Tools** | Deep Void (`#0D1117`) | Clean White (`#F0F6FC`) | Vibrant Amber / Coral (`#F778BA` / `#E3B341`) | Charcoal Wire (`#30363D`) | High density, crisp legibility, syntax pop |
| **Health & Wellness** | Clean Sage (`#F7F9F6`) | Forest Charcoal (`#1B281B`) | Botanical Green (`#15803D`) | Muted Moss (`#E5ECE3`) | Organic, healing, trustworthy |
| **Creative / Portfolio** | Pure Monochrome (`#000000` / `#FFFFFF`) | Inverted Strict | Single Electrified Accent (Neon Lime / Acid Yellow) | Stark Thin Hairlines (`#E5E5E5`) | High-fashion, avant-garde, bold |

---

## 3. WCAG 2.1 Contrast Standards & Accessibility Rules

All UI elements must pass mathematical contrast ratios calculated using relative luminance:

$$\text{Contrast Ratio} = \frac{L_1 + 0.05}{L_2 + 0.05}$$

### Contrast Benchmarks:
1. **WCAG AA Body & Normal Text (< 18pt regular or < 14pt bold):**
   - Minimum ratio: **4.5:1** against underlying surface.
2. **WCAG AA Large Text (>= 18pt regular or >= 14pt bold):**
   - Minimum ratio: **3.0:1** against underlying surface.
3. **UI Components & Graphical Objects:**
   - Active form borders, icons that convey status, and focus rings: **3.0:1** against adjacent background.
4. **Enhanced WCAG AAA (Recommended for long-form reading & dashboards):**
   - Normal text: **7.0:1**
   - Large text: **4.5:1**
