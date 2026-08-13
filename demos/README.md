# Interactive demonstrations

Self-contained JavaScript demos used in class. Each one is a **single HTML file**
that carries its own script and can be handed to students as a URL:

```
https://inference-skku.github.io/demos/<name>.html
```

## Why they live here and not in the site chrome

The five main pages have no JavaScript at all — they load a single stylesheet and
nothing else, which is why they render instantly and cannot break. Demos are the
opposite kind of artifact: they are all script, they get revised mid-semester, and
one broken demo should never take a page down with it. Keeping them as separate,
self-contained files means a demo can fail without touching anything else.

## Naming

`<course>-<topic>.html`, lowercase, hyphens:

```
fme1-slope-fields.html          Fundamental Mathematics in Engineering I
fme1-phase-portrait.html
fme2-heat-equation.html         Fundamental Mathematics in Engineering II
vi-kl-direction.html            Variational Inference  (the first one, built)
```

## Rules

1. **One file, no dependencies.** Inline the CSS and JS. No CDN, no npm, no build
   step — the rest of the site has none and these should not either. If you need
   a plotting routine, write the twenty lines of canvas code; it will outlive any
   library you would have imported.
2. **Works offline.** A student on a train should be able to open a saved copy.
3. **Responsive and theme-aware.** Reuse the tokens from `../style.css` by copying
   the `:root` block, or link the stylesheet with `<link rel="stylesheet"
   href="../style.css">` and add only what the demo needs on top.
4. **State the question at the top.** A demo without a question is a toy. One
   sentence saying what the reader should look for earns its place.

## Linking a demo from the course page

In `teaching.html`, find the course block and replace the placeholder:

```html
<p class="demos-label">Interactive demonstrations</p>
<p class="demos-empty">Coming soon.</p>
```

with a list:

```html
<p class="demos-label">Interactive demonstrations</p>
<ul class="demos">
  <li><a href="demos/fme1-slope-fields.html">Slope fields and Euler's method</a></li>
  <li><a href="demos/fme1-phase-portrait.html">Phase portraits of linear systems</a></li>
</ul>
```

The `.demos` and `.demos-label` styles are already in `style.css`.
