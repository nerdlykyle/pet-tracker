# Privacy

This project is designed so that there is, as nearly as possible, nothing to have a privacy policy *about*. Here is the complete picture, stated plainly.

## What we collect

Nothing. There is no server, no database, no account system, no analytics, no cookies set by the app, and no tracking of any kind. The maintainers of this project have no way to see your data, and neither does anyone else over the network.

## Where your data lives

Everything you enter — pet names, species, birthdays, photos, weekly scores, and notes — is stored in your browser's **localStorage** on your own device. It never leaves your phone or computer. The app works offline after the first load for exactly this reason: there is nothing to send anywhere.

## What this means in practice

- **No one can read your entries** — not the site owner, not a clinic that shared the link with you, not GitHub.
- **Your data is tied to one browser on one device.** If you open the tracker in a different browser or on a different device, it starts empty.
- **Clearing browser data deletes your entries.** If you clear your browser's site data/storage for this site, your entries are gone. There is no cloud copy to restore from.
- **Backups are in your hands.** The **Export** button saves all of your data (all pets, photos, notes, and entries) as a single JSON file that you control. **Import** restores it — this is also how you move your data to a new phone. We recommend exporting periodically.

## Photos

Pet photos are resized to a small thumbnail in your browser before being stored, and like everything else they are saved only in localStorage on your device. They are never uploaded.

## The clinic name in the link

If a veterinary clinic shares a link like `...?clinic=Happy+Paws+Veterinary`, the clinic name in that link is displayed inside the app and remembered on your device. This is cosmetic text only — it does not connect the app to the clinic, send the clinic anything, or identify you to anyone.

## Third-party requests

For full transparency, the page does make two kinds of network requests, neither of which includes any of your data:

- **Google Fonts** — the app loads its typefaces from `fonts.googleapis.com` / `fonts.gstatic.com`. Like any web request, Google's servers see your IP address when the fonts load. No app data is included. (Google's privacy policy applies to that request.)
- **cdnjs (handout page only)** — `handout.html`, the clinic handout generator, loads a QR-code library from `cdnjs.cloudflare.com`. The tracker itself (`index.html`) loads no JavaScript libraries.

If even font requests are a concern, the fonts can be self-hosted by editing the CSS; the app degrades gracefully to system fonts if they fail to load.

## Hosting

The static files are typically served by GitHub Pages. GitHub may keep standard web server logs (such as IP addresses) for the pages it serves, as described in [GitHub's privacy statement](https://docs.github.com/en/site-policy/privacy-policies/github-privacy-statement). The app itself adds nothing to this.

## Changes

If the app's data practices ever change (for example, if an optional cloud-sync feature were added), this document will be updated first, and any such feature would be opt-in.

## Questions

Open an issue on the repository.
