# Victor Herrera — Personal Website

A single-page personal site with basic information about me: experience, knowledge
and interests. Plain HTML + CSS, no build step, no framework.

Published with [GitHub Pages](https://pages.github.com/) at
**https://victorahm.github.io**.

## Contents

| File | Purpose |
|------|---------|
| `index.html` | The whole site: markup, styles and a tiny script for the copyright year. |
| `README.md` | This file — what the repo is and how to work on it. |
| `AGENTS.md` | Guidance for AI agents contributing to this repo. |

## Local development

There is nothing to build or install. Open the file directly:

```bash
open index.html        # macOS
xdg-open index.html    # Linux
```

Or serve it locally:

```bash
python3 -m http.server 8000
# http://localhost:8000
```

## Publishing

The site is served by GitHub Pages from the `main` branch (root). After merging a PR,
Pages rebuilds automatically — no manual deploy step.

## Editing the content

All content lives in `index.html`:

- **Header:** name, tagline and short intro.
- **About / Experience / Knowledge / Interests / Contact:** one `<section>` each.
- **Styles:** the `<style>` block in `<head>`; uses CSS variables, including a
  dark-mode palette via `prefers-color-scheme`.

## Contributing

1. Create a branch.
2. Make your change.
3. Check the page locally in a browser (desktop + narrow width).
4. Open a pull request.

## License

Content and code in this repository are © Victor Herrera.
