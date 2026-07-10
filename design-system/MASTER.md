# Design System

> When building a specific page, check `design-system/pages/[page-name].md` first.
> If a page-level file exists, its rules override this document.

---

**Project:** claude-web-studio

---

## Brand Colors

No default palette is defined. Colors are generated per-project using the design system generator:

```bash
python3 .claude/skills/ui-ux-pro-max/scripts/search.py "<keywords>" --design-system --persist -p "<project-name>"
```

This produces a project-specific palette based on product type, industry, and style preferences.

---

## Typography

Typography is configured per-project using the design system generator. Guidelines:

- Heading: sans-serif, 600–700 weight
- Body: sans-serif or serif, 400–500 weight
- Line height: 1.5–1.75 for body, 1.1–1.3 for headings
- Max line length: 65–75 characters

---

## Spacing (8px grid)

| Token | Value | Usage |
|-------|-------|-------|
| `--space-xs` | 4px / 0.25rem | Tight gaps |
| `--space-sm` | 8px / 0.5rem | Icon gaps, inline spacing |
| `--space-md` | 16px / 1rem | Standard padding |
| `--space-lg` | 24px / 1.5rem | Section padding |
| `--space-xl` | 32px / 2rem | Large gaps |
| `--space-2xl` | 48px / 3rem | Section margins |
| `--space-3xl` | 64px / 4rem | Hero padding |

---

## Shadows

| Level | Value | Usage |
|-------|-------|-------|
| `--shadow-sm` | `0 1px 2px rgba(0,0,0,0.05)` | Subtle lift |
| `--shadow-md` | `0 4px 6px rgba(0,0,0,0.1)` | Cards, buttons |
| `--shadow-lg` | `0 10px 15px rgba(0,0,0,0.1)` | Modals, dropdowns |
| `--shadow-xl` | `0 20px 25px rgba(0,0,0,0.15)` | Hero images, featured cards |

---

## Components

### Buttons

- Padding: 12px 24px
- Border-radius: 8px
- Font-weight: 600
- Transition: all 200ms ease
- Hover: opacity 0.9, translateY(-1px)
- Cursor: pointer

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
- Font-size: 16px (prevents iOS zoom)
- Focus: colored border + ring shadow

### Modals

- Overlay: rgba(0,0,0,0.5) with backdrop-filter blur(4px)
- Container: border-radius 16px, padding 32px, shadow-xl
- Max-width: 500px, width: 90%

---

## Style Direction

**Default style:** Minimalism & Swiss Style

Clean, spacious, functional, high contrast, geometric, grid-based. Best for SaaS platforms, enterprise apps, dashboards, professional tools.

**Key effects:** Subtle hover (200–250ms), smooth transitions, sharp shadows, clear type hierarchy, fast loading.

Override by running the design system generator with different keywords (e.g., "brutalist", "playful", "glassmorphism").

---

## Page Pattern

**Scroll-Triggered Storytelling**

| Section | Content |
|---------|---------|
| 1 | Intro hook |
| 2 | Problem (Chapter 1) |
| 3 | Journey (Chapter 2) |
| 4 | Solution (Chapter 3) |
| 5 | Climax CTA |

CTA placement: end of each chapter (mini) + final climax CTA.

---

## Anti-Patterns

- No emojis as icons — use SVG icons (Heroicons, Lucide)
- No missing cursor:pointer on clickable elements
- No layout-shifting hover effects
- No low contrast text — maintain 4.5:1 minimum
- No instant state changes — always transition (150–300ms)
- No invisible focus states
- No complex navigation that hides key paths
- No hidden contact info

---

## Quality Checklist

- [ ] Brand colors set (not defaults)
- [ ] Icons from consistent set (Heroicons or Lucide)
- [ ] cursor-pointer on all clickable elements
- [ ] Hover states with 150–300ms transitions
- [ ] Color contrast 4.5:1 minimum
- [ ] Focus states visible for keyboard navigation
- [ ] prefers-reduced-motion respected
- [ ] Responsive: 375px, 768px, 1024px, 1440px
- [ ] No content hidden behind fixed navbars
- [ ] No horizontal scroll on mobile
