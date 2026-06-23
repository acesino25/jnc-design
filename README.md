# JNC Design Compass

A universal design system guide and AI prompt toolkit, synthesized from 20+ world-class design systems (Material Design, Apple HIG, Atlassian, Shopify Polaris, GitHub Primer, IBM Carbon, Microsoft Fluent, Adobe React Aria, and more).

Use it as a reference, paste it into any AI as a system prompt, or call individual sub-tool prompts for specific design tasks.

---

## What's Inside

```
jnc-design/
├── README.md                   ← You are here
├── DESIGN_COMPASS.md           ← Full reference guide (all principles)
└── prompts/
    ├── MASTER_SYSTEM_PROMPT.md ← Paste into any AI to activate the full Compass
    ├── 01-foundations.md       ← Design tokens, grid, color, type, icons, hierarchy
    ├── 02-components.md        ← Component architecture, affordances, states, API design
    ├── 03-accessibility.md     ← Inclusive design and WCAG compliance
    ├── 04-voice-tone.md        ← UX copy and content guidelines
    ├── 05-motion.md            ← Animation, micro interactions, emotional design
    ├── 06-cross-platform.md    ← Web, iOS, Android, React Native
    ├── 07-context-adapters.md  ← Industry-specific guidance
    ├── 08-governance.md        ← Running a design system as a product
    └── 09-visual-craft.md      ← Affordances, hierarchy, shadows, overlays, dark mode
```

---

## Quick Start

### Option A — Full Compass (any AI)

1. Open `prompts/MASTER_SYSTEM_PROMPT.md`
2. Copy the entire contents
3. Paste as the **system prompt** (or first message) in any AI chat
4. Ask your design question naturally

### Option B — Single Sub-Tool

1. Pick the prompt file that matches your task (e.g., `03-accessibility.md`)
2. Copy its contents
3. Paste as context before your question

### Option C — Reference Only

Read `DESIGN_COMPASS.md` directly as a design reference without AI.

---

## Sub-Tools at a Glance

| File | Sub-Tool | Use It For |
|---|---|---|
| `01-foundations.md` | Foundations Forge | Tokens, grid, color, type, shadows, hierarchy |
| `02-components.md` | Component Architect | Components, affordances, states, API design |
| `03-accessibility.md` | Accessibility Blueprint | WCAG, ARIA, keyboard, screen readers |
| `04-voice-tone.md` | Voice & Tone Studio | UX copy, error messages, empty states |
| `05-motion.md` | Motion Playbook | Animations, micro interactions, emotional design |
| `06-cross-platform.md` | Cross-Platform Mapper | Web + mobile + native decisions |
| `07-context-adapters.md` | Context Adapters | Enterprise, consumer, gov, fintech, dev tools |
| `08-governance.md` | Governance Engine | Design system ops, versioning, contribution |
| `09-visual-craft.md` | Visual Craft | Affordances, hierarchy, shadows, overlays, dark mode |

---

## Sources

**Design Systems (direct exploration):**
Material Design 3 · Apple HIG · Atlassian · Shopify Polaris · GitHub Primer · GitLab Pajamas · IBM Carbon · Microsoft Fluent 2 · Elastic UI · Adobe React Aria · Radix UI · Zag.js · Semantic UI · Evergreen · Tamagui · AgnosticUI · Thumbprint · GOV.UK · Gestalt (Pinterest) · BBC GEL · and 100+ systems catalogued by Adele (UXPin) and Design System Repo.

**Applied UI/UX Theory (Sub-Tool 9):**
UI/UX Concept — 11 conceptos visuales fundamentales: Affordances & Signifiers · Visual Hierarchy · Grids & Spacing · Typography & Font Sizing · Color Theory · Dark Mode · Shadows · Icons & Buttons · Feedback & States · Micro Interactions · Overlays.

**Aggregated from:** [awesome-styleguides](https://github.com/streamich/awesome-styleguides)
