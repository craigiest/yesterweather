# Yesterweather

A mobile web app in the style of the iOS Weather app that shows **yesterday's** weather: high/low, precipitation and cloud cover, an hour-by-hour record, a 10-day history (starting with today so far) with expandable hourly detail, and a day-details section that can step through or jump to any date: normals and records, all-time monthly records, sunrise/sunset, UV index, visibility, wind, humidity and air quality.

Everything is in `index.html`. No build step and no API keys.

## Data sources

| Data | Primary (US) | Fallback |
| --- | --- | --- |
| Daily high, low, precipitation, snow | NOAA ACIS, nearest first-order/ASOS station | Open-Meteo |
| Hourly temperature, wind, humidity, visibility, clouds | NWS `api.weather.gov` station observations | Open-Meteo |
| Normals (1991–2020), daily records and all-time monthly records | NOAA ACIS | none (US only) |
| Any past date (calendar), back to 1940 | NOAA ACIS for daily values | Open-Meteo forecast API (last ~3 months) or ERA5 archive |
| US AQI, UV index, sunrise/sunset, condition codes | Open-Meteo | none |
| Place search | Open-Meteo geocoding | none |

Saved locations and unit choices (US or Metric presets, or per-measure units) are stored in the browser's `localStorage`.

## Hosting

Geolocation requires HTTPS. To host on GitHub Pages, enable Pages for this repository (Settings → Pages → deploy from branch, root folder).
