# Jetebble public settings host

This repository contains only Jetebble’s public companion settings page and its artwork. It keeps the settings address used by already-installed apps working while the watch app’s source repository stays private.

Settings: https://kvnsr1.github.io/pebble-flight/config/

GitHub Pages publishes `main` from `/`. The user-site repository name and `pebble-flight/config/` path preserve the exact address embedded in published Jetebble versions, including the `?v=0.7.8` query string. Do not move this directory or rename this repository without planning support for installed apps.

## Updating settings

The maintained source is `config/` in the Pebble Flight app checkout. Copy only these four files into `pebble-flight/config/` here, preserving their relative paths:

- `index.html`
- `assets/plane.svg`
- `assets/wordmark.svg`
- `assets/tagline.svg`

Run the app repository’s `test/settings-page.test.js` before copying. Review the diff, commit only the four listed files, and push this repository’s `main`. GitHub Pages deploys the update. Verify the live page and all three SVGs; do not assume a successful Git push means deployment succeeded.

This is a static page: it has no server, analytics or third-party scripts. The key entered by a user is returned directly to the Pebble companion app through `pebblejs://close`; the page does not save it to web storage. The Show/Minimize guide preference is the only localStorage setting.

Do not copy native source, watch builds, user settings, API keys, environment files or the full app repository into this public host. No watch app rebuild or Store release is needed for a settings-page-only change at the same URL.
