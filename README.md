# Arnab Kumar Pal — personal site

**One single file: `index.html`.** Everything lives inside it — the homepage,
about, projects, resume, all four writing posts, and contact — as panels you
slide through left and right. Nothing else is needed.

- No build step, no dependencies, no folders.
- Styles and scripts are inlined in the file.
- The photos are embedded as data URIs, so the file is fully self-contained
  (the only external request is the Google Fonts stylesheet).

## Hosting it (free)

1. Create a public repo on GitHub — this one is named `qualia`.
2. Upload `index.html` (and the `.nojekyll` file).
3. Repo → **Settings → Pages** → Source: *Deploy from a branch* →
   branch `main`, folder `/ (root)` → **Save**.
4. A minute later it's live at **https://rdxakp.github.io/qualia/**

## How it works

The whole site is one horizontal track. Move through it by dragging, swiping,
the ← → buttons, the arrow keys, or your scroll wheel (up/down moves it
sideways). It snaps panel to panel and the bottom bar shows where you are.

The **↕ Vertical** button (top right) turns the whole thing into a normal
top-to-bottom page — and it switches on by itself for anyone whose device is
set to "reduce motion".

Clicking a picture opens its works list in the drawer on the right.

## Editing it

Open `index.html` in any text editor.

- Each screen is a `<section class="h-panel" id="...">` inside
  `<div class="h-track">`. The panels in order are: index (with the about
  text), projects, resume, writing (with the three pictures), contact.
  Each piece of writing is its own page in `blog/` — the Writing panel
  links out to them.
- The top nav links jump to each panel by id.
- To swap a photo, replace the whole `data:image/jpeg;base64,...` string with
  your own. Keep each one under ~500 KB so the file stays quick to load.
- Colours live in the CSS variables at the top of the `<style>` block —
  change `--accent` and the whole site re-themes.

## Notes

- The `.nojekyll` file just tells GitHub Pages not to run Jekyll. Leave it.
- Because everything is inlined, the file is about 1.4 MB — that's the
  photos. It loads in one request, so it's still fast.
