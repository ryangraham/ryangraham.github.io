# Astro Blog Design

Date: 2026-01-02

## Overview

Build a new static blog using Astro with Content Collections. Posts are Markdown files in
`src/content/blog/`. The site uses a warm, personal design with a hero and recent posts on
the home page, a paginated blog index, and individual post pages.

## Architecture

- Generator: Astro
- Content: Markdown in `src/content/blog/` with Content Collections schema (Zod validation).
- Routes:
  - `/` home with hero + recent posts list
  - `/blog` paginated index (e.g., `/blog/1`, `/blog/2`)
  - `/blog/[slug]` post detail
- Data flow: `getCollection('blog')` sorted by date desc and sliced for lists.

## Components and Layout

- `BaseLayout.astro`: HTML shell, header (site title + Blog link), footer.
- `PostLayout.astro`: post wrapper (title, date, description, content).
- `PostList.astro`: reusable list for home + index.
- `Pagination.astro`: page navigation for index.
- Home hero with short intro; recent posts list below.
- Styling:
  - CSS variables for palette (warm, personal theme).
  - Typography: serif headings, readable sans body.
  - Subtle gradient/texture background, generous spacing.
  - Responsive content width, Markdown element styles.
  - Code blocks: contrasting background + rounded corners.
  - Images: responsive by default.

## Data, Errors, Testing

- Build-time validation: required frontmatter (title, date, description), optional tags.
- Build fails on invalid frontmatter with clear errors.
- Add a simple 404 page for missing routes.
- Manual verification checklist:
  - `astro build` succeeds
  - Home shows latest posts
  - Pagination links work
  - Post renders images + code blocks correctly

