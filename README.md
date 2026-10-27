# a-debow.github.io

Personal academic website of **Ahmad Debow**: AI & security, cloud-native engineering, publications and projects.

**Live site:** https://a-debow.github.io

## How this repository is organised

| Path | What it is |
|------|------------|
| `docs/` | **The published website.** GitHub Pages serves this folder (Settings → Pages → *Deploy from a branch*, `main`, `/docs`). |
| `_pages/`, `_projects/`, `_data/`, `_bibliography/` | Content sources (pages, project write-ups, CV/work data, publications). |
| `_layouts/`, `_includes/`, `_sass/`, `assets/` | Theme ([al-folio](https://github.com/alshedivat/al-folio)) templates, styles, images and PDFs. |
| `_config.yml` | Site settings. |

## Updating the site

1. Edit the content files (`_pages/`, `_projects/`, `_data/`, …).
2. Build locally with Docker:
   ```bash
   docker compose up        # preview at http://localhost:8080
   ```
   or with Ruby: `bundle exec jekyll build`.
3. Replace the published copy with the fresh build:
   ```bash
   JEKYLL_ENV=production bundle exec jekyll build
   rm -rf docs && cp -r _site docs && touch docs/.nojekyll
   ```
4. Commit and push. GitHub Pages updates within a minute or two.

> `docs/` and `site/` are excluded in `_config.yml`, so a build never copies the old site into the new one.

## License

Theme: [al-folio](https://github.com/alshedivat/al-folio) (MIT, see `LICENSE`). Content © Ahmad Debow.
