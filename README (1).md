# Sunda Shelf Field Key

A single-page ID game that pulls a fresh, random, research-grade plant
observation from the [iNaturalist API](https://api.inaturalist.org) on
every round — no build step, no server, no API key. Guess family,
genus, and (for a bonus) species; use the order/locality/family clue
chips if you're stuck.

Region covered: a bounding box over the Sunda Shelf (Malay Peninsula,
Sumatra, Java, Borneo, Bangka–Belitung).

## Run it locally
Just open `index.html` in a browser. That's it.

## Put it on GitHub Pages (free, permanent link)
1. Create a new repo on GitHub, e.g. `sunda-field-key`.
2. Add `index.html` to the repo root (drag-and-drop on github.com works,
   or:
   ```
   git init
   git add index.html README.md
   git commit -m "Sunda Shelf field ID game"
   git branch -M main
   git remote add origin https://github.com/<you>/sunda-field-key.git
   git push -u origin main
   ```
3. On GitHub: repo → **Settings → Pages** → under "Build and
   deployment", set **Source: Deploy from a branch**, branch
   **main**, folder **/ (root)** → Save.
4. Wait ~1 minute, then your game is live at
   `https://<you>.github.io/sunda-field-key/`.

Every visit re-queries iNaturalist, so it never runs out of content
and stays current as new research-grade records get added.

## Tuning it further
- `BOUNDS` at the top of the `<script>` in `index.html` is the lat/lng
  box being queried — tighten it to just Borneo, or widen it to all of
  Malesia, by editing those four numbers.
- Add `&taxon_id=<id>` to the fetch URL in `fetchCandidate()` to
  restrict the game to one family or order (e.g. Orchidaceae,
  Dipterocarpaceae) for focused practice.
- Scoring weights (10/15/20/5 points) are in the `submit` handler —
  change them freely.
