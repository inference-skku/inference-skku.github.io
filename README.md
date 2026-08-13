# inference-skku.github.io

Website for **Inference Lab**, School of Mechanical Engineering, Sungkyunkwan University.
Served at <https://inference-skku.github.io/>.

## How it works

Plain HTML and one stylesheet. **No build step, no dependencies, no JavaScript.**
Edit a file, commit, push — GitHub Pages serves it. Nothing here can rot between
edits, which is the point: an academic site gets touched a few times a year, and
a toolchain that needs maintenance in between is a liability.

```
index.html         claim, three layers, openings callout, news
research.html      the three layers in full, current program
publications.html  all publications, reverse chronological, tagged by layer
teaching.html      courses, and the route from a course into the lab
join.html          hiring notice: prerequisites, funding, starter projects
style.css          the whole design; light/dark via prefers-color-scheme
demos/             interactive in-class demos — see demos/README.md
```

The five pages are JavaScript-free by design. The demos under `demos/` are the
exception and are deliberately isolated: each is one self-contained file, so a
broken demo can never take a page down with it.

## Editing

**Adding a publication** — copy a `<div class="pub">` block in `publications.html`,
keep reverse-chronological order, wrap your own name in `<span class="me">`, and
tag it `State`, `Function`, `Education` or a new layer.

**Adding news** — add an `<li>` to the `.news` list in `index.html`, newest first.
There is a comment there marking what to update as the CCAI decision and the
JAMES submission land. Do not list a paper as submitted before it is submitted.

**Colours and spacing** — all tokens live at the top of `style.css` under `:root`,
with dark-mode overrides directly beneath. Change them in one place.

## Things still to fill in

- `teaching.html` carries a `TODO` comment: the course *areas* are right, but the
  official titles, codes and semesters need to come from the SKKU catalogue.
- News entries need updating as work lands.

## Local preview

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>. Check both light and dark (change your OS
appearance setting) and a narrow window — the layout is responsive and should
never scroll horizontally.
