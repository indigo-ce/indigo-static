# Indigo Static

A starter template for static sites, blogs, and landing pages — the static counterpart of [indigo-fullstack](../indigo-fullstack). Built with Astro, Tailwind CSS 4, content collections, and type-safe i18n. Fully static output; deploy to any static host.

## Features

- **Astro** static output — plain HTML in `dist/`, no server required
- **Content collections** — Markdown/MDX blog with zod-validated frontmatter
- **Type-safe i18n** — `en` (default, unprefixed) and `ja`, translations checked at compile time
- **Token-based theming** — semantic color tokens, light/dark mode, no flash on load
- **Self-hosted fonts** — Inter variable font via Astro's fonts API, no font CDN
- **RSS** at `/feed.xml`, **sitemap** at `/sitemap-index.xml`, SEO meta in `BaseLayout.astro`
- **MDX** support in pages and posts

## Quick Start

```bash
pnpm install
pnpm dev        # localhost:4321
```

Then make it yours:

1. Set `site` in `astro.config.mjs` and `Sitemap:` in `public/robots.txt` to your production URL.
2. Update `src/consts.ts` (site title, description, author).
3. Translate UI strings in `src/translations/`.
4. Replace the sample posts in `src/content/blog/`.
5. Rebrand the theme in `src/styles.css` — see `skills/indigo-theming/SKILL.md`.

## Commands

| Command             | Action                                 |
| ------------------- | -------------------------------------- |
| `pnpm dev`          | Start dev server at `localhost:4321`   |
| `pnpm build`        | Build the static site to `./dist/`     |
| `pnpm preview`      | Build, then preview the output locally |
| `pnpm check`        | Run Astro/TypeScript diagnostics       |
| `pnpm format`       | Format all files with Prettier         |
| `pnpm format:check` | Verify formatting without writing (CI) |

## Project Structure

```
src/
├── components/     # Header, Footer, ThemeSelect, LanguagePicker, Card…
├── content/blog/   # Blog posts (Markdown/MDX)
├── i18n/           # Locale constants and helpers
├── layouts/        # BaseLayout (SEO head), PageLayout, BlogPost
├── lib/            # Theme utilities
├── pages/
│   ├── [...lang]/  # Localized pages (rendered once per locale)
│   ├── blog/       # Blog index + post routes (default locale)
│   ├── 404.astro   # Static-host 404
│   └── feed.xml.ts # RSS feed
├── scripts/        # Client-side language detection/redirect
├── styles.css      # All theme variables (theming lives here)
└── translations/   # en.json, ja.json
```

## Skills

Procedural guides for agents and humans live in `skills/`:

- `skills/indigo-theming/SKILL.md` — the theming system: palettes, semantic tokens, dark mode, fonts, rebranding
- `skills/indigo-i18n/SKILL.md` — translation files, localized pages, locale-aware URLs, adding a language
