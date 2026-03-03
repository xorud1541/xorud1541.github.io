# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Astro 5 static blog deployed to GitHub Pages at https://xorud1541.github.io. Uses the Astro Blog starter template with MDX and sitemap integrations.

## Commands

- `npm run dev` — Start dev server (localhost:4321)
- `npm run build` — Production build to `./dist/`
- `npm run preview` — Preview production build locally

## Architecture

- **Content**: Blog posts live in `src/content/blog/` as `.md` or `.mdx` files. The content collection schema is defined in `src/content.config.ts` — frontmatter requires `title`, `description`, `pubDate`, and optionally `updatedDate` and `heroImage`.
- **Pages**: File-based routing in `src/pages/`. Blog listing at `/blog/`, individual posts via `src/pages/blog/[...slug].astro`, RSS feed at `src/pages/rss.xml.js`.
- **Layouts**: `src/layouts/BlogPost.astro` wraps blog post content.
- **Components**: Shared UI in `src/components/` (BaseHead, Header, Footer, FormattedDate, HeaderLink).
- **Global config**: Site title and description constants in `src/consts.ts`.
- **Styles**: Global CSS in `src/styles/global.css`.
- **Deployment**: Pushes to `main` trigger `.github/workflows/deploy.yml` which builds and deploys to GitHub Pages (Node 20).
