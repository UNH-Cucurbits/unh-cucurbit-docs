# Cucurbit Lab Docs

Internal documentation for the UNH Cucurbit Breeding & Genetics Program, built with [Quarto](https://quarto.org) and published on GitHub Pages.

## Preview locally

```bash
quarto preview
```

## Layout

```
_quarto.yml              site config (title, navbar, sidebar, theme)
index.qmd                home page
getting-started/         one folder per sidebar section;
breedbase/                 each has an index.qmd (section landing page)
naming/
protocols/
computing/
contributing/            how to edit the site + Quarto syntax cheat sheet
_templates/page.qmd      copy this to start a new page (not rendered)
assets/                  light.scss, dark.scss (colors), custom.scss (shared rules)
.github/workflows/       GitHub Action that publishes on push to main
```

The sidebar is generated from the folders. Each page's `order:` field sets its position, so adding a page never requires editing `_quarto.yml`.

## One-time setup

1. Replace the `YOUR-ORG/YOUR-REPO` placeholders in `_quarto.yml` (three spots).
2. Push the repo to GitHub.
3. Run this once from your own computer. It creates the `gh-pages` branch and a `_publish.yml` file; commit `_publish.yml`.
   ```bash
   quarto publish gh-pages
   ```
4. In the repo, go to **Settings > Pages** and set the source to **Deploy from a branch**, branch `gh-pages`, folder `/ (root)`.

From then on, every push to `main` re-renders and publishes the site.

If the Action fails with a permissions error, check **Settings > Actions > General > Workflow permissions** and allow read and write.

## Filling in the stubs

Every section page starts as a stub with headings and a "Draft" note. Delete the note once a page is written, and delete stub pages you don't need. The page title comes from `title:` in the YAML header, so don't also start the page with a `#` heading.

## Changing the look

- Colors: `$primary` in `assets/light.scss` and `assets/dark.scss`
- Shared styling (home page cards, headings): `assets/custom.scss`
- Base themes are Bootswatch Flatly (light) and Darkly (dark), set in `_quarto.yml`
