# 2D Raumplaner — SEO Landing Page

## Architecture

Single-file approach: each page is a self-contained `index.html` with shared CSS.

```
project-root/
├── index.html              ← Complete page (header + main + footer)
├── css/
│   ├── global.css          ← Shared styles: reset, typography, header, footer, layout, buttons, icons, tables, FAQ
│   └── 2d-raumplaner.css   ← Page-specific styles for this landing page
└── README.md               ← This file
```

## Key Design Decisions

- **Dark theme** inspired by smsactivate.biz — dark navy backgrounds (#0b0f1a, #111827), blue accent (#3b82f6)
- **Font**: DM Sans via Google Fonts (loaded in `<head>`)
- **No JavaScript**: Pure HTML/CSS. FAQ uses `<details>/<summary>`. Mobile nav uses CSS checkbox hack.
- **All icons**: Inline SVG with `currentColor` and `aria-hidden="true"`
- **Semantic HTML**: `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<footer>` — no generic `<div>` wrappers for content blocks
- **Mobile-first**: Single breakpoint at 768px, max content width 800px (1100px wide sections)

## Schema Markup

The `<head>` includes four JSON-LD blocks:

1. **SoftwareApplication** — defines the tool
2. **HowTo** — the 5-step tutorial
3. **FAQPage** — mirrors the visible FAQ section
4. **BreadcrumbList** — navigation path

## Image Placeholders

All images use `<div class="img-placeholder">` with descriptive text and an AI image generation prompt inside `<em>` tags. Replace these with actual `<img>` elements when images are ready.

## How to Add a New Landing Page

1. Create a directory: `mkdir new-page-slug/`
2. Copy `index.html` into it — update `<head>` metadata (title, description, canonical, OG, JSON-LD)
3. Update the `<main>` content blocks
4. Create `css/new-page-slug.css` for page-specific styles
5. Update the CSS link in `<head>`: `<link rel="stylesheet" href="/css/new-page-slug.css">`
6. Header and footer markup is repeated in each page — update both if site-wide changes are needed

### Multi-page structure example:

```
project-root/
├── index.html
├── 3d-raumplaner/
│   └── index.html
├── kuchenplanung-online/
│   └── index.html
├── css/
│   ├── global.css
│   ├── 2d-raumplaner.css
│   ├── 3d-raumplaner.css
│   └── kuchenplanung-online.css
└── README.md
```

## Content Checklist

- [x] Target keyword "2D Raumplaner" in H1, meta title, meta description, 2+ H2s
- [x] All 19 core entities from the brief addressed
- [x] Semantic triples expressed (Raumplaner → erstellt → Grundriss, etc.)
- [x] FAQ with 7 questions matching FAQPage schema
- [x] HowTo schema for 5-step tutorial
- [x] SoftwareApplication schema
- [x] CTA buttons link to raum-planer-online.de
- [x] Navigation links to internal page sections
- [x] German language throughout (`lang="de"`)
