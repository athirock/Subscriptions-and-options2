# Proximus — Subscription configuration prototype

Interactive front-end-only prototype of the MyProximus Enterprise
subscription-configuration flow: **Step 1 (Select subscription)** and
**Step 2 (Options, optional)**, unlocked in place on the same page after
clicking "Confirm subscription". No backend — all plan data, filters and
selection state run client-side in `script.js`.

## What's in Step 2

Only the **"International and roaming (outside EU) options"** accordion is
built out in full (recurring roaming with quantity 1–20, daily roaming,
recurring international), matching the reference screenshot. The other five
accordions (Data options in Belgium and EU, Barrings, National surf limit,
Roaming surf limit, Other services) are present and expandable but show a
placeholder note — they weren't in scope for this round.

## Known assumptions / things to double-check

- Recurring roaming cards start **unchecked** (the reference screenshot showed
  a live customer's already-active options — a fresh "select options" wizard
  seemed like the more useful state to test from).
- "Belgium & EU" and "Negotiated" filter chips are real chips but will
  currently always show "no options match" — there's no EU-zone or negotiated
  roaming bundle in the sample data, which mirrors the real page's explanation
  that EU-zone usage needs no roaming option.
- All underlined destination/zone links point to the public roaming rates
  page with a `#goodtoknow` anchor guess (to land on the "Good to know"
  section) — the exact anchor id on the live page wasn't confirmed, so it may
  not scroll to the right spot.
- Selecting a daily roaming option clears any recurring roaming selections
  and vice versa, per the real page's "activating this deactivates all other
  roaming options" behavior.

## Files
- `index.html` — markup
- `styles.css` — all styling (Lavender design tokens, Proximus colors)
- `script.js` — plan data, filter logic, and rendering

## Run locally
Just open `index.html` in a browser — no build step, no dependencies.

## Publish with GitHub Pages
1. Create a new repo (or use an existing one) and push these three files to it.
2. In the repo: **Settings → Pages**.
3. Under **Build and deployment → Source**, choose **Deploy from a branch**.
4. Pick the branch (e.g. `main`) and folder `/ (root)`, then **Save**.
5. GitHub will publish at `https://<your-username>.github.io/<repo-name>/`
   within a minute or two — that link is shareable for public testing.

## Notes
- The Proximus logo SVG is inlined directly in `index.html`.
- Everything (fonts fall back to system sans-serif, icons are inline SVG) is
  self-contained — nothing external is fetched, so it works on GitHub Pages
  with no extra config.
