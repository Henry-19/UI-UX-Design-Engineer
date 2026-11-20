# Interaction Mechanics & The 5 Core Screen States

## 1. Deep Dive: The 5 Essential Screen States

A production UI is defined by how it handles edge cases and transitions, not just its perfect populated state.

```
       ┌──────────────┐
       │   INITIAL    │
       └──────┬───────┘
              │ fetch()
              ▼
       ┌──────────────┐
       │   LOADING    │  ───► Skeleton screens matching layout geometry
       └──────┬───────┘
              │
       ┌──────┴──────────────────────────┐
       │                                 │
[Data > 0]                        [Error Encountered]
       ▼                                 ▼
┌──────────────┐                  ┌──────────────┐
│  IDEAL STATE │                  │  ERROR STATE │
└──────┬───────┘                  └──────┬───────┘
       │                                 │ Retry
[Data = 0]                               ▼
       ▼                          ┌──────────────┐
┌──────────────┐                  │   RECOVERY   │
│ EMPTY STATE  │                  └──────────────┘
└──────────────┘
```

### 1.1 Ideal State
- **Real-world edge cases:** Always test names with 30+ characters, non-ASCII characters, and variable badge counts.
- **Data formatting:** Use localized numbers (`Intl.NumberFormat`), relative time with full date tooltips, and clear unit suffixes.
- **Actionability:** Hover/focus states reveal secondary actions (copy ID, pin, delete) without cluttering the resting state.

### 1.2 Loading State (Skeleton Screens)
- **Geometry Match:** Skeletons must mirror the exact dimensions (height, width, border-radius) of the rendered content.
- **Pulse Animation:** Subtle opacity pulse (`0.6` to `1.0`) over `1.5s ease-in-out`. Avoid harsh white shimmering sweeps on dark backgrounds.
- **Progressive Hydration:** Render navigation and page headers immediately while async tables or feeds hydrate.

### 1.3 Empty State
- **Three Core Elements:**
  1. Contextual illustration or high-clarity icon (not an arbitrary doodle).
  2. Clear, empathetic heading ("Chưa có bài tập nào được tạo").
  3. Actionable next step with an immediate CTA ("Tạo bài tập đầu tiên").
- **Educational Value:** Mention what benefits occur once the user completes the action.

### 1.4 Error State
- **User-Centric Messaging:** Never dump raw SQL, stack traces, or `500 Internal Server Error` to the user.
- **Clear Explanation:** Say what went wrong in plain human language ("Không thể tải danh sách học sinh do mất kết nối mạng").
- **Recovery Pathway:** Always provide an immediate recovery mechanism:
  - Primary button: "Thử lại ngay" (calls re-fetch).
  - Secondary link: "Kiểm tra trạng thái hệ thống" or "Liên hệ hỗ trợ".
  - Collapsible accordion for technical details (error code, trace ID for support tickets).

### 1.5 Degraded / Partial State
- If secondary widgets (e.g. analytics chart) fail while primary widgets (e.g. active student list) succeed, display an inline alert card inside the failed widget instead of crashing or blocking the entire screen.

---

## 2. Micro-Interactions & Spring Physics

### 2.1 CSS Transition Curves
Avoid linear transitions for UI elements. Use deceleration curves for entering elements and acceleration curves for exiting elements:

```css
:root {
  /* Natural Spring Bezier */
  --ease-spring: cubic-bezier(0.16, 1, 0.3, 1);
  --ease-out-quad: cubic-bezier(0.25, 0.46, 0.45, 0.94);
  --ease-in-out-cubic: cubic-bezier(0.65, 0, 0.35, 1);
}

/* Button Micro-Feedback */
.btn-interactive {
  transition: transform 120ms var(--ease-spring),
              background-color 150ms ease-out,
              box-shadow 150ms ease-out;
}

.btn-interactive:hover {
  transform: translateY(-1px);
}

.btn-interactive:active {
  transform: translateY(1px) scale(0.98);
}
```

### 2.2 Accessible Focus Rings
Never hide focus outlines for keyboard users. Use a distinct, offset focus ring:
```css
*:focus-visible {
  outline: 2px solid var(--border-focus);
  outline-offset: 2px;
}
```

### 2.3 Reduced-Motion Compliance
Always include media queries to respect user OS accessibility preferences:
```css
@media (prefers-reduced-motion: reduce) {
  *,
  *::before,
  *::after {
    animation-duration: 0.01ms !important;
    animation-iteration-count: 1 !important;
    transition-duration: 0.01ms !important;
    scroll-behavior: auto !important;
  }
}
```
