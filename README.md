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

## Adding a monthly entry

1. Create `_posts/YYYY-MM-DD-slug.md` (the date in the filename is required).
2. Front matter at the top:

   ```yaml
   ---
   layout: post
   title: "Your title"
   ---
   ```

3. Write Markdown below it.
4. `git add . && git commit -m "post: your title" && git push`

The site rebuilds automatically within a minute. Work-in-progress lives in
`_drafts/` and is not published until moved into `_posts/` with a dated filename.

## Pages

- `about.md` — About
- `resume.md` — Resume (drop a PDF at `assets/files/resume.pdf` for the download link)
- `_config.yml` — title, tagline, nav order, social links
