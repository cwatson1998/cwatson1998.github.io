# Deployment Notes

## Current Production Path

The primary live site is:

- `https://cwatson1998.github.io/`

This repository is the source for that site. In normal usage, publishing happens via GitHub Pages from this repository, not via the Penn web host.

## Penn Hosting Status

The Penn site was previously served from `https://www.seas.upenn.edu/~ccwatson/`, but that path is now legacy. The Penn page currently redirects to the GitHub Pages site.

The script in [`scripts/deploy_public_html.sh`](./scripts/deploy_public_html.sh) is kept only in case you ever want to publish a copy of the generated `_site/` output to Penn hosting again.

## Legacy Manual Deployment

If you ever do want to push the built site to Penn hosting again, the flow is:

```bash
bundle exec jekyll build
scripts/deploy_public_html.sh
```

That script:

1. Builds the site with `JEKYLL_ENV=production`.
2. `rsync`s `_site/` to `ccwatson@eniac.seas.upenn.edu:public_html/`.

Optional overrides:

- `REMOTE=myuser@remote.example.edu scripts/deploy_public_html.sh`
- `REMOTE_PATH=public_html/custom_dir scripts/deploy_public_html.sh`

## Recommended Verification

For current day-to-day work, verify changes locally first:

```bash
bundle exec jekyll serve -l -H localhost
```

Then confirm the live site at `https://cwatson1998.github.io/` after your GitHub Pages publish completes.
