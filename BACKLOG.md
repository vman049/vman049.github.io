# Backlog

## Upgrade to minima 3.x

Kills `assets/main.scss` — dark mode becomes `minima: {skin: dark}` in config.
Blocked on leaving GitHub Pages' legacy build, which pins minima 2.5.1.

1. Add `.github/workflows/jekyll.yml`; set Pages source to GitHub Actions.
2. `Gemfile`: drop `github-pages`, add `jekyll ~> 4.3`, `minima ~> 3.0`.
3. Delete `assets/main.scss`, set `minima.skin: dark`.
4. Move `github_username` under `minima.social_links` (3.x syntax).
5. Check About/Resume/posts for drift.
