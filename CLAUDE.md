# CLAUDE.md

This file provides guidance to kscc (claude.ai/code) when working with code in this repository.

## Build Commands

```bash
# Serve locally with live reload
hugo server

# Build the static site (output to public/)
hugo

# Serve including drafts
hugo server --buildDrafts

# Create a new post
hugo new post/YYYY-MM-DD-slug/index.zh_hans.md
```

Requires Hugo Extended >= 0.157.0.

## Architecture

Hugo static blog using **hugo-theme-stack v4** as a git submodule at `themes/hugo-theme-stack/`. The project follows a **theme-only architecture**: no custom layouts, assets, or static files — all presentation is delegated to the theme. Site-level customization is done exclusively through `hugo.toml`.

## Content Structure

- Bilingual blog: **Simplified Chinese** (`zh_hans`, primary, weight 1) and **English** (`en`, weight 2)
- Posts are **page bundles** under `content/post/YYYY-MM-DD-slug/` with `index.zh_hans.md` and `index.en.md`
- Images are co-located inside each post's page bundle directory
- Front matter uses **TOML** (`+++` delimiters) with fields: `date`, `title`, `tags`
- Standalone pages (archives, search) live under `content/page/`
- Permalinks: posts use `/p/:slug/`, pages use `/:slug/`

## Theme Customization

Available theme shortcodes: `bilibili`, `gitlab`, `quote`, `tencent`, `video`, `youtube`. Render hooks exist for blockquote, mermaid, heading, image, and link. Theme defaults are in `themes/hugo-theme-stack/config/_default/params.toml`.

## Deployment

Repo name suggests GitHub Pages intent, but no CI/CD workflow is configured yet.
