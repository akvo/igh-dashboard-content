# IGH Dashboard — Content Repo

This repo holds the editable text for the IGH dashboard. Each piece
of copy lives as its own file, organised by page-folder.

## Editing content

1. Find the page folder for the screen you want to edit
   (`home/`, `analytical_insights/`, `portfolio_analysis/`,
   `cross_pipeline_analytics/`, `who_priority/`, or `layout/`).
2. Click into the file for the specific text. Filenames preserve the
   dotted key (e.g. `hero.title.txt`).
3. Click the pencil icon (top-right of the file view).
4. Edit the text.
5. Scroll down, write a short commit message (optional but
   encouraged), and click "Commit changes" → "Commit directly to the
   `main` branch".

The staging dashboard updates within ~1 minute.

## When something doesn't update

1. Open this repo's **Actions** tab.
2. If the most recent run has a red X, click into it — the error
   tells you what's wrong (usually a length limit or the wrong file
   extension for a markdown key).
3. Fix the file (edit + commit again). The next run publishes if it
   passes.

If the run is green but staging still hasn't updated, ask a developer
to trigger `workflow_dispatch` on the dashboard repo's
`content-sync.yml`.

## File extensions

- `.txt` — plain text.
- `.md` — markdown, rendered as formatted text on the site.

The expected extension for each key is defined in `schema.json` —
**do not edit `schema.json`**; it's managed by the sync bot.

## What NOT to edit

Managed by the dev team or automated scripts; the next sync will
overwrite changes to these:

- `schema.json`
- `package.json`, `package-lock.json`
- Anything under `scripts/`
- Anything under `.github/`
