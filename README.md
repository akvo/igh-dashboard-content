# IGH Dashboard Content Repo

This repo holds the editable text for the IGH dashboard. Each piece
of copy lives as its own file, organised by page-folder.

## Editing content

1. Find the page folder for the screen you want to edit. The folders
   listed at the top of this repo are named after the dashboard's
   pages: `home/`, `pipeline_explorer/`, `who_priority/` and so on.
   Two are not pages. `layout/` holds the text that appears on every
   screen (header, sidebar, footer), and `guided_tour/` holds the
   walkthrough.
2. Click into the file for the specific text. Filenames preserve the
   dotted key (e.g. `hero.title.txt`).
3. Click the pencil icon (top-right of the file view).
4. Edit the text.
5. Click the green "Commit changes..." button at the top right of the
   editor. In the box that opens, optionally write a short message,
   leave "Commit directly to the `main` branch" selected, and confirm.

The staging dashboard updates within ~1 minute.

## When something doesn't update

1. Open this repo's Actions tab.
2. If the most recent run has a red X, click into it. The error tells
   you what's wrong, usually a length limit or the wrong file
   extension for a markdown key.
3. Fix the file (edit + commit again). The next run publishes if it
   passes.

If the run is green but staging still hasn't updated, ask a developer
to trigger `workflow_dispatch` on the dashboard repo's
`content-sync.yml`.

## File extensions

- `.txt` is plain text.
- `.md` is markdown, rendered as formatted text on the site.

`schema.json` sets the expected extension for each key. **Do not edit
`schema.json`**; the sync bot manages it.

## What NOT to edit

The dev team and automated scripts manage these files. The next sync
overwrites anything you change in them:

- `schema.json`
- `package.json`, `package-lock.json`
- Anything under `scripts/`
- Anything under `.github/`

## Deleting or adding files

Deleting a content file does not remove that piece of copy. The next
sync just writes the file back with its last known text. If you want
a piece of copy gone for good, ask a developer to remove its key from
the dashboard's `content.yaml`.

Adding a new `.txt` or `.md` file inside a page folder doesn't add new
content either. It isn't tied to any key, so the next sync deletes it
silently. If you need a new piece of copy, ask a developer to add the
key first; sync will then create the file for you to edit.

The files in each page folder are the complete list of what you can
change. If the text you're after isn't there, it isn't editable here
yet.
