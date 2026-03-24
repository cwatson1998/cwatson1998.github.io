# Christopher Watson Website

This repository contains the source for `https://cwatson1998.github.io/`.

It is a Jekyll site built on top of the Academic Pages template, but this README is intended to describe how this specific repo works now rather than the upstream template in general.

## What Actually Renders the Site

- The homepage is [`_pages/index.md`](./_pages/index.md). It has `permalink: /`, so it becomes the root URL.
- Site-wide metadata and behavior live in [`_config.yml`](./_config.yml).
- The top navigation is defined in [`_data/navigation.yml`](./_data/navigation.yml).
- Shared HTML structure lives in [`_layouts/`](./_layouts/) and [`_includes/`](./_includes/).
- Styles live in [`_sass/`](./_sass/) and [`assets/css/`](./assets/css/).
- JavaScript source lives in [`assets/js/_main.js`](./assets/js/_main.js) and is bundled into [`assets/js/main.min.js`](./assets/js/main.min.js).

## Content Model

- [`_pages/`](./_pages/) contains standalone pages like the homepage, publications index, and teaching index.
- [`_publications/`](./_publications/) contains one Markdown file per publication.
- [`_teaching/`](./_teaching/) contains one Markdown file per course or TA entry.
- [`_talks/`](./_talks/) and [`_portfolio/`](./_portfolio/) are available collections, though they are not prominent in the current nav.
- [`files/`](./files/) contains downloadable PDFs and other static attachments.
- [`images/`](./images/) contains profile photos, icons, and other static media.

## Local Development

Install dependencies once:

```bash
bundle install
npm install
```

Run the local preview:

```bash
bundle exec jekyll serve -l -H localhost
```

Open `http://localhost:4000`.

If you change JavaScript under `assets/js/`, rebuild the minified bundle:

```bash
npm run build:js
```

You can also use Docker:

```bash
docker compose up
```

## Deployment

The live site is served from GitHub Pages at `https://cwatson1998.github.io/`.

The Penn site currently redirects to the GitHub Pages site, so the Penn deployment flow is not the primary publishing path anymore. Legacy Penn-hosting notes are kept in [`DEPLOYMENT.md`](./DEPLOYMENT.md).

## Notes And Caveats

- `old_html_website/` is a legacy copy of an older site and is excluded from the Jekyll build.
- `future: true` is enabled in [`_config.yml`](./_config.yml), so future-dated content can appear in builds.
- There is a GitHub Actions workflow for regenerating talk-map data, but not a custom deployment workflow in this repo.
