# archievizt.github.io

My portfolio. Jekyll with the Minimal theme, built and hosted by GitHub Pages.

- Home page: https://archievizt.github.io
- CV: https://archievizt.github.io/cv.html

## What lives where

- `index.md` is the home page: about, certifications, projects, tech stack, contact.
- `_data/cv.yml` holds everything on the CV page. Edit the CV there.
- `cv.html`, `_layouts/cv.html`, and `assets/css/cv.css` lay out the CV page.
- `_includes/security-headers.html` holds the Content Security Policy for every page.
- `_includes/safe-url.html` checks every link that comes from `_data/cv.yml`.
- `_config.yml` holds the name, sidebar text, site address, and theme.
- `_layouts/default.html` is the Minimal theme layout, hardened and with a tidier footer.
- `assets/css/style.scss` adds the small home page touches (ID block, status dot, tag chips).
- `netops-automation/` is the netops-automation field report, a standalone page with its own stylesheet and Content Security Policy.
- `assets/cv.pdf` is optional. Add it and a PDF link appears on the CV page.
- `SECURITY.md` says how to report a security problem; `.env.example` is the template for local settings.

## Editing in the browser

Open a file, click the pencil icon, change the text, then click Commit changes. The site updates within a few minutes.

In `_data/cv.yml`, keep each line of text inside double quotes, indent with spaces (never tabs), and keep the `- ` at the start of each bullet. The full rules are at the top of that file.

## Security

- No secrets live here and none are needed. Never commit keys, passwords, or tokens. For a local setting, copy `.env.example` to `.env`: git ignores `.env`, and Jekyll never publishes files starting with a dot.
- Every page carries a Content Security Policy. The site runs no JavaScript and loads nothing from other domains, so an injected script, outside image, or form is refused by the browser. Adding a script or outside service means allowing it in `_includes/security-headers.html` first.
- Everything from `_data/cv.yml` is HTML-escaped, and CV links must start with `https://`, `mailto:`, or `/`, or they show as plain text.
- This repository is public. Keep personal details to what you mean to publish, and strip location data from photos before adding them.
- There are no GitHub Actions workflows. If you add one, set `permissions: contents: read` at the top and pin every action to a full commit SHA.
- Keep Dependabot alerts and push protection on (Settings, Advanced Security).

## Preview locally (optional)

```
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve
```

Then open http://127.0.0.1:4000. The preview only listens on your own computer; don't add `--host 0.0.0.0` on a shared network. Commit the `Gemfile.lock` that `bundle install` creates, so versions stay pinned.
