# MOLI site — map & sighting tracker

## Files
- `index.html` — full site + Leaflet map + report form
- `sightings.json` — **public moderated pins only** (you edit this)

## How reports work (static hosting)

1. Visitor submits the form.
2. Until you set `CONFIG.formEndpoint` or `CONFIG.reportEmail` in `index.html`:
   - browser **downloads a JSON** of the report (so nothing is lost).
3. You review, then add an approved pin to `sightings.json`:

```json
{
  "id": "2026-001",
  "lat": 56.12,
  "lng": -3.94,
  "species": "Hedgehog",
  "date": "2026-10-03",
  "area": "A92 near Freuchie",
  "status": "approved",
  "notes": ""
}
```

4. Commit/upload `sightings.json` — the map reloads it.

## Optional: auto-inbox

In `index.html` script `CONFIG`:

```js
formEndpoint: 'https://formspree.io/f/YOUR_ID',  // or own API
reportEmail: 'you@domain.com',                 // mailto fallback
```

Remove the example pin from `sightings.json` before treating the map as live data.

## Safety / privacy
- Form stresses safe reporting; no requirement for photos.
- Optional email never shown on map.
- Round or offset lat/lng before publishing if needed.
