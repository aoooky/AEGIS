# AEGIS — Chrome Web Store Permission Justifications
# Each field: max 1000 characters

---

## storage
Used to store user preferences locally within the browser: language (EN/RU), temperature unit (C/F), wind unit (km/h, m/s, mph), theme (dark/light/biscuit), compact mode toggle, liquid cursor toggle, map size, saved locations, and recent searches. Also caches weather data (current conditions, forecast, AQI, pollen) with TTL-based expiration (1-24 hours) to enable offline access and reduce redundant API calls. All data remains in chrome.local.storage and never leaves the browser. No personal data is collected or transmitted.

---

## geolocation
Used to automatically detect the user's current geographic coordinates via the browser's Geolocation API when the extension first loads or when the user requests location refresh. The obtained latitude and longitude are used exclusively to construct API requests to Open-Meteo for fetching weather data relevant to the user's area. Coordinates are stored temporarily in chrome.local.storage for the current session only and are not transmitted to any third party. The user can deny geolocation and manually search for any city instead.

---

## notifications
Used to send Chrome native system notifications alerting the user to dangerous or severe weather conditions. The extension's service worker checks weather thresholds every 10 minutes in the background and triggers notifications for: extreme heat (above 38C), extreme cold (below -30C), dangerous wind gusts (above 90 km/h), high UV index (above 9), thunderstorms, unhealthy air quality (AQI above 150), elevated PM2.5/PM10 levels, and high pollen counts. Maximum 3 notifications are sent per day to avoid spam. All logic runs locally — no data is sent externally for notification purposes.

---

## sidePanel
Used to render the AEGIS weather panel inside Chrome's built-in side panel UI, accessible via the keyboard shortcut Ctrl+Shift+E or through the extension's right-click context menu. This allows users to view weather data in a persistent sidebar without opening a popup or leaving their current tab. The side panel loads the same panel.html file used by the popup, with a compact layout automatically applied. No data is transmitted as a result of using this permission — it is purely a Chrome UI presentation feature.

---

## contextMenus
Used to add a single "Open AEGIS" menu item to Chrome's context menu (right-click menu) on the extension icon. This provides users with quick access to open the weather panel without needing to remember keyboard shortcuts. When clicked, it opens the side panel. No data is collected, stored, or transmitted through this feature. It is purely a UI convenience feature with no network or data implications.

---

## host_permissions (Разрешение на доступ к хостам)

The extension accesses exactly 4 public open-data APIs for its single purpose — displaying weather: 1) api.open-meteo.com — weather forecast (temperature, wind, precipitation, UV, pressure, etc.). 2) air-quality-api.open-meteo.com — air quality (AQI, PM2.5, PM10, O3, NO2, SO2) and pollen data. 3) nominatim.openstreetmap.org — geocoding (city search and reverse lookup). 4) basemaps.cartocdn.com — map tiles for the interactive Leaflet map. All are free, open-source services. Only GET requests are made. No authentication, cookies, or user credentials are involved. No data is sent to any other hosts.
