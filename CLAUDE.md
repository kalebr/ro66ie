# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Production Matters** is a Jekyll static blog focused on game development production — process, people, and the business of games. It targets producers who want results-oriented insights into optimizing game development cycles.

## Commands

```bash
# Install dependencies
bundle install

# Start local dev server with live reload (http://localhost:4000)
bundle exec jekyll serve

# Build static site to _site/
bundle exec jekyll build

# Update gems
bundle update
```

There are no test or lint commands — this is a content/static site project.

## Architecture

This is a standard [Jekyll 4](https://jekyllrb.com/) site using the **Minima 2.5** theme.

- **`_posts/`** — Blog posts, named `YYYY-MM-DD-slug.md`. Each post requires Jekyll front matter (layout, title, date, categories).
- **`_config.yml`** — Site-wide configuration: title, email, description, theme, and plugins.
- **`_site/`** — Generated output (gitignored; never edit directly).
- **`index.markdown` / `about.markdown`** — Top-level pages using Jekyll front matter.

Active plugins: `jekyll-feed` (RSS at `/feed.xml`) and `jekyll-seo-tag` (via Minima theme).

## Content

Posts live in `_posts/` and use this front matter pattern:

```yaml
---
layout: post
title: "Post Title"
date: YYYY-MM-DD HH:MM:SS -0500
categories: jekyll update
---
```

## Platform Notes

Development is on Windows. The Gemfile includes `wdm` (Windows file watching) and `tzinfo-data` (timezone support). These are required for `jekyll serve --watch` to work on Windows.

`_config.yml` is **not** reloaded automatically by `jekyll serve` — restart the server after any config changes.
