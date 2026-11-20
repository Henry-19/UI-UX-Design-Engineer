# Pre-Flight UI/UX Design Audit Checklist

Use this checklist to perform a self-audit before shipping any UI component, page, or feature.

---

## 1. Visual Hierarchy & Aesthetic Integrity
- [ ] **Anti-Slop Validation:** Does this interface look distinct, purposeful, and free of generic AI clichés (such as unneeded gradient text, floating card soup, or centered SaaS templates)?
- [ ] **Color Discipline (60-30-10):** Is there a clear dominant background (60%), structural text/borders (30%), and a single focused accent color (10%)?
- [ ] **Typographic Consistency:** Are font sizes derived from a defined typographic scale (e.g. 1.200 Minor Third) rather than arbitrary pixel sizes?
- [ ] **Line-Length Control:** Is paragraph width constrained to 65–80 characters for optimal reading ergonomics?

---

## 2. Accessibility & Usability (WCAG 2.1 AA)
- [ ] **Contrast Compliance:** Does all standard text have at least 4.5:1 contrast against its background?
- [ ] **Large Text & Controls:** Do headings and input borders maintain at least 3.0:1 contrast?
- [ ] **Touch Target Size:** Are all interactive touch targets (buttons, links, icon toggles) at least 44x44 CSS pixels on mobile viewports?
- [ ] **Color Independence:** Is critical information conveyed through icons/labels in addition to color alone?
- [ ] **Keyboard Navigability:** Can a user navigate the entire flow using only Tab, Shift+Tab, Enter, Space, and Escape?
- [ ] **Focus Rings:** Is `:focus-visible` prominently visible with at least a 2px offset ring?

---

## 3. The 5 Essential Screen States
- [ ] **Ideal State:** Does the layout handle normal, overflowing, and edge-case content gracefully (e.g., long strings, internationalization)?
- [ ] **Loading State:** Are skeleton loaders tailored to the layout rather than an isolated generic spinner?
- [ ] **Empty State:** Does the empty screen provide an encouraging message and an immediate action button?
- [ ] **Error State:** Does the error screen provide human-readable text and a "Try Again" recovery action?
- [ ] **Degraded/Partial State:** If a sub-service fails, does the rest of the application remain functional?

---

## 4. Interaction, Responsiveness & Motion
- [ ] **Tactile Feedback:** Do buttons and inputs provide immediate feedback on `:hover`, `:active`, and `:focus`?
- [ ] **Motion Sensitivity:** Is `@media (prefers-reduced-motion: reduce)` respected across all animations and transitions?
- [ ] **Mobile & Tablet Reflow:** Does the interface adapt smoothly between 375px (mobile), 768px (tablet), and 1280px+ (desktop)?
