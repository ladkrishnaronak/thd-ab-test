# The Divines Health — Wellness Program Landing Page

Static site, no build step. Plain HTML + Tailwind CDN.

## Routes

| Route | What it is |
|---|---|
| `/` | **Live page — Version B (research winner), extended.** The core Explore screen. |
| `/enroll/` | Enrollment form + confirmation state |
| `/call/` | Free 1:1 call booking + confirmation state |
| `/a/` | Research variant A — *Inspiring Journey* (kept as evidence, do not edit) |
| `/b/` | Research variant B — *Video-Led, Clear Path* as tested (kept as evidence, do not edit) |

`/a` and `/b` are frozen snapshots of what the 3 usability participants actually clicked on Aug 13, 2026. They are linked from a small footer note on `/`. Do not modify them — they are the research record.

## Which version won

**Version B — "Video-Led, Clear Path"** won and is now promoted to `/`.

| | Satisfaction | Ease of use |
|---|---|---|
| Version A — Inspiring Journey | 36.5% (Red) | 46.5% (Red) |
| **Version B — Video-Led, Clear Path** | **83% (Green)** | **80% (Green)** |

Source: `TDH_findings_report.docx`, n=3, mobile, Aug 13 2026.

> **Note:** earlier versions of this README had A and B swapped. The mapping above is correct and matches the findings report — `/a` is Inspiring Journey, `/b` is Video-Led.

## Design tokens

Palette is taken from the tested Version B prototype (derived from `ColorScheme_1.jpg`):

```
#8d6f4c  Deep Bronze     — primary buttons, links
#c99f6c  Honeyed Amber   — accents, highlights, active states
#a9a190  Mossed Bronze   — secondary text
#ede0bd  Ivory Glow      — borders, video block, cards
#cdc5af  Golden Sands    — dividers
#e5dcc9  Sand            — image placeholder blocks
#f7f4ee  Ivory           — section backgrounds
#4a3f35  Dark            — body text
```

Type: **Cormorant Garamond** (headings, quotes) + **Manrope** (body/UI).
Frame: `max-width: 420px` — mobile-first, as all social traffic is mobile.

## What's built vs. what's Phase 2

**Built (clickable end-to-end):**
- Explore hub — video, symptom recognition grid, 4-phase program journey, what-you-gain, founders, testimonials, FAQ
- 1:1 Call booking with slot picker + confirmation state
- Enrollment form with validation + confirmation state
- Symptom selections carry from `/` into `/enroll/` via `sessionStorage`

**Phase 2 (per findings report §4.3 — deliberately out of scope):**
- Payment processing
- Real form backend (currently `console.log` only — no data is stored or sent)
- Calendly embed (slot picker in `/call/` is a placeholder for it)
- Redirect to the existing thedivineshealth.com homepage after enrollment

## Two designed peak moments (Peak-End Rule)

1. **Peak — symptom recognition** on `/`. Tapping symptoms is the emotional "that's me" moment; the count feeds back a message tying the symptoms together.
2. **End — enrollment confirmation** on `/enroll/`. Animated, names the user, lays out exactly what happens next, and directly answers the trust hesitation a participant raised ("It can be fake") with a WhatsApp verification path and the physical clinic address.

## Run locally

```
python3 -m http.server 8080
# open http://localhost:8080
```

## Deploy

Vercel auto-deploys on push to `main`. No build command, no output directory — static files served as-is (`vercel.json` sets `cleanUrls` + `trailingSlash`).

## Note on images

Photography and icons are not embedded yet — solid color blocks and emoji stand in. Real founder photos and program imagery exist in the project files (`IMG_9090`–`IMG_9095`) and should be swapped in during the fidelity pass.
