# Claude Web Studio

![Next.js](https://img.shields.io/badge/Next.js-16-black?logo=next.js)
![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-4-06B6D4?logo=tailwindcss&logoColor=white)
![Framer Motion](https://img.shields.io/badge/Framer_Motion-12-FF0055?logo=framer&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green)

AI-powered premium website builder stack — Next.js + Framer Motion + design system + 21st.dev components, orchestrated by Claude Code.

Turn Claude Code from a generic code generator into a senior-level web designer. One prompt, agency-grade output.

---

## How It Works

```
┌─────────────────────────────────────────────────────────────┐
│                    YOU (the human)                           │
│         "Build a landing page for my SaaS product"          │
└──────────────────────────┬──────────────────────────────────┘
                           │
                           ▼
┌─────────────────────────────────────────────────────────────┐
│                  CLAUDE CODE (the engine)                    │
│                                                             │
│  Reads 3 things automatically:                              │
│  ┌───────────────┐ ┌──────────────┐ ┌───────────────────┐  │
│  │ design-system/ │ │ .claude/     │ │ .claude/skills/   │  │
│  │ MASTER.md     │ │ commands/    │ │ ui-ux-pro-max/    │  │
│  │               │ │ build-page.md│ │                   │  │
│  │ Spacing       │ │              │ │ 67 styles         │  │
│  │ Shadows       │ │ Stack rules  │ │ 96 palettes       │  │
│  │ Components    │ │ Quality      │ │ 57 fonts          │  │
│  │ Anti-patterns │ │ checklist    │ │ 99 UX rules       │  │
│  └───────┬───────┘ └──────┬───────┘ └────────┬──────────┘  │
│          └─────────────────┴───────────────────┘             │
│                            │                                 │
│                            ▼                                 │
│              ┌─────────────────────────┐                    │
│              │  GENERATES CODE USING:  │                    │
│              └─────────────────────────┘                    │
└──────────────────────────┬──────────────────────────────────┘
                           │
              ┌────────────┼────────────┐
              │            │            │
              ▼            ▼            ▼
┌──────────────┐ ┌──────────────┐ ┌──────────────────┐
│   NEXT.JS    │ │FRAMER MOTION │ │   21st.dev       │
│   App Router │ │              │ │   Components     │
│              │ │ whileInView  │ │                  │
│ src/app/     │ │ stagger      │ │ Hero sections    │
│ src/         │ │ hover scale  │ │ Pricing tables   │
│ components/  │ │ page fade-in │ │ Feature cards    │
│              │ │              │ │ Navbars/Footers  │
│ Tailwind CSS │ │ "use client" │ │                  │
└──────┬───────┘ └──────┬───────┘ └────────┬─────────┘
       │                │                   │
       └────────────────┴───────────────────┘
                        │
                        ▼
┌─────────────────────────────────────────────────────────────┐
│                    OUTPUT: Your Website                      │
│                                                             │
│  ✓ Consistent design tokens (not random hex codes)          │
│  ✓ Scroll-triggered animations (not static blocks)          │
│  ✓ Professional components (not reinvented wheels)          │
│  ✓ Accessible (4.5:1 contrast, focus states, keyboard nav) │
│  ✓ Responsive (375px → 1440px)                              │
│  ✓ Lighthouse 90+                                           │
└─────────────────────────────────────────────────────────────┘
```

---

## Prerequisites

| Requirement | Version | Install |
|-------------|---------|---------|
| Node.js | 18+ | [nodejs.org](https://nodejs.org) |
| npm | 9+ | Comes with Node.js |
| Python | 3.8+ | `brew install python3` (macOS) or [python.org](https://python.org) |
| Claude Code | Latest | `npm install -g @anthropic-ai/claude-code` |
| Anthropic account | — | [console.anthropic.com](https://console.anthropic.com) |

The ui-ux-pro-max design skill is **bundled in this repo** (`.claude/skills/ui-ux-pro-max/`) — no separate installation needed.

---

## Quick Start

```bash
# 1. Clone the repo
git clone https://github.com/YOUR_USERNAME/claude-web-studio.git
cd claude-web-studio

# 2. Install dependencies
npm install

# 3. Start the dev server
npm run dev
# → http://localhost:3000

# 4. Open Claude Code in the project directory
claude

# 5. Use the built-in command to start building
/build-page
# Claude will ask for your brand colors, then generate production-ready UI
```

---

## The 4 Layers

### Layer 1: Next.js + Tailwind (Framework)

The foundation. Server-side rendering, file-based routing, utility-first CSS. Every page you build lives in `src/app/`.

### Layer 2: Framer Motion (Animation)

The polish. Without this, AI-generated sites look static and lifeless. With it:
- Hero sections breathe (fade + slide on mount)
- Cards stagger in on scroll
- Buttons scale on hover
- Page transitions feel smooth

This single addition is what separates "AI website" from "agency website."

### Layer 3: UI/UX Pro Max (Design Intelligence)

The taste. A bundled skill with **67 styles, 96 color palettes, 57 font pairings, and 99 UX guidelines**. Instead of Claude making random design choices, it follows a comprehensive design system.

**No default colors are baked in.** When you start building, Claude asks for your brand colors/mood, then generates a tailored palette.

### Layer 4: 21st.dev (Component Library)

The shortcut. Instead of Claude inventing every component from scratch, it pulls from a library of production-ready, professionally designed UI blocks and adapts them to your brand.

---

## Usage Examples

### Example 1: Generate your design system

```
Give me a design system for a fintech startup.
Mood: trustworthy, modern, dark mode preferred.
Brand colors: deep navy (#1a1a2e) and electric blue (#4361ee).
```

Claude runs the design system generator and creates your project-specific `MASTER.md` with colors, typography, spacing, and component specs.

### Example 2: Build a full landing page

```
Build a landing page for a project management SaaS called "FlowBoard".
Include: sticky navbar, hero with headline + CTA, 3 feature cards with icons,
social proof section with logos, pricing table (3 tiers), FAQ accordion, footer.
Use scroll-triggered animations on every section.
```

### Example 3: Add a section

```
Add a testimonial carousel between the features and pricing sections.
Pull a testimonial component from 21st.dev, adapt it to our design tokens,
and add a staggered fade-in animation.
```

### Example 4: Review and polish

```
Review the current landing page for:
- Animation timing (should feel snappy, not slow)
- Mobile responsiveness (test at 375px)
- Accessibility (contrast, focus states, keyboard nav)
- Performance (lazy load images, optimize fonts)
Fix any issues you find.
```

---

## Design System

The design system lives in `design-system/MASTER.md`. It defines:

- **Spacing** — 8px grid system (4px to 64px tokens)
- **Shadows** — 4 depth levels for elevation
- **Component specs** — Button, card, input, modal structures (color-independent)
- **Anti-patterns** — Things Claude must never do
- **Pre-delivery checklist** — Quality gates before any code ships

### Generating a Brand-Specific Palette

```bash
python3 .claude/skills/ui-ux-pro-max/scripts/search.py "fintech dark modern" --design-system --persist -p "YourProject"
```

This searches 5 domains in parallel (product type, style, color, landing structure, typography) and returns a complete system.

### Page-Specific Overrides

Create `design-system/pages/pricing.md` to override MASTER rules for a specific page. Claude checks page-level files first, falls back to MASTER.

---

## Commands

### `/build-page`

**How to use:** In Claude Code, type `/build-page` in the prompt. Claude reads the command definition and follows all 4 layers automatically.

What it enforces:

1. Next.js App Router + TypeScript
2. Framer Motion animations (scroll reveals, stagger, hover)
3. Design system rules (asks for brand colors if not yet configured)
4. 21st.dev components where applicable
5. Quality checklist before delivering

You can also just describe what you want in plain language — the design system and command file are both read automatically by Claude Code when working in this project.

---

## Tech Stack

| Layer | Tool | Purpose |
|-------|------|---------|
| Framework | Next.js 16 + App Router | SSR, routing, structure |
| Styling | Tailwind CSS 4 | Utility-first CSS |
| Animation | Framer Motion 12 | Scroll reveals, hover, transitions |
| Types | TypeScript 5 | Type safety |
| Design | ui-ux-pro-max (bundled) | 67 styles, 96 palettes, 57 fonts, 99 UX rules |
| Components | 21st.dev | Production-ready UI blocks |
| AI | Claude Code | The developer |

---

## Project Structure

```
claude-web-studio/
├── src/
│   └── app/                # Next.js App Router pages
├── design-system/
│   ├── MASTER.md           # Global design rules (no default colors)
│   └── pages/              # Page-specific overrides
├── .claude/
│   ├── commands/
│   │   └── build-page.md   # Enforces all 4 layers
│   └── skills/
│       └── ui-ux-pro-max/  # Bundled design intelligence (548K)
│           ├── SKILL.md
│           ├── scripts/     # Python CLI for design system generation
│           └── data/        # 67 styles, 96 palettes, 57 fonts, 99 UX rules
├── package.json
└── tsconfig.json
```

---

## What You Save

| Traditional Route | Cost | Time |
|-------------------|------|------|
| Hire a web designer | $5K–$15K | 4–8 weeks |
| Hire an agency | $10K–$30K | 6–12 weeks |
| Claude Code + this stack | $20/month | 1–3 days |

---

## Contributing

1. Fork the repo
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Make your changes
4. Test with `npm run build` (no errors)
5. Open a PR with a clear description

### Ideas for Contribution

- Add more design system presets (e-commerce, healthcare, gaming)
- Create additional `/commands` for common workflows
- Add example pages showcasing different styles
- Improve the ui-ux-pro-max data (more palettes, fonts, UX rules)

---

## License

MIT

---

## Credits

- Stack concept from [noocap's guide](https://noocap.notion.site)
- Design intelligence from ui-ux-pro-max
- Components from [21st.dev](https://21st.dev)
- Built with [Claude Code](https://claude.com/claude-code)
