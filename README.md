# Rough River Retreat — Site Update Guide

## How it all works now
- **Source files:** GitHub repo `VHAM-YOLO/RoughRiver`
- **Hosting:** Cloudflare Pages (free) — auto-deploys every time you push to the `main` branch (~1 minute)
- **Domain:** roughriverretreat.com (+ www) — DNS managed in Cloudflare, registered/renewed at GoDaddy
- **Booking availability:** public Google Calendar ("Rough River House")

The whole idea: you edit files in the GitHub repo and commit. Cloudflare publishes the change automatically. You never touch the hosting directly.

## To edit text or a page
1. Open the file in the repo — `index.html` (home page), `photos.html` (gallery), or `styles.css` (styling).
2. Make your edit (the pencil icon on GitHub, or edit locally on your Mac).
3. Commit to `main`. Cloudflare redeploys in about a minute.

## To add gallery photos
1. Use photos you own — your own phone shots. Never reuse real-estate/MLS listing photos.
2. Convert to `.webp` and resize to ~2048px on the long edge (or just send them to me and I'll do it).
3. Name them continuing the sequence. The highest right now is `photo50`, so start new ones at `photo51`.
4. Put the files in the `images/` folder.
5. For each new photo, add one line inside the photo grid in `photos.html`, e.g.:
   `<a href="images/photo51.webp" target="_blank" rel="noopener"><img loading="lazy" src="images/photo51.webp" alt="Rough River Retreat photo 48"></a>`
6. Commit to `main`.

## To remove a photo
- Delete that photo's line in `photos.html` (and optionally delete the file from `images/` to tidy up).
- **Important:** the filenames don't match the order photos appear in the grid, so go by the **filename in the code**, not by where the photo shows up on the page. (That's the mix-up we ran into before.)

## Handy reminders
- **Batch edits into one commit** when you can — fewer deploys, cleaner history.
- See an old version after updating? **Hard refresh** (Cmd+Shift+R) or open in a private window. It's almost always browser cache, not a real problem.
- **DNS now lives in Cloudflare**, not GoDaddy — but your domain is still *registered* at GoDaddy, so keep that yearly renewal paid.
- Hosting is back to **$0/month** (just confirm the Netlify billing is switched off).

## Where everything lives
| Service | What it does |
|---|---|
| GitHub (`VHAM-YOLO/RoughRiver`) | Your site's files |
| Cloudflare Pages | Hosting + automatic deploys |
| Cloudflare DNS | Domain routing |
| GoDaddy | Domain registration only |
| Google Calendar | Booking availability |
