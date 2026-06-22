# Eagle Catering — Drinks Quantity Calculator

A single-file web app that calculates how much of each drink to buy for an event, based on guest count and event type.

## What it is

`eagle-catering-drinks-calculator.html` is a self-contained file — no build step, no server, no install. It loads React, Tailwind, and Google Fonts from CDNs at runtime, so it needs an internet connection to work, but otherwise runs entirely in the browser.

## How to deploy it

Pick one:

**Netlify Drop (fastest, free, no account)**
1. Go to app.netlify.com/drop
2. Drag `eagle-catering-drinks-calculator.html` onto the page
3. You get a live URL immediately. Share that with staff.
4. Note: Drop sites are temporary/random-named unless you create a free account to claim them permanently.

**GitHub Pages (free, permanent, can use a custom domain later)**
1. Create a GitHub repo
2. Upload the file, renamed to `index.html`
3. Repo Settings → Pages → enable, point it at the main branch
4. You get a stable `username.github.io/repo-name` URL

**Netlify with an account / your existing site host**
Same drag-and-drop as above, but persists permanently and supports attaching a custom subdomain (e.g. `tools.eaglecatering.co.uk`).

## What's calculated

For each selected drink: `units needed = ceil(guests × per-guest rate for the chosen event type)`, then rounded up to the nearest full pack/case.

Drinks covered: soft drink cans, 1L glass water bottles, 330ml plastic water bottles, wine (75cl bottles), juice cartons.

Event types: Wedding, Corporate, Private Party, Funeral.

## What's editable in the app itself

Click "Show consumption rates & pack sizes" to edit:
- Per-guest consumption rate, per drink, per event type
- Pack/case size per drink

Changes apply immediately but **only last for that browser session** — refreshing the page resets everything to the defaults below. There's no database or persistence; this is a calculator, not a saved-order system.

## Important caveat: Funeral rates are not sourced

The Wedding, Corporate, and Private Party default rates are based on published catering-industry per-guest-per-hour consumption guidance for a roughly 4-hour event.

**The Funeral column has no such source.** No industry data on funeral catering drink consumption was found. Those numbers are placeholder estimates only. The app flags this visually (amber highlighting, asterisk) in the rate editor — don't remove that flag if you ever edit the code, and don't treat those numbers as reliable until you've checked them against your own event experience.

## Known limitations

- Requires internet access (CDN-loaded dependencies) — won't run fully offline.
- No auto-adjustment for event duration. Rates assume ~4 hours; for longer events, industry guidance suggests adding roughly 0.75 drinks/guest per additional hour — adjust the rate table manually.
- Pack/case sizes are reasonable UK retail defaults, not verified against any specific supplier. Check against what you actually buy in before relying on the pack counts.
