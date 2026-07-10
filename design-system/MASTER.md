# Design System Master File

> **LOGIC:** When building a specific page, first check `design-system/pages/[page-name].md`.
> If that file exists, its rules **override** this Master file.
> If not, strictly follow the rules below.

---

**Project:** claude-web-studio
**Generated:** 2026-07-10

---

## BEFORE YOU BUILD: Ask for Brand Colors

**No default palette is defined.** Before building any component or page, you MUST ask the user for:

1. **Brand colors** — primary, secondary, accent/CTA
2. **Background preference** — light, dark, or both
3. **Mood/vibe** — e.g. "warm and friendly", "cold and corporate", "bold and playful"

Then run:
```bash
python3 .claude/skills/ui-ux-pro-max/scripts/search.py "<user's keywords>" --design-system --persist -p "<project-name>"
```

This generates a project-specific palette. Until colors are provided, DO NOT proceed with visual code.

---

## Global Rules (color-independent)

### Typography

Ask user for font preference, or run `/ui-ux-pro-max` to get a recommended pairing. Common starting point:
- Heading: sans-serif, 600-700 weight
- Body: sans-serif or serif, 400-500 weight
- Line height: 1.5-1.75 for body, 1.1-1.3 for headings
- Max line length: 65-75 characters

### Spacing System (8px grid)

| Token | Value | Usage |
|-------|-------|-------|
| `--space-xs` | `4px` / `0.25rem` | Tight gaps |
| `--space-sm` | `8px` / `0.5rem` | Icon gaps, inline spacing |
| `--space-md` | `16px` / `1rem` | Standard padding |
| `--space-lg` | `24px` / `1.5rem` | Section padding |
| `--space-xl` | `32px` / `2rem` | Large gaps |
| `--space-2xl` | `48px` / `3rem` | Section margins |
| `--space-3xl` | `64px` / `4rem` | Hero padding |

### Shadow Depths

| Level | Value | Usage |
|-------|-------|-------|
| `--shadow-sm` | `0 1px 2px rgba(0,0,0,0.05)` | Subtle lift |
| `--shadow-md` | `0 4px 6px rgba(0,0,0,0.1)` | Cards, buttons |
| `--shadow-lg` | `0 10px 15px rgba(0,0,0,0.1)` | Modals, dropdowns |
| `--shadow-xl` | `0 20px 25px rgba(0,0,0,0.15)` | Hero images, featured cards |

---

## Component Specs (structure only — colors come from brand)

### Buttons

- Padding: 12px 24px
- Border-radius: 8px
- Font-weight: 600
- Transition: all 200ms ease
- Hover: opacity 0.9, translateY(-1px)
- Always: `cursor: pointer`

### Cards

- Border-radius: 12px
- Padding: 24px
- Shadow: `--shadow-md`
- Hover: shadow-lg, translateY(-2px)
- Transition: all 200ms ease

### Inputs

- Padding: 12px 16px
- Border: 1px solid (neutral border color)
- Border-radius: 8px
- Font-size: 16px (prevents zoom on mobile)
- Focus: colored border + ring shadow

### Modals

- Overlay: rgba(0,0,0,0.5) + backdrop-filter blur(4px)
- Container: white/dark bg, border-radius 16px, padding 32px, shadow-xl
- Max-width: 500px, width: 90%

---

## Style Guidelines

**Style:** Minimalism & Swiss Style (override by running /ui-ux-pro-max with different keywords)

**Keywords:** Clean, simple, spacious, functional, white space, high contrast, geometric, sans-serif, grid-based, essential

**Key Effects:** Subtle hover (200-250ms), smooth transitions, sharp shadows if any, clear type hierarchy, fast loading

### Page Pattern

**Pattern Name:** Scroll-Triggered Storytelling

- **Conversion Strategy:** Narrative increases time-on-page 3x. Use progress indicator. Mobile: simplify animations.
- **CTA Placement:** End of each chapter (mini) + Final climax CTA
- **Section Order:** 1. Intro hook, 2. Problem, 3. Journey, 4. Solution, 5. Climax CTA

---

## Anti-Patterns (Do NOT Use)

- No emojis as icons — use SVG icons (Heroicons, Lucide, Simple Icons)
- No missing cursor:pointer on clickable elements
- No layout-shifting hovers — avoid scale transforms that displace siblings
- No low contrast text — 4.5:1 minimum contrast ratio
- No instant state changes — always use transitions (150-300ms)
- No invisible focus states — focus states must be visible for a11y
- No complex navigation that hides key paths
- No hidden contact info

---

## Pre-Delivery Checklist

Before delivering any UI code, verify:

- [ ] Brand colors confirmed with user (NOT defaults)
- [ ] No emojis used as icons (use SVG instead)
- [ ] All icons from consistent icon set (Heroicons/Lucide)
- [ ] `cursor-pointer` on all clickable elements
- [ ] Hover states with smooth transitions (150-300ms)
- [ ] Color contrast 4.5:1 minimum
- [ ] Focus states visible for keyboard navigation
- [ ] `prefers-reduced-motion` respected
- [ ] Responsive: 375px, 768px, 1024px, 1440px
- [ ] No content hidden behind fixed navbars
- [ ] No horizontal scroll on mobile
