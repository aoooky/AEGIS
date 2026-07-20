# AEGIS — Privacy Policy & Permission Justifications

## Privacy Policy

AEGIS is a weather extension that fetches real-time weather data from open APIs. **No personal data is collected, stored, transmitted, or shared with third parties.** All data processing happens locally within the browser. The extension does not use analytics, advertising, or tracking of any kind.

---

## Permission Justifications

### `storage`
Used to store user preferences (language, temperature unit, wind unit, theme, compact mode, liquid cursor toggle, map size) and to cache weather data for offline access. All data remains within the browser's local storage and is never transmitted externally.

### `geolocation`
Used solely to automatically detect the user's current location for weather queries. Coordinates are sent only to the Open-Meteo API to fetch weather data for the user's area. Location data is not stored persistently or shared with any third party.

### `notifications`
Used to send Chrome system notifications about dangerous weather conditions (thunderstorms, extreme heat/cold, dangerous wind gusts, high UV index, unhealthy air quality, elevated pollen levels). Notifications are triggered locally by the service worker based on weather data thresholds. Maximum 3 notifications per day.

### `sidePanel`
Used to provide the AEGIS weather panel in Chrome's side panel, allowing users to view weather data without leaving their current tab. This is a Chrome UI feature and does not involve any data transmission.

### `contextMenus`
Used to add a single "Open AEGIS" entry to the extension's right-click context menu, providing quick access to the weather panel. No data is collected or transmitted through this feature.

---

## Host Permission Justifications

### `https://api.open-meteo.com/*`
Fetches weather forecast data including temperature, humidity, wind, precipitation, UV index, visibility, dew point, cloud cover, pressure, soil temperature, solar radiation, CAPE, sunshine duration, and daily/hourly forecasts.

### `https://air-quality-api.open-meteo.com/*`
Fetches air quality data (European AQI, PM2.5, PM10, O3, NO2, SO2) and pollen data (alder, birch, grass, ragweed) from the Open-Meteo Air Quality API.

### `https://nominatim.openstreetmap.org/*`
Used for geocoding — converting city names to coordinates (forward geocoding) and coordinates to city/region names (reverse geocoding) via the OpenStreetMap Nominatim service.

### `https://basemaps.cartocdn.com/*`
Loads map tile images for the interactive Leaflet map component. No user data is sent to this server.

---

## Remote Code

AEGIS **does not use remote code**. All JavaScript files (`panel.js`, `background.js`, `liquid-cursor.js`, `leaflet.js`) are bundled within the extension package. No code is loaded from external sources at runtime. The extension's Content Security Policy (`script-src 'self'`) enforces this restriction.

---

## Purpose

AEGIS is a weather extension that provides real-time weather information for any location. It automatically detects the user's location or allows manual city search to display current temperature, wind, humidity, UV index, air quality, precipitation, and 30+ atmospheric metrics. The extension fetches data exclusively from Open-Meteo open APIs and stores preferences locally. It sends browser notifications for severe weather conditions such as thunderstorms, extreme temperatures, dangerous wind, and high pollen levels. The interactive map displays weather data with animated wind particles. All data processing occurs locally — no personal information is collected, stored, or transmitted to third parties. The extension operates as a popup panel or Chrome side panel for convenient access.

---

## Contact

For questions about this privacy policy, contact: [your-email@example.com]
