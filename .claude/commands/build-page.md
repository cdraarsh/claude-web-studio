# Build Page

Build a section or full page for this project following all 4 layers of our stack.

## Pre-flight: Brand Colors

Before writing any visual code, check if brand colors exist in `design-system/MASTER.md`. If only the template is there (no hex values defined), ask the user for:
1. Brand colors (primary, secondary, accent/CTA)
2. Background preference (light, dark, or both)
3. Mood/vibe (e.g. "warm and friendly", "bold and playful")

Then generate the palette:
```bash
python3 .claude/skills/ui-ux-pro-max/scripts/search.py "<user's keywords>" --design-system --persist -p "<project-name>"
```

## Stack Rules

### 1. Framework
- Next.js App Router with TypeScript
- Tailwind CSS for all styling
- Components in `src/components/`
- Pages in `src/app/`

### 2. Animation (Framer Motion)
- Use `"use client"` directive on any component with Framer Motion
- Scroll-triggered reveals using `whileInView` with `viewport={{ once: true }}`
- Staggered children with `variants` and `staggerChildren: 0.1`
- Hover transitions: `whileHover={{ scale: 1.02 }}` with `transition={{ duration: 0.2 }}`
- Page transitions: fade in on mount with `initial={{ opacity: 0, y: 20 }}`
- Respect `prefers-reduced-motion` — wrap animations in a check

### 3. Design System (from design-system/MASTER.md)
- Read `design-system/MASTER.md` before building any component
- Follow the color tokens, typography, and spacing defined there
- Check `design-system/pages/[page-name].md` for page-specific overrides
- Run `/ui-ux-pro-max` for new design decisions

### 4. Components (21st.dev)
- Before building a complex component from scratch, check https://21st.dev for a production-ready version
- Adapt 21st.dev components to match our design tokens
- Add Framer Motion entrance animations to imported components

## Quality Checklist
- [ ] No emojis as icons — use Lucide React or Heroicons
- [ ] `cursor-pointer` on all clickable elements
- [ ] Hover states with 150-300ms transitions
- [ ] Color contrast 4.5:1 minimum
- [ ] Focus states visible for keyboard navigation
- [ ] Responsive: test at 375px, 768px, 1024px, 1440px
- [ ] Images: use `next/image` with proper width/height
- [ ] Lighthouse performance 90+
