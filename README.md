# Imagination Infrastructure — M26 Studio · CEPT · 2026

A living point-cloud of the studio's semester: each thread is a student, each point a piece of
work, coloured by student and arranged in time. Scroll to travel from the isometric overview down
into the cloud and through everyone's work.

**Live site:** once GitHub Pages is turned on for this repo (see below), it's published at
`https://<your-username>.github.io/<repo-name>/`.

## Putting this on GitHub Pages

1. Create a new repository on GitHub (public, unless you're on a paid plan that supports private
   Pages) and upload the contents of this folder to it (drag-and-drop the files on github.com, or
   `git init` + `git add .` + `git commit` + `git push` if you're comfortable with git).
2. In the repo, go to **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Under **Branch**, choose `main` (or whichever branch you pushed to) and folder `/ (root)**, then
   **Save**.
5. GitHub takes a minute or two to publish. The URL appears at the top of that same Pages settings
   page once it's live — `https://<your-username>.github.io/<repo-name>/`.

That's it — no build step, no server. `index.html` at the root is the whole site; GitHub Pages
serves it directly.

## Updating the content

You don't need to touch any code to add students or submissions. See **`data/README.md`** for the
full guide — in short:

- **`data/students.csv`** — the roster. One name per row.
- **`data/submissions.csv`** — the real submitted work. One row per piece: student, date, a short
  caption, and optionally an image.
- **`uploads/`** — where submission images live.

Edit either CSV directly on github.com (GitHub shows a spreadsheet-style editor for `.csv` files),
or edit it locally in Excel/Numbers/Sheets and push the change. Either way, GitHub Pages rebuilds
automatically within about a minute of a commit, and the site re-reads the CSVs on its own — no
conversion step, nothing to send anyone.

## Before you make the repo public

Everything in this folder becomes publicly downloadable once Pages is on (that's how static
hosting works). `uploads/` currently has a few files from early project work
(`Assignment Handout Example.pdf`, `M26_Semester Plan.xlsx`, `Studio Pitch.pdf`) alongside the
submission image — worth a quick look to make sure nothing in there is meant to stay private
before you push.

## File structure

```
index.html                    the site (this is what GitHub Pages serves)
support.js                    runtime the site depends on — keep alongside index.html
data/
  students.csv                 roster — edit to add/remove/rename students
  submissions.csv               real submitted work — edit to publish new work
  README.md                     full field-by-field guide for both CSVs
uploads/                        images referenced from submissions.csv (+ misc project files)
Living Canvas 3D.dc.html        source copy used for future edits — not needed for hosting
```

## Limits worth knowing

- Only `Type: image` submissions render an actual picture today; `video`/`audio` show as a plain
  caption box.
- Everything here is client-side and static — there's no login, no moderation queue, and no
  backend. Anyone with push access to the repo can edit the CSVs.
