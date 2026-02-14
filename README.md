# Field Recording Log

A lightweight, mobile-first PWA for logging field recordings in the wild. Designed for sound recordists who want a quick way to document each recording session with location, weather, and visual context — without fiddling with spreadsheets in the field.

## Features

- **Photo capture** — snap a photo of the recording location directly from your phone's camera
- **Automatic GPS** — coordinates and accuracy logged via browser geolocation
- **Reverse geocoding** — resolves coordinates to a human-readable place name (e.g. "Leuven, Vlaams-Brabant")
- **Weather conditions** — temperature, wind direction, Beaufort scale, and relative humidity fetched automatically via [Open-Meteo](https://open-meteo.com/)
- **Title + description** — give each recording a quick title and optional detailed notes about environment, sound sources, and equipment
- **Map view** — all recordings plotted on a dark basemap (Leaflet + CARTO tiles)
- **Detail view** — full metadata with a mini-map for each recording
- **Stats dashboard** — total recordings, this month's count, and recordings with location data
- **Export** — download your log as CSV or GeoJSON, ready for QGIS, ArcGIS, or any spreadsheet
- **Offline-capable** — service worker caches the app shell; recording, photo, and GPS work without internet (weather and map tiles require connectivity)
- **Installable** — add to your home screen on iOS or Android for a fullscreen app experience

## Getting started

This is a single HTML file — no build tools, no dependencies to install.

### Option 1: GitHub Pages (recommended)

1. Fork or clone this repository
2. Go to **Settings → Pages**
3. Set source to **Branch: main**, folder **/ (root)**
4. Your app is live at `https://your-username.github.io/Fieldrecording_registry/`
5. Open on your phone and add to home screen

### Option 2: Local

Open `index.html` directly in your mobile browser. Note that some browsers restrict camera and geolocation access for local files — hosting (even locally) is recommended.

## Data storage

All recordings are stored in your browser's `localStorage`. Data stays on your device and is never sent to any server. Clear your browser data = lose your recordings, so export regularly.

## Export formats

| Format | Contents |
|--------|----------|
| **CSV** | id, date, time, title, description, location name, coordinates, accuracy, temperature, wind, Beaufort, humidity |
| **GeoJSON** | Same fields as properties on Point features — drop directly into GIS software |

## APIs used

- [Open-Meteo](https://open-meteo.com/) — weather data (free, no API key)
- [Nominatim / OpenStreetMap](https://nominatim.openstreetmap.org/) — reverse geocoding (free, no API key)
- [CARTO](https://carto.com/basemaps/) — dark map tiles
- [Leaflet](https://leafletjs.com/) — map rendering

## License

MIT
