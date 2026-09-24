# CLAUDE.md — rules for Claude Code in this repository

This is the SOAR Lab website (Department of Physiology, Faculty of Medicine,
Khon Kaen University). The owner, Dr Panus Choocheepwattana, is a
physician-physiologist, not a web developer, and is the only editor. He
maintains the site by editing text in marked places or by asking for small,
specific changes. Optimise every decision for that.

## Working rules

- Make the smallest change that satisfies the request; do not restyle or reword unrelated sections.
- Before committing, summarise the diff in plain language and wait for my OK.
- Never push without my explicit instruction.

## Hard constraints — do not break these

1. Plain HTML + CSS. Vanilla JS only where unavoidable (e.g. mobile menu). No framework, no build step, no package.json, no Jekyll.
2. Must deploy as-is to GitHub Pages from `main` / root.
3. **Use relative paths only** (`style.css`, `assets/img/x.jpg`, never `/style.css`), so the site works both at `https://drmattchoo.github.io/soar/` and at the custom domain root.
4. Content: use ONLY what is in the **Content** section below. Never invent people, publications, grants, awards, affiliations, dates, numbers, quotes or testimonials, and never complete or "correct" a reference. Missing content → a visible `[TODO: …]` placeholder; list every TODO in your final summary.
5. No analytics, trackers, cookies, embeds or third-party scripts. Fonts: IBM Plex Sans + IBM Plex Sans Thai (SIL OFL), self-hosted as woff2 in `assets/fonts/` with `font-display: swap`. If you cannot download them, fall back to Google Fonts and tell me.
6. Do not use the KKU or Faculty of Medicine logo or any university branding unless I place the file in `assets/img/` myself.
7. Accessibility: semantic landmarks, exactly one `h1` per page, alt text, WCAG AA contrast, visible focus states, fully keyboard-navigable, honour `prefers-reduced-motion`.
8. Mobile-first and responsive; no horizontal scroll at 360 px wide.
9. Clinical content is informational only; nothing may read as individual medical advice.

Note for constraint 4: the "Content section" was in the original site brief.
The content now on the site, plus anything the owner provides in a request,
is the only allowed content.

Known exception to constraint 3 (approved by the owner): `404.html` uses
inline styles and full `https://drmattchoo.github.io/soar/` links, because
GitHub Pages serves it at arbitrary broken URLs where relative paths fail.
Update those links if a custom domain is added.

## Editability rules

- Wrap every block of text or link I am likely to change in `<!-- EDIT HERE: <what this is> -->` … `<!-- END EDIT -->`.
- Each person and each publication is one self-contained, copy-pasteable block, preceded by a comment showing how to add another.
- Flat, obvious file layout (see Files). No generated or minified code.
- All design tokens (colours, fonts, spacing, max width) as CSS custom properties at the top of `style.css`, each with a one-line comment.
- CSS commented by section, using the same section names as the HTML.

## Files

`index.html`, `style.css`, `script.js` (mobile menu only), `404.html`,
`favicon.svg`, `.nojekyll`, `assets/img/`, `assets/fonts/`, `README.md`,
`CLAUDE.md`.
