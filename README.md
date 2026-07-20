# AEGIS

Weather on steroids — Chrome extension for real-time weather data.

## Features

- Current temperature, feels-like, humidity, pressure, wind, UV index, visibility, cloud cover, precipitation
- 30+ atmospheric metrics in real time
- 14-day forecast with hourly detail
- Severe weather alerts (thunderstorms, extreme heat/cold, dangerous wind, high UV)
- Air quality data (AQI, PM2.5, PM10, O₃, NO₂, SO₂)
- Pollen counts (birch, grass, ragweed, alder)
- Interactive Leaflet map with animated wind streams
- Moon phases, sunrise/sunset with countdown
- Clothing recommendations based on current conditions
- Three themes: dark, light, biscuit
- Chrome side panel support (Ctrl+Shift+E)
- Offline mode with data caching
- English and Russian localization

## Installation

### From Chrome Web Store

1. Go to [AEGIS on Chrome Web Store](#)
2. Click **Add to Chrome**

### Manual installation (developer mode)

1. Download or clone this repository
2. Open `chrome://extensions`
3. Enable **Developer mode**
4. Click **Load unpacked** and select the `AEGIS` folder

## Permissions

| Permission | Purpose |
|---|---|
| `storage` | Caches weather data and stores user preferences |
| `geolocation` | Auto-detects your location for weather queries |
| `notifications` | Alerts for dangerous weather conditions |
| `sidePanel` | Renders the weather panel in Chrome's side panel |
| `contextMenus` | Adds "Open AEGIS" to the right-click menu |

## Data Sources

- [Open-Meteo](https://open-meteo.com/) — weather forecast and air quality APIs
- [Nominatim](https://nominatim.openstreetmap.org/) — geocoding (city search)
- [CARTO](https://carto.com/) — map tiles

## Privacy

AEGIS does not collect, store, or transmit personal data. All weather data is fetched directly from open APIs. Location is used only for weather queries and is processed locally. No tracking, no ads, no analytics.

## License

MIT
