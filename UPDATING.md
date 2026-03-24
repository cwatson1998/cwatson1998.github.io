# Updating This Site

This file is the short operational checklist for making routine updates to the site at `https://cwatson1998.github.io/`.

## Files You Will Usually Touch

- `_config.yml` for site-wide metadata and behavior.
- `_pages/index.md` for the homepage content.
- `_data/navigation.yml` for the header links.
- `_publications/*.md` for publication entries.
- `_teaching/*.md` for teaching entries.
- `files/` for downloadable PDFs and supporting files.
- `images/` for profile photos and other static assets.

## Typical Update Workflow

1. Edit content.
2. Preview locally with:

   ```bash
   bundle exec jekyll serve -l -H localhost
   ```

3. If you changed JavaScript, rebuild the minified bundle:

   ```bash
   npm run build:js
   ```

4. Run a production-style build check:

   ```bash
   bundle exec jekyll build
   ```

5. Push to GitHub and confirm the published site at `https://cwatson1998.github.io/`.

## Notes

- `old_html_website/` is a legacy archive and is excluded from the Jekyll build.
- The Penn-hosting deployment script is retained only as a legacy/manual fallback; see `DEPLOYMENT.md`.
- `future: true` is enabled, so future-dated entries can appear in the generated site.
