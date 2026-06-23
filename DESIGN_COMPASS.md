# THE DESIGN COMPASS
### A Universal Design System Guide — Synthesized from 20+ World-Class Sources

> Distilled from: Material Design, Apple HIG, Atlassian, Shopify Polaris, GitHub Primer, GitLab Pajamas, IBM Carbon, Microsoft Fluent, Elastic UI, Adobe React Aria, Radix UI, Zag.js, Semantic UI, Evergreen, Tamagui, AgnosticUI, Thumbprint, Gestalt (Pinterest), Duolingo, and cross-industry analysis of 100+ systems (Adele, Design System Repo).

---

## How to Use This Compass

This guide is divided into **8 Sub-Tools**, each targeting a distinct phase or angle of design work. Use them independently or in combination.

| Sub-Tool | Best For |
|---|---|
| [1. Foundations Forge](#1-foundations-forge) | Starting from scratch — tokens, grid, color, type |
| [2. Component Architect](#2-component-architect) | Building reusable UI components |
| [3. Accessibility Blueprint](#3-accessibility-blueprint) | Making everything inclusive |
| [4. Voice & Tone Studio](#4-voice--tone-studio) | Writing UX copy and content guidelines |
| [5. Motion Playbook](#5-motion-playbook) | Animation, transitions, micro-interactions |
| [6. Cross-Platform Mapper](#6-cross-platform-mapper) | Designing for web, mobile, native simultaneously |
| [7. Context Adapters](#7-context-adapters) | Adapting principles by industry/product type |
| [8. Governance Engine](#8-governance-engine) | Running and scaling a design system as a product |

---

## 1. Foundations Forge
> *Use when: Starting a new design system, auditing existing foundations, establishing design tokens.*

### 1.1 Design Tokens — The Single Source of Truth

Design tokens are named values that represent visual decisions (color, spacing, typography, radius, shadow, motion). They are the most important primitive in a scalable system.

**Token Hierarchy (3 Layers)**
```
Global (Raw)  →  Semantic (Alias)  →  Component (Specific)
--color-blue-500  →  --color-action  →  --button-background
```

- **Global tokens**: Raw values. Never used directly in components (`#3B82F6`, `16px`).
- **Semantic tokens**: Context-named aliases (`--color-action`, `--color-danger`, `--color-success`). This layer is what components consume.
- **Component tokens**: Scoped to a specific component (`--button-primary-bg`, `--card-border-radius`). Use sparingly.

**Lessons from the systems:**
- *Atlassian*: Semantic naming (accent, warning, danger, disabled) enables dark mode and theme switches without touching component code.
- *Thumbprint*: Export tokens to SCSS, JS, iOS (Swift), and Android (XML) from a single source — never duplicate values across platforms.
- *GitLab Pajamas*: Token documentation should include "authoring," "reading," and "usage" guides — three perspectives for three audiences.
- *IBM Carbon*: All token values are multiples of a base unit (8px). Nothing arbitrary.

**Token Naming Convention:**
```
{category}-{variant}-{state}
color-action-hover
color-feedback-danger-default
space-layout-xl
```

---

### 1.2 Grid & Spacing

**The 8-Point Grid (Universal)**
All spacing values are multiples of 8: `4, 8, 16, 24, 32, 40, 48, 64, 80, 96`.
Use 4 for micro-adjustments (icon padding, internal button spacing).

**IBM's 2x Grid Concept**
IBM Carbon uses a grid where all dimensions divide cleanly by 2. This creates proportional harmony at every breakpoint and reduces arbitrary decisions to near-zero.

**Layout Zones (Apple HIG)**
- **Safe Areas**: Content must respect notches, home indicators, and rounded corners. Reserve inner safe zones for primary interaction.
- **Content Margins**: Consistent horizontal padding that scales with screen width, not a fixed pixel value.

**Spacing Scale Template:**
```
xs:  4px   — Icon gaps, input internal padding
sm:  8px   — Tight element groupings
md:  16px  — Standard content spacing
lg:  24px  — Section padding, card gaps
xl:  32px  — Major layout sections
2xl: 48px  — Page-level breathing room
3xl: 64px+ — Hero areas, large breakpoints
```

---

### 1.3 Color System

**The 5-Tier Color Architecture**
```
Brand     — Core identity colors (primary, secondary)
Neutral   — Grays, backgrounds, surfaces
Semantic  — Success, warning, danger, info
Data      — Chart palettes, sequential/divergent scales
Interactive — Focus rings, hover states, pressed states
```

**Lessons from the systems:**
- *Material Design 3*: **Dynamic Color** generates a harmonious palette from a single seed color using the HCT color space (Hue, Chroma, Tone). The entire UI palette can be derived programmatically from a user's wallpaper.
- *Atlassian*: Never define color by hue alone — define it by semantic role. The same blue that represents "action" should never represent "warning."
- *Apple HIG*: Semantic system colors (`systemBlue`, `systemRed`) adapt automatically to dark mode, high contrast, and color blindness modes.
- *Government systems (GOV.UK, USWDS)*: Start with accessibility constraints. Define your palette inside WCAG AA/AAA contrast ratios, not the other way around.

**Dark Mode Strategy:**
- Don't invert light mode. Dark mode is a separate surface-level system.
- Light mode: white backgrounds, colored accents.
- Dark mode: near-black surfaces with desaturated/lightened accents.
- Use semantic tokens as the switch layer — the component never changes, only the token values do.

**Color Roles:**
```
Surface       — Background of any element
On-Surface    — Content placed on surface
Container     — Filled element backgrounds (chips, cards)
On-Container  — Content inside containers
Outline       — Borders and dividers
```

---

### 1.4 Typography

**Type Scale — Ratio-Based**
Use a modular scale (Major Third: 1.250, Perfect Fourth: 1.333, Major Second: 1.125 for dense UIs).

```
Display  — Hero text, large numbers (40-72px)
Headline — Page/section titles (24-36px)
Title    — Card and component headers (18-22px)
Body     — Reading content (14-16px)
Label    — UI labels, captions (11-13px)
Code     — Monospace (match body size)
```

**Lessons from the systems:**
- *Apple HIG*: Use **Dynamic Type** — text scales with user accessibility preferences, not viewport. Design with relative units (`em`, `rem`), never `px` for type.
- *IBM Carbon*: Type is functional, not decorative. Every type style has a clear purpose — never use heading styles for visual effect alone.
- *Semantic UI*: "Plurality and word order link concepts intuitively." Type sizes should communicate hierarchy through relationship, not just size alone — use weight, spacing, and color to reinforce it.
- *Material Design*: Pair a display font (expressive) with a body font (readable). They should contrast in personality but share proportional harmony.

**Line Length Rule:**
Optimal reading length is 45–75 characters per line. Never let prose content span full-width on large screens.

---

### 1.5 Iconography

- **SVG over icon fonts** — Every major modern system (Shopify, GitHub, IBM, Elastic) has migrated to SVG. Icon fonts have accessibility issues, render inconsistently, and block text rendering.
- **Grid discipline** — Design icons on a consistent artboard (24×24px standard). Use a consistent padding zone (2px inner padding for breathing room).
- **Semantic naming** — Icons should be named by meaning, not appearance. `icon-delete`, not `icon-trash`. `icon-add-user`, not `icon-person-plus`.
- **Two-weight system** — Offer `outlined` (default, lighter) and `filled` (selected state, emphasis). Never mix weights within a single context.
- *GitHub Primer*: Octicons are a standalone package — keep your icon library independently versioned and deployable.
- *GitLab Pajamas*: Support **animated icons** for state transitions (loading spinner, checkmark reveal). Animation should confirm action completion, not decorate.

---

## 2. Component Architect
> *Use when: Designing or building reusable UI components — from buttons to complex patterns.*

### 2.1 The Component Tier Model

```
Primitives    — Raw HTML elements + ARIA roles (div, button, input)
     ↓
Atoms         — Smallest styled units (Button, Badge, Avatar, Icon)
     ↓
Molecules     — Composed atoms (InputField = Label + Input + Error)
     ↓
Organisms     — Feature-level components (DataTable, NavigationBar)
     ↓
Patterns      — Multi-organism layouts (EmptyState, PageHeader, Form)
     ↓
Templates     — Full page scaffolds (DashboardLayout, AuthLayout)
```

### 2.2 Architecture Philosophies — Choose One

**Option A: Styled Components (Evergreen, Material UI)**
Full styling + behavior bundled. Fast to use, opinionated visually. Best for teams that want uniformity over customization.

**Option B: Headless / Behavior-Only (Radix UI, Adobe React Aria, Zag.js)**
Logic and accessibility without styles. Maximum design freedom. Best for teams building their own visual language on top of solid behavior.

**Option C: CSS-First / Framework-Agnostic (AgnosticUI, Semantic UI)**
Components defined in pure CSS. Wrappers per framework. Best when working across multiple frontend stacks.

**Option D: Universal / Cross-Platform (Tamagui, React Native Web)**
One codebase targets web and native simultaneously. Compiled to atomic CSS on web, native primitives on mobile.

**Recommendation by context:**
- New SaaS product → Option A (move fast)
- Design agency with diverse clients → Option B (flexibility)
- Multi-framework enterprise → Option C
- App that must be web + native → Option D

---

### 2.3 The Finite State Machine Mental Model (Zag.js)

Every interactive component is a state machine. Before building, map the states:

```
Button:
  default → hover → pressed → loading → disabled

Dialog:
  closed → opening → open → closing → closed

Input:
  empty → focused → filled → error → disabled
```

For each state, define:
- **Visual change** (style)
- **Behavioral change** (event handling)
- **Accessibility change** (ARIA attributes)

This prevents "zombie states" — impossible combinations like `loading + disabled` or `error + success`.

---

### 2.4 Component API Design Rules

Inspired by Radix UI, React Aria, and Evergreen:

1. **Props should reflect intent, not implementation.** `variant="danger"` not `backgroundColor="red"`.
2. **Composability over configuration.** Prefer children and slots over props that control sub-rendering.
3. **Escape hatches always exist.** Every component should accept `className`, `style`, or `as` for when the system doesn't cover the edge case.
4. **Never block native behavior.** Don't prevent native events from bubbling unless there's a documented reason.
5. **Defaults must work without props.** A `<Button />` with no props must render something functional.

**Component Documentation Template:**
```
Name + Description
├── When to use / When NOT to use
├── Variants (visual states)
├── Props API
├── Slots / Composition API
├── Keyboard behavior
├── ARIA roles and attributes
├── Related components
└── Code example (minimal + real-world)
```

---

### 2.5 Patterns Library (Beyond Components)

Patterns are solutions to recurring design problems. Unlike components, patterns are documented decisions, not code units.

**Essential Patterns to Document:**
- **Empty State** — What to show when there's no data. Include icon + headline + CTA.
- **Loading State** — Skeleton screens vs spinners vs progress bars (and when to use which).
- **Error Handling** — Inline validation vs toast vs full-page error. Recovery path always included.
- **Confirmation Dialogs** — Destructive actions always require explicit confirmation. Irreversible actions get a typing challenge.
- **Onboarding** — First-run experience. Never assume the user knows the product.
- **Search & Filter** — How facets, query input, and results interact.
- **Forms** — Field order, grouping, validation timing (on blur, not on keystroke).

---

## 3. Accessibility Blueprint
> *Use when: Building accessible components, auditing existing UI, or establishing accessibility standards.*

### 3.1 The Four Accessibility Principles (POUR)

From WCAG 2.1 — the minimum standard for any public-facing product:

- **Perceivable** — All content can be seen, heard, or felt.
- **Operable** — All functionality works via keyboard, switch, or voice.
- **Understandable** — Content and UI behavior are predictable and clear.
- **Robust** — Works reliably across browsers, OS, and assistive tech.

**Minimum bar: WCAG 2.1 AA.** Government systems often target AAA.

---

### 3.2 The 6 Accessibility Layers (GitLab Pajamas)

Evaluate every component against all six:

```
1. Visual      — Color contrast ≥ 4.5:1 (text), ≥ 3:1 (large text/UI)
2. Semantic    — Correct HTML elements (button is a button, not a div)
3. Keyboard    — Tab, Enter, Space, Arrow keys, Escape all work
4. Focus       — Visible focus indicators, logical focus order
5. Screen Reader — Correct ARIA roles, labels, live regions
6. Motion      — Respects prefers-reduced-motion
```

---

### 3.3 Adobe React Aria's Key Insight

Accessibility is architecture, not a checkbox. The lesson:

- **Separate behavior from style.** Accessibility logic (ARIA, keyboard, focus) belongs in the behavior layer. Styles are layered on top.
- **Normalize across browsers.** The same focus behavior works differently in Safari, Firefox, and Chrome. A behavior library handles this so your product doesn't have to.
- **Three-tier composability.** Offer: (a) ready-made full components, (b) composable sub-components via context, (c) raw hooks for full control. Never force users to fork to customize.

---

### 3.4 Practical Accessibility Patterns

**Focus Management:**
- Modal opens → focus moves to first interactive element inside.
- Modal closes → focus returns to the element that triggered it.
- Focus never gets "lost" in the void.

**ARIA Live Regions:**
- Use `aria-live="polite"` for status messages (save successful, item added).
- Use `aria-live="assertive"` ONLY for errors that require immediate attention.
- Never spam live regions — one announcement per action.

**Color Independence:**
- Never use color as the ONLY way to convey information. Add icons, text, or patterns.
- Error states: red border + error icon + descriptive text. Not just red border.

**Keyboard Navigation Standards:**
```
Tab          — Move between interactive elements
Shift+Tab    — Reverse direction
Enter/Space  — Activate (buttons, checkboxes)
Arrow keys   — Navigate within a component (tabs, menus, selects)
Escape       — Close overlays, cancel operations
Home/End     — Jump to first/last item in a list
```

---

## 4. Voice & Tone Studio
> *Use when: Writing UI copy, error messages, onboarding text, empty states, or establishing content guidelines.*

### 4.1 The Tone Spectrum

All product voice exists on a spectrum. Calibrate to your product and moment:

```
Formal ←————————————————→ Playful
Professional ←——————————→ Friendly
Authoritative ←—————————→ Conversational
```

**By product type:**
- Enterprise (IBM, Salesforce, SAP): Formal, precise, authoritative.
- Productivity SaaS (Atlassian, GitHub): Professional but warm, collaborative.
- Consumer/E-commerce (Shopify Polaris): Clear, merchant-respectful, direct.
- Consumer/Education (Duolingo): Encouraging, playful, celebratory.
- Government (GOV.UK): Plain language, neutral, no jargon.

---

### 4.2 The 4 Voice Principles

1. **Clear over clever.** If a clever line requires a second read, rewrite it.
2. **Positive framing.** "Save your progress" not "Don't lose your work."
3. **Action-oriented.** CTAs describe what happens: "Send invoice" not "Submit."
4. **Empathy in errors.** Errors are not the user's fault. Guide them forward.

---

### 4.3 Content Patterns

**Button Labels:**
```
✓  Save changes       → Describes what will happen
✓  Send to team       → Specific and clear
✗  OK / Submit        → Vague, doesn't describe the action
✗  Click here         → Inaccessible (screen readers read links out of context)
```

**Error Messages:**
```
Structure: What went wrong + Why (if helpful) + What to do next

✓  "Your session expired. Sign in again to continue."
✗  "Error 403. Request forbidden."
```

**Empty States:**
```
Structure: Icon/illustration + Headline + Supporting text + CTA

"No projects yet" 
  → "Create your first project to get started."
  → [Create project] button
```

**Confirmation Dialogs:**
```
Headline: Verb + noun (what's happening)
Body: Consequences, not repetition of headline
Cancel: [Cancel] — always on the left
Confirm: [Delete project] — mirrors headline verb, not just "OK"
```

---

### 4.4 Formatting Conventions (GitLab Pajamas)

- **Dates**: Absolute when > 1 week ago (`Jun 15`), relative when < 1 week (`3 days ago`).
- **Numbers**: Use commas for thousands (`1,234`), not spaces.
- **Punctuation**: No periods in UI labels. Periods in body copy.
- **Verb tense**: Present for current state (`Saving...`), past for completion (`Saved`).
- **Capitalization**: Title case for navigation, labels, button labels. Sentence case for body copy and descriptions.

---

## 5. Motion Playbook
> *Use when: Designing animations, transitions, or interaction feedback.*

### 5.1 The Purpose of Motion

Motion has 4 legitimate jobs in UI. Nothing else.

```
1. Feedback     — Confirm an action occurred (button press ripple, success checkmark)
2. Orientation  — Show spatial relationship (drawer slides from right, where it lives)
3. Focus        — Direct attention (highlight new content, shake on error)
4. Delight      — Reward moments (celebratory confetti, character animation)
```

Never animate for decoration. Every animation must serve at least one of these.

---

### 5.2 Duration Scale

```
Instant   — 0ms      : State changes, no transition (toggles in dense UI)
Micro     — 100ms    : Button press, icon state change
Fast      — 150-200ms: Tooltip appear, small popover
Standard  — 250-300ms: Modal open, dropdown expand
Slow      — 400-500ms: Page transition, large drawer
Emphasis  — 600ms+   : Onboarding animations, celebration moments
```

**Rule: Exits are faster than entrances.** Content leaving the screen feels sluggish if it matches entrance speed. Exits: 100-150ms. Entrances: 200-300ms.

---

### 5.3 Easing Curves

```
Standard   — cubic-bezier(0.4, 0.0, 0.2, 1) : Most UI transitions
Enter      — cubic-bezier(0.0, 0.0, 0.2, 1) : Elements entering from off-screen
Exit       — cubic-bezier(0.4, 0.0, 1, 1)   : Elements leaving the screen
Emphasize  — cubic-bezier(0.2, 0.0, 0, 1.0) : Expressive moments, spring-like
Linear     — linear                          : Progress bars, counters only
```

Never use `ease-in-out` (the CSS default) — it feels mechanical and uncommitted.

---

### 5.4 Reduced Motion

Always respect `prefers-reduced-motion: reduce`.

```css
@media (prefers-reduced-motion: reduce) {
  /* Replace animations with instant state changes */
  /* Or use opacity-only transitions (0.3s max) */
}
```

Vestibular disorders make motion physically painful. This is not optional.

---

### 5.5 GitLab Icon Animation Pattern

For icon state transitions:
- **Feedback icons** (success ✓, error ✗): Draw-on animation, 200-300ms.
- **Loading spinner**: Constant rotation, 750ms per revolution. Never stops until loaded.
- **Expand/collapse chevron**: 90° rotation, 150ms standard easing.

---

## 6. Cross-Platform Mapper
> *Use when: Designing a product that must work across web, iOS, Android, or React Native.*

### 6.1 Input Model Differences

| Dimension | Web | iOS | Android | watchOS |
|---|---|---|---|---|
| Primary input | Mouse + keyboard | Touch | Touch | Crown + tap |
| Touch targets | 24px minimum | 44px minimum | 48dp minimum | 44pt minimum |
| Navigation | Browser history | Navigation stack | Back button (physical/gesture) | Page-based |
| Overlays | CSS z-index | Sheets / modals | Bottom sheets / dialogs | Minimal |
| Text input | Keyboard always present | Soft keyboard | Soft keyboard | Voice preferred |

---

### 6.2 Token Portability (Thumbprint Model)

Define all design tokens once, export to every platform:

```
tokens.json (source)
  ├── tokens.scss       → Web CSS
  ├── tokens.js         → React / JS
  ├── tokens.swift      → iOS
  └── tokens.xml        → Android
```

This means the same `color-action` token is `#3B82F6` everywhere — not approximated, not hardcoded.

---

### 6.3 Tamagui's Universal Component Model

For React + React Native shared codebases:

- Style with a superset of React Native's style API — it compiles to atomic CSS on web.
- Themes as CSS variables on web, JavaScript objects on native.
- Animation drivers are swappable per platform (Reanimated on native, CSS on web).
- Responsive props declared inline, compiled away at build time — no runtime overhead.

**When to use:** App that genuinely needs web + native parity. Not worth the complexity if only one platform.

---

### 6.4 Platform Personality vs Platform Consistency

**Consistency-first (Fluent, Atlassian):** Every platform feels like the same product. Navigation, visual language, and interactions are normalized.

**Platform-native (Apple HIG):** Each platform adopts native patterns. iOS uses swipe-to-delete, macOS uses right-click menus — even if the product is the same.

**Recommendation:** Consistency wins for B2B/enterprise tools where efficiency is paramount. Platform-native wins for consumer apps where the user's OS fluency is an asset.

---

### 6.5 AgnosticUI's Framework-Agnostic Principle

If you support multiple frontend stacks (React, Vue, Svelte, Angular):
- Write component logic once in pure CSS/HTML.
- Wrap with a thin adapter per framework.
- Never duplicate behavior — only duplicate the binding layer.
- Expose the source files directly in the project (not inside `node_modules`) so they can be read and modified without ejecting.

---

## 7. Context Adapters
> *Use when: Adapting design system principles to a specific industry, product type, or user context.*

### 7.1 Enterprise & B2B (IBM, Salesforce, SAP, Atlassian, Elastic)

**Design priorities:**
- Information density over whitespace — users are professionals who live in these tools.
- Keyboard navigation is not optional — power users never reach for the mouse.
- Data tables are the hero component. Invest heavily in sorting, filtering, inline editing.
- Sidebar navigation, not hamburger menus. Screen space is abundant on desktop.
- Error recovery is critical — destructive actions require multi-step confirmation.
- AI patterns (Atlassian Rovo, GitLab Duo): Surface AI suggestions inline, never modal. Show provenance. Allow one-click dismissal.

**Token considerations:**
- Dense type scale (13-14px body, tight line height).
- More neutral, desaturated palette — color signals action, not decoration.
- Elevation system matters: distinguish primary surface, sidebar, modal, tooltip.

---

### 7.2 Consumer & E-Commerce (Shopify, Duolingo, Airbnb, GO-JEK)

**Design priorities:**
- Visual delight as a conversion tool — emotion sells.
- Mobile-first always. Most consumer traffic is mobile.
- Onboarding is a product in itself. First-run experience = first impression.
- Trust signals embedded in UI: reviews, guarantees, social proof near CTAs.
- Gamification patterns (Duolingo model): streaks, progress indicators, celebration moments. Reward every completed action.
- Large touch targets, generous spacing, high-contrast CTAs.

**Token considerations:**
- Expressive type scale with a brand personality font.
- Saturated, vibrant brand colors with confidence.
- Illustration/animation as a system element — not an afterthought.

---

### 7.3 Government & Public Sector (GOV.UK, USWDS, Australian Government)

**Design priorities:**
- Accessibility first. AAA compliance where possible. No motion by default.
- Plain language. Every word earns its place. No jargon.
- Progressive enhancement — must work without JavaScript.
- Consistent across all departments — one system, many products.
- Trust through restraint. Government sites should feel stable, not trendy.
- Test with real users from diverse ability, age, and tech backgrounds.

**Token considerations:**
- Simple, high-contrast palette (high legibility at low contrast settings).
- Default serif or system font (no external font dependencies).
- Minimal animation.
- Forms are the core component — invest disproportionately.

---

### 7.4 Financial & Healthcare (AXA, E-Trade, Finastra)

**Design priorities:**
- Trust and clarity are the primary emotions to design for. Not delight.
- Data visualization is a first-class feature: charts, timelines, portfolio views.
- Compliance-aware copy — every claim may need legal review.
- Never make irreversible financial actions easy. Friction is a feature.
- Precision typography — numbers must be tabular, monospace-aligned.

**Token considerations:**
- Conservative color use. Green = gain, red = loss is a global convention. Don't break it.
- Tabular number font variant (`font-variant-numeric: tabular-nums`).
- Elevation for transaction flows — modal + tray pattern for multi-step flows.

---

### 7.5 Developer Tools & Platforms (GitHub, GitLab, Elastic, Grafana)

**Design priorities:**
- Monospace font support. Code is content.
- Dark mode is a first-class feature, not an afterthought — many devs live in dark mode.
- Information density: developers want data, not whitespace.
- Keyboard shortcuts are a delight feature — document and surface them.
- CLI/terminal aesthetics are aspirational — bring terminal clarity to GUI.
- Syntax highlighting as a design token system.

**Token considerations:**
- Dual light/dark token system from day one.
- Color-blind safe data palette for charts (no red/green only).
- Monospace type as a design element, not just a code style.

---

### 7.6 Media & Publishing (BBC GEL, FutureLearn)

**Design priorities:**
- Typography is the hero. The content IS the product.
- Reading comfort: optimal line length (45-75 chars), generous line height (1.5-1.8).
- Image system with strong art direction rules.
- Navigation serves discoverability — everything must be findable.
- Streaming/real-time state handling: live badges, countdown timers.
- Accessibility for audio/video: captions, transcripts, audio descriptions.

**Token considerations:**
- Editorial-grade type scale with large Display sizes.
- Restrained UI palette so content (images, video) pops.
- Responsive typography that scales gracefully from mobile to large display.

---

## 8. Governance Engine
> *Use when: Running a design system as a shared product for multiple teams.*

### 8.1 The Design System as a Product

A design system is not a side project. It is a product with users (designers and engineers), a backlog, releases, and a support model.

**The three organizational models:**

```
Centralized   — One core team owns everything. Fast, consistent. Risks: bottleneck.
Federated     — Core team sets standards; squads contribute. Scales well. Risks: drift.
Distributed   — Each team owns their part. Risky, leads to fragmentation.
```

**Recommendation:** Start centralized. Move to federated as the system and org mature.

---

### 8.2 Contribution Model (GitLab Pajamas, Atlassian)

Create a contribution playbook:

```
Propose   → Request/RFC in shared issue tracker
Review    → Design + engineering + accessibility review
Build     → Component built against design token standards
Document  → Component doc + Storybook + Figma annotation
Release   → Semantic versioning (MAJOR.MINOR.PATCH)
Announce  → Changelog + team notification
```

**Contribution tiers:**
- **Tier 1 (Core):** Owned by the core team. Reviewed strictly.
- **Tier 2 (Contributed):** Built by product teams, reviewed by core.
- **Tier 3 (Experimental):** Labs/sandbox. Use at your own risk, may be promoted.

---

### 8.3 Versioning & Breaking Changes

Use **Semantic Versioning**:
- `PATCH` (1.0.1) — Bug fix, no API change.
- `MINOR` (1.1.0) — New component or variant, backward compatible.
- `MAJOR` (2.0.0) — Breaking change. Requires migration guide.

**Codemods:** Provide automated migration scripts (`npx @yourds/upgrade`) for breaking changes. Manual migrations kill adoption.

---

### 8.4 Tooling Stack (Patterns from 100+ Systems)

**Design:**
- Figma (dominant), tokens via Figma Variables or Token Studio plugin.
- Storybook as the living reference (component isolation, interaction testing).
- Chromatic or Percy for visual regression testing.

**Engineering:**
- CSS: Sass/SCSS for token generation, CSS custom properties for runtime theming.
- JS: TypeScript for component APIs (prevents prop misuse at compile time).
- Bundling: Vite or tsup for library builds.
- Distribution: npm package with ESM + CJS exports.
- Monorepo: Turborepo or Nx for multi-package systems.

**Testing:**
- Unit: Jest + Testing Library (behavior, not implementation).
- Accessibility: axe-core automated scans in CI.
- Visual: Chromatic snapshots per Storybook story.
- E2E: Playwright for critical interaction paths.

---

### 8.5 Documentation Architecture

Inspired by Primer (GitHub's 3-audience model):

```
Product UI docs     → For engineers building product features
Brand/Marketing docs → For designers making campaign assets  
Contribution docs   → For teams wanting to extend the system
```

**Documentation page structure:**
```
Overview      — What it is, when to use, when NOT to use
Anatomy       — Labeled diagram of the component parts
Variants      — All visual states with visual examples
Behavior      — Interaction, animation, state transitions
Accessibility — Keyboard, ARIA, screen reader notes
Content       — Copy guidelines specific to this component
Code          — Import, props API, code examples
Changelog     — Version history for this component
```

---

### 8.6 Measuring System Health

Track these metrics to know if your system is working:

| Metric | What it measures |
|---|---|
| Adoption rate | % of product surfaces using system components |
| Design debt | # of one-off components not in the system |
| Contribution velocity | PRs merged per quarter from outside the core team |
| Accessibility score | axe-core violations per release |
| Time to first use | How long for a new engineer to render a working component |
| Satisfaction score | NPS from designers and engineers using the system |

---

## Quick Reference: Principles Distilled

### The 12 Universal Principles

These appeared across nearly every system studied:

1. **Semantic over visual** — Name things by role, not appearance.
2. **Accessibility is architecture** — Bake it in from the start; retrofitting fails.
3. **Tokens are the system** — Components change; tokens should be permanent.
4. **Composability over configuration** — Fewer props, more composition.
5. **Platform respect** — Native patterns exist for good reasons. Override them with purpose.
6. **Motion serves function** — Every animation must earn its place.
7. **Documentation is the product** — Undocumented components don't exist for most users.
8. **Consistency enables speed** — Users shouldn't have to think about familiar patterns.
9. **Design for error** — Every interaction can fail. Design the recovery path first.
10. **Color is semantic** — Color should convey meaning, not just aesthetics.
11. **Dark mode is a system** — Not an inverted afterthought.
12. **The system serves the product** — When the system constrains a real user need, the product wins. Document the exception.

---

## Source Systems Reference

| System | Company | Best For |
|---|---|---|
| Material Design 3 | Google | Consumer apps, dynamic color, mobile |
| Human Interface Guidelines | Apple | Platform-native iOS/macOS design |
| Atlassian Design Language | Atlassian | Productivity/SaaS, AI patterns |
| Polaris | Shopify | E-commerce, merchant-facing tools |
| Primer | GitHub | Developer tools, multi-audience docs |
| Pajamas | GitLab | Developer tools, AI-human patterns |
| Carbon | IBM | Enterprise, data density, 2x grid |
| Fluent 2 | Microsoft | Cross-platform, Office-ecosystem |
| Elastic UI | Elastic | Search/analytics, data-heavy UIs |
| React Aria | Adobe | Accessible behavior primitives |
| Radix UI | WorkOS | Fast, accessible, unstyled components |
| Zag.js | Chakra team | State-machine-driven component logic |
| Semantic UI | Community | Human-readable HTML, theming |
| Evergreen | Segment | Enterprise SaaS, composable primitives |
| Tamagui | Community | React + React Native universal |
| AgnosticUI | Community | Multi-framework, AI-readable components |
| Thumbprint | Thumbtack | Service marketplace, multi-platform tokens |
| GOV.UK / USWDS | Government | Public sector, accessibility-first |
| Gestalt | Pinterest | Visual discovery, consumer |
| GEL | BBC | Media, editorial, broadcasting |

---

*Compiled from the awesome-styleguides repository (github.com/streamich/awesome-styleguides) and direct exploration of 20+ live design systems.*
