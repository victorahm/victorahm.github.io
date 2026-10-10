# AGENTS.md

Guidance for AI agents working on this repository.

## What this repo is

Victor Herrera's personal website: one static page with basic information
(about, experience, knowledge, interests, contact). It is published with GitHub
Pages from the `main` branch, root directory.

- Site: https://victorahm.github.io
- Issue tracker: https://redmine.obsidianasystems.com/projects/personal-website

## Ground rules

- **This is a deliberately simple site.** Do not introduce a framework, bundler,
  package manager, build step or SSG unless the user explicitly asks for one.
- Everything is in a single file: `index.html`. Keep it that way unless the user
  asks for a split.
- **No invented facts.** Never add employers, job titles, dates, degrees, projects
  or skills that the user has not provided. If a section needs real details you
  don't have, ask, or leave a clearly marked placeholder in the PR description.
- Match the existing style: semantic HTML, plain CSS with custom properties,
  no external assets (no CDNs, fonts, analytics or trackers).
- Do not commit or push unless the user explicitly asks.

## Layout

```
index.html   # the entire site: <style> block in <head>, sections in <body>
README.md    # repo description, local dev, publishing, editing notes
AGENTS.md    # this file
```

## Structure of index.html

1. `<head>` — meta, title, description, and a single `<style>` block that defines
   CSS variables in `:root` (light) and a dark palette under
   `@media (prefers-color-scheme: dark)`.
2. `<header>` — name (h1), tagline, short intro and in-page `<nav>`.
3. `<main>` — one `<section id="...">` per topic:
   `about`, `experience`, `knowledge`, `interests`, `contact`.
4. `<footer>` — copyright with a tiny inline script setting the current year.

Conventions:

- Section headings: `<h2>`; items inside a section: `.item` with `h3`, `.meta`,
  paragraph.
- Skill list uses `<ul class="tags">` (pill-style chips).
- Internal links target section ids; keep `nav` in sync when adding a section.
- External links get `rel`-safe plain `<a href>`; internal anchors use `#id`.

## Content checklist before a PR

- Title, meta description and header name match the site owner.
- All `nav` links point at existing section ids.
- Page renders at 360 px width and on desktop; light and dark scheme both look OK.
- No placeholder text (like `Lorem ipsum` or `TODO`) left behind unless it was the
  point of the PR.
- HTML validates reasonably (balanced tags, quoted attributes, `lang` attribute set).

## Verification

There is no test suite. Verify by opening the page:

```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

Check the browser console for errors and resize the window to confirm responsiveness.
If only markup changed, a quick visual check is enough.

## Git / PR workflow

- Branch from `main`, one logical change per PR.
- Reference the tracking issue (Redmine project `personal-website`) in the PR body.
- Never push directly to `main`.
