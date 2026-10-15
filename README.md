# Yesterweather

A mobile web app in the style of the iOS Weather app that shows **yesterday's** weather: high/low, precipitation and cloud cover, an hour-by-hour record, a 10-day history with expandable hourly detail, and air quality, normals, records, sunrise/sunset, UV index and visibility.

Everything is in `index.html`. No build step and no API keys.

## Data sources

| Data | Primary (US) | Fallback |
| --- | --- | --- |
| Daily high, low, precipitation, snow | NOAA ACIS, nearest first-order/ASOS station | Open-Meteo |
| Hourly temperature, wind, humidity, visibility, clouds | NWS `api.weather.gov` station observations | Open-Meteo |
| Normals (1991–2020) and daily records | NOAA ACIS | none (US only) |
| US AQI, UV index, sunrise/sunset, condition codes | Open-Meteo | none |
| Place search | Open-Meteo geocoding | none |

Saved locations and the US/SI unit choice are stored in the browser's `localStorage`.

## Hosting

Geolocation requires HTTPS. To host on GitHub Pages, enable Pages for this repository (Settings → Pages → deploy from branch, root folder).
