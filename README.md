# vman049.github.io

Personal blog — practitioner's notes on LLM post-training. Built with Jekyll,
served by GitHub Pages at <https://vman049.github.io>.

## Writing a post

Add a file to `_posts/` named `YYYY-MM-DD-title.md` with front matter:

```yaml
---
layout: post
title: "Your Title"
date: 2026-06-21
---
```

Push to `main` and GitHub Pages rebuilds automatically (~1 min). Drafts live in
`_drafts/` (no date prefix) and don't publish.

## Local preview (optional)

```bash
bundle install
bundle exec jekyll serve --drafts
# http://localhost:4000
```
