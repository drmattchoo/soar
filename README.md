# SOAR Lab website

The website of SOAR Lab (Space, Operational & Aviation Research Laboratory),
Department of Physiology, Faculty of Medicine, Khon Kaen University.

- Live address: https://drmattchoo.github.io/soar/
- It is plain HTML and CSS. There is nothing to install or build.

## What each file is

| File | What it is |
|---|---|
| `index.html` | The whole website: every section's text is here |
| `style.css` | Colours, fonts and layout. Colours are at the top |
| `script.js` | Opens and closes the menu on phones. Nothing else |
| `404.html` | The "page not found" page |
| `favicon.svg` | The small "SL" icon in the browser tab |
| `assets/img/` | Photos. Put `pi.jpg` here |
| `assets/fonts/` | The IBM Plex fonts (free licence in `OFL.txt`) |
| `.nojekyll` | An empty file that tells GitHub to publish the files as they are. Leave it |
| `CLAUDE.md` | Rules for Claude Code when it edits this site |

## Edit a sentence

1. Open `index.html` in a text editor (TextEdit in plain-text mode, or VS Code).
2. Search for the words you want to change. Every editable block sits between
   `<!-- EDIT HERE: … -->` and `<!-- END EDIT -->`.
3. Change only the words between the `>` and `<` marks. Leave the tags alone.
4. Save, then preview (below).

Special characters: write `&` as `&amp;` in the HTML.

## Add a person

1. In `index.html`, find `HOW TO ADD A PERSON`.
2. Copy the example block below it (from `<li class="person">` to `</li>`).
3. Paste it after the last person's `<!-- END EDIT -->` line.
4. Change the name, the role and the affiliation.

## Add a publication or presentation

1. In `index.html`, find `HOW TO ADD A PUBLICATION`.
2. Copy the example block below it (from `<li class="pub">` to `</li>`).
3. Paste it just below that comment, so the newest item is first.
4. Replace the text with the reference. If it has a DOI, put the DOI in both
   places on the link line. If it has no DOI, delete the link line.

## Replace a photo

1. Save the photo as a JPEG named `pi.jpg`. A portrait shape (4:5) about
   640 × 800 pixels works well. Keep it under about 300 KB.
2. Put it in `assets/img/`, replacing the old file.
3. If the person in the photo changes, update the `alt="…"` text next to
   `pi.jpg` in `index.html`.

## Preview on your Mac

Quick look: double-click `index.html`, or in Terminal:

```bash
open index.html
```

## Publish a change

Run these in Terminal from the `soar` folder
(`cd ~/Desktop/soar`). Replace the message in quotes with what you changed.

```bash
git add -A
git commit -m "Update People section"
git push
```

GitHub updates the live site one or two minutes later.

## Undo a bad change

See the list of recent changes:

```bash
git log --oneline -10
```

Each line starts with a short code, e.g. `3f2a1bc`. To undo that change
(this adds a new change that reverses it; nothing is lost):

```bash
git revert 3f2a1bc
git push
```

If you have edited files but not committed yet and want to throw those edits away:

```bash
git restore .
```

## Ownership & exit plan

- The site's code lives in the GitHub account **drmattchoo**, repository **soar**
  (https://github.com/drmattchoo/soar). It is hosted free by GitHub Pages.
- It is a personal account, not a university account, so the site does not
  depend on KKU systems and keeps working if you leave KKU.
- If you leave KKU:
  1. Update the affiliation, address and email in `index.html`. The
     `panuch@kku.ac.th` address will probably stop working, so change it in
     both places (Join us and Contact).
  2. Decide the lab site's future: keep it as your own, hand it to a
     successor, or archive it.
  3. To hand it over: on GitHub, open the repository → **Settings** →
     **General** → **Transfer ownership**, and enter the new owner's
     GitHub username. The site address will change to theirs.
  4. To close it: **Settings** → **Pages** → unpublish, then
     **Settings** → **General** → **Archive this repository**. The code
     stays readable as a record.
- Keep access to the drmattchoo account: turn on two-factor authentication
  and store the recovery codes somewhere safe.
