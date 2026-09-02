# Backlog

Ideas and deferred work for this site. Listed in `exclude` in `_config.yml`,
alongside `README.md`, so it is never copied into the built site.

---

## Upgrade to minima 3.x to simplify the styling

**Status:** deferred · **Opened:** 2026-09-01

### Why

The site currently runs **minima 2.5.1**, which is what GitHub Pages' legacy
build pipeline pins. That version hard-codes its colours and has no theming
support, so dark mode is hand-rolled: `assets/main.scss` imports minima and
then restates its entire palette as CSS custom properties in order to override
it.

Minima 3.x ships **skins** natively. The whole of `assets/main.scss` would
collapse to one line of config:

```yaml
minima:
  skin: dark    # also: auto, classic, solarized, ...
```

The same version gap already bit us once: `_config.yml` originally declared the
GitHub link using minima 3.x's `minima.social_links` syntax, which 2.5.1 ignores
outright — the footer social list rendered empty and nobody noticed. On 3.x that
config would simply have been correct.

### What it involves

GitHub Pages' legacy pipeline won't do this; it only builds the frozen gem set.
The upgrade means moving to a **GitHub Actions** build:

1. Add `.github/workflows/jekyll.yml` (the standard `actions/jekyll-build-pages`
   flow), and switch the repo's Pages source from "Deploy from a branch" to
   "GitHub Actions".
2. Replace `gem "github-pages"` in the `Gemfile` with `gem "jekyll", "~> 4.3"`
   and `gem "minima", "~> 3.0"`.
3. Delete `assets/main.scss` and set `minima.skin` instead.
4. Move `github_username` back under `minima.social_links` (3.x syntax).
5. Re-check the About and Resume pages and any published posts for layout drift.

### Why it's deferred

The current setup works and needs zero maintenance — GitHub patches the pinned
gems. Switching to Actions means owning the dependency set and a build workflow,
in exchange for deleting a stylesheet that is already written and working.

Worth doing if we ever want newer Jekyll features, another skin, or find
ourselves fighting 2.5.1's styling again.
