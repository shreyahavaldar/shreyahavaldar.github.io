# shreyahavaldar.com

Single-page personal site. Plain static HTML — no build step, no Jekyll, no dependencies.

```
index.html          the entire site (markup + CSS + a few lines of JS)
CNAME               custom domain for GitHub Pages
.nojekyll           tells Pages to serve files as-is, skipping the Jekyll build
images/shreya.jpeg  portrait
images/leaf.png     favicon
files/              CV
```

## Editing

Everything lives in `index.html`.

- **Colors** — the `:root` block at the top of the `<style>` tag. Dark mode is the
  `[data-theme="dark"]` block right below it. The palette follows one rule:
  dark green = links, sage = structure (rules, dates, venues), terracotta =
  awards and hover, charcoal = text and headings.
- **News** — add an `<li>` at the top of `<ul class="news">`. Items marked
  `class="extra"` are hidden behind the "Show earlier news" button; move the
  class down the list as new items are added to keep ~5 visible. Each item gets a
  category emoji: 🌎 conference travel · 🎉 award/milestone · 📝 paper ·
  📚 invited talk or new role.
- **Publications** — copy an existing `<li>` in `<ul class="pubs">`. Wrap your own
  name in `<span class="me">` and use `<span class="award">` for awards. Prefer
  ACL Anthology links over arXiv where the paper is published.
- **CV** — drop the new PDF in `files/` and update the link in the header.

Two values must stay in sync: `.wrap { max-width }` and the `440px` in the theme
toggle's `right: max(...)` calc, which is half of it. The toggle drifts into the
text column otherwise.

## Preview locally

```sh
python3 -m http.server 8000
# then open http://localhost:8000
```

Open `index.html` directly and it mostly works, but Safari blocks `localStorage`
on `file://`, so the dark-mode toggle won't remember your choice.

## Deploy (GitHub Pages)

Push to the root of `shreyahavaldar.github.io`, then Settings → Pages →
Build from branch → `main` / `/ (root)`.

`CNAME` and `.nojekyll` must be committed — Pages reads both from the repo root.
DNS is managed in Squarespace: four A records on the apex pointing at GitHub's
`185.199.108–111.153`, and a `www` CNAME to `shreyahavaldar.github.io`.
