# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this is

Personal academic/portfolio website for Sung Ju (Thomas) Lee, built with **Jekyll** using the **Minimal Mistakes** theme pulled in as a `remote_theme` (not vendored — the theme source is not in this repo). Deployed via **GitHub Pages** at `https://thomas11809.github.io/personal-website` (note the `/personal-website` `baseurl`). There is no CI workflow; GitHub Pages builds the `master` branch automatically on push using the `github-pages` gem.

## Commands

```bash
bundle install                 # install gems (first time / after Gemfile changes)
bundle exec jekyll serve       # local dev server with live reload at http://localhost:4000/personal-website
bundle exec jekyll build       # build static site into _site/
```

Note: `_config.yml` is NOT reloaded by `jekyll serve` — restart the server after editing it.

## Structure & conventions

- `_config.yml` — site-wide settings: title, author sidebar/footer links, theme skin (`air`), pagination, plugins, and Jekyll `defaults` that auto-apply layout/front-matter to all `_posts` and `_pages`. Most "global" changes (nav author bio, social links, default post options) live here, not in templates.
- `_data/navigation.yml` — top nav bar (`main:` list). The CV link points to a Google Drive URL.
- `_pages/` — standalone pages, each with a `permalink`. Included in the build via the `include: [_pages]` setting. `home.md` uses `layout: splash` and is the site root (`permalink: /`); `projects.md` uses `layout: archive` and auto-lists posts by category (`Start-up`, `Media Art`) via Liquid + the theme's `archive-single.html` include, so newly published posts appear automatically; `research.md` (`layout: archive`) is a hand-maintained publication list; `blog.md` (`layout: posts`) lists all posts. `category-archive.md` (`/categories/`) and `tag-archive.md` (`/tags/`) are theme-driven liquid archives.
- `_posts/` — blog/portfolio entries named `YYYY-MM-DD-Title.md`. Posts are grouped via `categories:` (e.g. `Start-up`, `Media Art`) and `tags:`; the Projects page lists them from `site.categories`. Use `<!--more-->` with `excerpt_separator` for excerpts, and the theme's `gallery:` front-matter + `{% include gallery %}` for image grids.
- `_drafts/` — unfinished posts (no date prefix in filename). Excluded from the normal build; preview with `bundle exec jekyll serve --drafts`. To publish, fill out the content and `git mv` the file into `_posts/` with a `YYYY-MM-DD-` prefix.
- `assets/images/` — media for posts, organized by project (e.g. `assets/images/Airus/<project>/`). Posts reference these by absolute path (`/assets/images/...`); Jekyll prepends `baseurl` automatically for theme helpers but raw markdown links must account for `baseurl` when needed.

## Editing guidance

- Layouts, includes, and SCSS come from the remote theme and are not present locally — to override them you must add the corresponding file (e.g. `_layouts/`, `_includes/`, `_sass/`) to shadow the theme's version. Do not assume a template exists in-repo.
- When adding a new post, match the existing front-matter pattern (`title`, `layout: single`, `excerpt_separator`, `categories`, `tags`) so it slots into the existing archives and `defaults`.
- `Gemfile.lock` and `_site/` are gitignored.
