# Liudmyla — notes from the mat

A personal yoga practice journal. Plain HTML, CSS and Markdown, built
automatically by GitHub Pages (Jekyll). No build tools needed to publish.

---

## Putting it on GitHub

1. Create a new repository on GitHub. Two choices:
   - Name it **`<your-username>.github.io`** → the site lives at
     `https://<your-username>.github.io` and `baseurl` in `_config.yml` stays empty.
   - Name it anything else, e.g. **`website`** → the site lives at
     `https://<your-username>.github.io/website` and you must set
     `baseurl: "/website"` in `_config.yml`.

2. From this folder (git is already initialised and the files are staged):

   ```sh
   git commit -m "My yoga journal"
   git remote add origin https://github.com/<your-username>/<repo>.git
   git push -u origin main
   ```

3. On GitHub: **Settings → Pages → Build and deployment → Source: Deploy from a
   branch → Branch: `main` / `/ (root)`** → Save.

4. Wait a minute or two, then open your URL. Every `git push` after that
   republishes the site automatically.

---

## Adding a journal entry

Create one file in `_posts/`. The filename **must** be
`YYYY-MM-DD-some-title.md`:

```markdown
---
title: "Half moon, whole morning"
date: 2026-10-04 07:00:00 +0300
tags: [balance, standing]
place: Home
---

Write whatever you like here, in plain Markdown.

*italic*, **bold**, [a link](https://example.com), and

> a quote, for the line the teacher said that stuck.
```

`tags` and `place` are optional — delete those lines if you don't want them.
Then commit and push; the entry appears on the home page and in `/journal/`.

---

## Editing the rest

| What | File |
|---|---|
| Your name, tagline, site description | `_config.yml` |
| Home page text | `index.html` |
| About page | `about.md` |
| Practice page | `practice.md` |
| Colours, fonts, spacing | `assets/css/style.css` (top of the file) |
| Page shell, nav, footer | `_layouts/default.html` |

**Change your email address** — `about.md` currently says
`you@example.com`.

---

## Previewing locally (optional)

Only if you want to see changes before pushing. Needs Ruby:

```sh
bundle install
bundle exec jekyll serve
```

Then open <http://localhost:4000>. Otherwise just push and look at the live site.
