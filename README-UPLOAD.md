# Minnette Johnson — MSSE portfolio files

This bundle keeps `index.md` as the homepage, as required by the assignment, while using a Jekyll layout and separate CSS file for the styled design.

## Upload to the repository root

Upload or replace these paths in `minnettejohnson-dot/msse-portfolio`:

- `_config.yml`
- `index.md`
- `_layouts/default.html`
- `assets/css/style.css`
- `favicon.svg`

Keep your existing `msse601/` folder and decision record. Keep your personal photo in the repository root with the exact filename `minnette.jpg`.

## Important

- Do **not** upload the old full-document `index.html` from the earlier version. The assignment homepage is `index.md`.
- If GitHub currently has an `index.html` that contains the old full page, you can remove it after backing it up. The Jekyll `index.md` is the intended homepage for this setup.
- The page links to `msse601/MSSE601-ADR-hybrid-architecture.html`, which Jekyll normally generates from `msse601/MSSE601-ADR-hybrid-architecture.md`. If your decision record has a different filename, update that link in `index.md`.
- `_config.yml` uses `url: https://minnettejohnson-dot.github.io` and `baseurl: /msse-portfolio`, so the stylesheet, favicon, and portrait links work on the project site.

## Suggested upload method

From the repository page on GitHub, choose **Add file → Upload files** and upload these files while preserving the folder paths. GitHub's web uploader may not automatically create nested directories in all workflows; if needed, create `_layouts/default.html` and `assets/css/style.css` with **Add file → Create new file** and paste the corresponding contents from the bundle.
