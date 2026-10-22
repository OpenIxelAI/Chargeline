# ChargeLine

Trip planner for a Tesla that carries adapters. It plans charging stops with Tesla Superchargers plus the CCS and Level 2 chargers your adapters unlock, then hands the route to Google Maps or guides you itself with GPS and voice.

**Open it:** <https://openixelai.github.io/Chargeline/>

On a phone, open the link in Safari or Chrome and use **Add to Home Screen** so it launches like an app.

## What it does

- From/To search like Google Maps, or tap the map to drop a start or destination
- Fastest charging plan: battery % on arrival and departure, charge time and clock times at every stop, adjusted for elevation and the weather forecast along the route
- Chargers color-coded by what your car can use: Tesla & NACS (red), CCS via adapter (purple), Level 2 (green)
- Add or remove stops yourself; the battery math updates instantly
- **Google Maps** button opens the whole trip with your charging stops as waypoints; each stop also has its own **Navigate** button
- **Send to car** opens the phone share sheet so you can pick the Tesla app
- **Start** gives turn-by-turn directions with GPS, spoken prompts and automatic rerouting

## Set these once

- **Your model** — Settings (top right). Defaults to Model Y Long Range.
- **Adapters you carry** — CCS1 and J1772 are on by default.
- **Free charger-data key** — the shared `DEMO_KEY` allows a few trips per hour. Get your own at <https://developer.nlr.gov/signup/> and paste it in Settings. It's stored only in your browser.

CCS adapter tip: on 2019–2020 builds, check **Controls → Software → Additional Vehicle Information** shows *CCS Adapter Support: Enabled*.

## Data sources

- Chargers: U.S. DOE Alternative Fuels Data Center, via NLR (formerly NREL)
- Routing: OSRM on OpenStreetMap
- Map tiles: © OpenStreetMap contributors (standard tiles, no key needed); satellite imagery and labels © Esri
- Elevation and forecast: Open-Meteo

Battery and time figures are estimates from your car profile. Stall availability isn't live, so check the Tesla app before committing to a third-party stop.

## Running it elsewhere

It's a single `index.html` with no build step. Any static host works (GitHub Pages, nginx, Caddy). Phone GPS needs the page served over HTTPS.
