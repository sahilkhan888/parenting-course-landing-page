# Parenting Course Landing Page

## Project Overview

Marketing landing page for "Raise Emotionally Strong, Resilient Children" — an online parenting course by Aswathi Sreekanth, offered through Entri. Single-page static site optimized for conversion.

## Tech Stack

- **HTML5** — Single `index.html` file (no framework)
- **Tailwind CSS** — Via CDN (`cdn.tailwindcss.com`), config inlined in `<script>` tag
- **Vanilla JavaScript** — Inline scripts for scroll animations, accordions, nav effects
- **Google Fonts** — Inter (body) and Noto Serif (headings)

## Project Structure

```
index.html              # Entire landing page (HTML + Tailwind config + JS)
assets/assets/
  Hero/                 # Hero section images (hero.png, grid.png, blue-shape.svg)
  Instructor/           # Instructor photos and background (aswathy.png, aswathy-full.png, bg-pattern.png)
  entri-assets/         # Brand assets (entri-logo.svg)
```

## Development

No build step. Open `index.html` directly in a browser or serve with any static server:

```sh
# Option 1: Python
python3 -m http.server 8000

# Option 2: Node (if npx available)
npx serve .
```

There is no `package.json`, no bundler, no linter, no test framework.

## Design System

Tailwind theme is extended inline in `index.html`:

- **Primary blue**: `#0089FF` (light: `#E6F3FF`, dark: `#0070D6`)
- **CTA blue**: `#0061B5` (dark: `#004F94`)
- **Warm accent**: `#FF6B35`
- **Success green**: `#10B981`
- **Text dark**: `#1A1A2E`, body: `#4A4A68`, muted: `#8A8AA3`
- **Page bg**: `#FAFBFF`
- **Fonts**: `"Noto Serif"` (serif headings), `"Inter"` (sans body)

## Code Conventions

- All code lives in `index.html` — HTML structure, Tailwind config, custom CSS (`<style>`), and JS (`<script>`) are co-located
- Tailwind utility-first styling; minimal custom CSS (only for animations and effects)
- Semantic HTML with proper heading hierarchy
- Accessibility: ARIA attributes (`aria-expanded`), focus-visible states, alt text on images
- Responsive: mobile-first using Tailwind breakpoints (`sm:`, `md:`, `lg:`)

## Key JS Behaviors

1. **Scroll reveal** — `IntersectionObserver` on `.reveal` / `.reveal-child` elements (threshold 15%, root margin -40px)
2. **FAQ accordion** — One-at-a-time toggle with chevron rotation
3. **Curriculum accordion** — Independent toggles (multiple can be open)
4. **Nav scroll effect** — Shadow + solid bg added after 10px scroll

## Page Sections (in order)

1. Sticky nav → 2. Hero → 3. Reality of Parenting → 4. Course Benefits → 5. Designed for Busy Parents → 6. What Makes This Different → 7. Who It's For → 8. What You'll Learn → 9. Curriculum (4 modules) → 10. Instructor Bio → 11. FAQ → 12. Final CTA → 13. Footer

## When Editing

- Keep everything in `index.html` — do not split into separate files unless explicitly asked
- Preserve the Tailwind CDN approach; do not add a build step without being asked
- Match existing color tokens and font families from the Tailwind config
- Maintain accessibility (ARIA, semantic HTML, alt text)
- Images are in `assets/assets/` (nested) — use that path in `src` attributes
- No `.gitignore` exists yet; avoid committing OS files like `.DS_Store`
