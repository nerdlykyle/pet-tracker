# Weekly Pet Check-In

A free, private, mobile-first quality-of-life tracker for pets, built on the HHHHHMM scale (Hurt, Hunger, Hydration, Hygiene, Happiness, Mobility, More good days than bad) developed by veterinary oncologist Dr. Alice Villalobos.

Owners score their pet once a week on seven 0–10 sliders, add notes, and watch the trend over time. Before an appointment, one tap produces a clean printable/shareable summary of recent weeks to hand to the vet — replacing the photocopied paper questionnaire.

## Why it's built this way

- **No backend, no accounts, no cost.** A single static HTML file. Host it free on GitHub Pages and it runs forever.
- **Private by design.** All data — pets, photos, scores, notes — lives in the browser's localStorage on the owner's own device. Nothing is ever uploaded or collected. See [PRIVACY.md](PRIVACY.md).
- **Mobile-first.** Big touch targets, installable via "Add to Home Screen," works offline after first load.

## Features

- Multiple pets (cat / dog / other) with photos and birthdays (age computed live)
- Weekly HHHHHMM scoring with a 0–70 total and plain-language reading (35+ is the generally accepted quality-of-life threshold)
- Per-week notes for documenting symptoms and episodes
- Saved weeks lock against accidental edits; tap "Edit this week" to change
- Trend chart with the 35-point threshold marked
- Tappable history — pull any past week back up, scores and notes intact
- "Prepare vet visit summary" — print/save PDF, copy as text, or share the last 12 weeks
- Export/import: one JSON backup covers all pets, photos, and entries (this is also how data moves to a new phone)
- Clinic branding via URL parameter (see below)

## Deploy (GitHub Pages)

1. Put `index.html` (and optionally `handout.html`) in a public repo.
2. Repo **Settings → Pages → Source: Deploy from a branch → main / (root) → Save**.
3. Your tracker is live at `https://YOUR-USERNAME.github.io/REPO-NAME/` within a minute.

## For veterinary clinics

One hosted copy can serve any number of clinics — each clinic just uses its own link:

```
https://YOUR-USERNAME.github.io/REPO-NAME/?clinic=Happy+Paws+Veterinary
```

The app displays "Provided by Happy Paws Veterinary" and remembers it on the client's device.

**Printable handout:** open `handout.html` on the hosted site, enter your tracker URL and clinic name, and print. It generates a QR-code handout with simple instructions for clients — scan, add your pet, check in weekly, bring the summary to appointments.

> Note: the `?clinic=` parameter is cosmetic and not tamper-proof — anyone can put any name in a URL. If a clinic needs a locked-down version, fork the repo and hard-code the clinic name in `index.html`.

## Data & privacy

Everything stays on-device in localStorage. The trade-off is honest: that's maximum privacy, but a lost or wiped phone without an exported backup means lost data. The app reminds users to export periodically. Full details in [PRIVACY.md](PRIVACY.md).

## Disclaimer

This tracker is an observation aid to support conversations between pet owners and their veterinarians. It is not medical advice, makes no diagnoses, and no single score should drive any decision. The HHHHHMM scale and the 35-point threshold are guidance commonly used in veterinary quality-of-life discussions; interpretation belongs to the owner and their vet.

## Tech notes

- Single-file vanilla HTML/CSS/JS — no framework, no build step
- Fonts loaded from Google Fonts; QR generation on the handout page uses qrcodejs from cdnjs (the tracker itself has no JS dependencies)
- Photos are center-cropped and resized to 220 px JPEG client-side before storage to keep localStorage small
