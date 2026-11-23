# UI/UX Design Engineer Skill (Elite Edition)

[![GitHub Stars](https://img.shields.io/github/stars/Henry-19/UI-UX-Design-Engineer?style=for-the-badge&logo=github)](https://github.com/Henry-19/UI-UX-Design-Engineer)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](https://opensource.org/licenses/MIT)
[![skills.sh](https://img.shields.io/badge/skills.sh-Compatible-0a0a0a.svg?style=for-the-badge)](https://skills.sh)

A comprehensive Agent Skill designed for AI Coding Agents (Antigravity, Claude Code, Cursor, Copilot, Windsurf) to elevate user experience, eliminate generic cookie-cutter interfaces ("AI Slop"), and automate production-grade Design System standards.

## ⚡ Quick Install

```bash
npx skills add Henry-19/UI-UX-Design-Engineer -g
```

---

## 1. Provenance & Synthesis from Leading Industry Repositories

This skill synthesizes and distills the strengths of premier UI/UX agent skills on GitHub:

| Repository / Source | Core Strengths | Limitations & Gaps | Contribution to this Skill |
|---|---|---|---|
| **`anthropics/skills`** (`frontend-design`) | • Exceptional "Anti-AI-Slop" mindset<br>• Prompts agent as Design Director<br>• Avoids cliche pastel gradient palettes | • Qualitative only; lacks mathematical token scales<br>• Lacks concrete WCAG a11y specifications<br>• No standardized 5 screen states | Adopted the **Bespoke Design Persona** philosophy and the AI cliche purge rules (see `references/anti-slop-guidelines.md`). |
| **`nextlevelbuilder/ui-ux-pro-max-skill`** | • Rich database of color palettes and font pairings<br>• Covers diverse stacks (React, Vue, SwiftUI) | • Bulky token footprint; context-heavy<br>• Lacks micro-interaction physics<br>• High dependency on external lookup tables | Distilled core **Color Harmony Matrices** and **Typography Scales**, optimized for context window efficiency. |
| **`wshobson/agents`** (`design-system-patterns`) | • Strict 3-Tier Design Token architecture (Primitive, Semantic, Component)<br>• Strong CSS custom properties support | • Heavily CSS-centric, lacks UX perspectives<br>• Does not address cognitive load or user mental models | Adopted the **3-Tier Token Architecture** and the **60-30-10** color distribution rule. |
| **`uxuiprinciples/agent-skills`** | • Thorough interface verification checklist | • Post-flight audit only; lacks generative design guidance | Integrated into the **Pre-flight Design Audit Checklist** (15 criteria). |

---

## 2. Directory Structure

```
D:\SkillAgent\UI-UX-Design-Engineer\
├── SKILL.md                                 # Primary skill instructions for AI Agents
├── README.md                                # Architecture overview and documentation
├── references/
│   ├── anti-slop-guidelines.md              # Anti-cliche standards & brand archetype styling
│   ├── design-tokens-and-color.md           # 3-tier token architecture, palettes & WCAG ratios
│   ├── typography-and-spacing.md            # Typographic scales (1.200) & 8pt/4pt spatial rhythm
│   └── interaction-and-states.md            # Mandatory 5 screen states & spring motion curves
└── checklists/
    └── preflight-design-audit.md            # 15-point pre-flight interface audit rubric
```

---

## 3. Installation & Usage

### For Google Antigravity / Claude Code
Copy or link the folder into your project's skill directory:
```bash
# Workspace-specific installation:
cp -r D:\SkillAgent\UI-UX-Design-Engineer .github/skills/ui-ux-design-engineer
# Or Claude Code:
cp -r D:\SkillAgent\UI-UX-Design-Engineer .claude/skills/
```

### For Cursor / Windsurf
Add to your `.cursorrules` or `.windsurfrules`:
```markdown
Always adhere to the UI/UX Design Engineer Skill located at D:\SkillAgent\UI-UX-Design-Engineer\SKILL.md.
Never output generic AI templates or low-contrast text. Enforce 5 screen states and WCAG AA compliance.
```

---

## 4. Core Invariants

1. **Anti-Slop First:** Never use repetitive gradient heroes, floating card soup, or washed-out gray text on white canvas.
2. **5 Mandatory Screen States:** Every view and component must explicitly account for: *Ideal (rich data), Loading (geometric skeletons), Empty (actionable and encouraging), Error (human-readable + retry CTA), Degraded (graceful partial failure).*
3. **WCAG 2.1 AA:** Minimum text contrast 4.5:1. Minimum touch target 44x44px. Full keyboard Tab order and visible `:focus-visible`.
4. **Motion Ergonomics:** Always include `@media (prefers-reduced-motion: reduce)` fallbacks for all transitions and keyframe animations.
