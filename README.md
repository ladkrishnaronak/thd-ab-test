# The Divines Health — A/B Prototype

Static site, no build step. Pulled directly from the two Figma prototypes:

- **Version A** — `/a` — "Video-Led, Clear Path": full program detail leads, structured linear walkthrough (hero → metadata → symptoms → video → program phases → founders → testimonials → enroll → contact).
- **Version B** — `/b` — "Inspiring Journey": video hero + tap-to-recognize symptom grid, shorter and more interactive, program phases shown as a 4-card journey.
- **Home** — `/` — links to both versions.

## Run locally

No install needed — it's plain HTML + Tailwind CDN.

```
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy to Vercel

1. Push this folder to a new GitHub repo.
2. In Vercel: New Project → Import the repo.
3. Framework preset: **Other** (no build command, no output directory needed — Vercel serves the static files as-is).
4. Deploy. Routes `/`, `/a`, `/b` work automatically because each is a folder with its own `index.html`.

## Note on images

The original Figma image/icon assets weren't embedded in this pass (icons here are simplified to keep the handoff fast) — the design uses solid color blocks in place of imagery. If you want the real photos/icons pulled in, ask Claude Code to re-run `get_design_context` on the two Figma files and swap the placeholder blocks for the real asset URLs before they expire (Figma asset links are only valid ~7 days).
