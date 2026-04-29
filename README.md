# FlightBoard Community

This repository is the community contribution layer for **FlightBoard** — a VATSIM flight information display system (FIDS) that shows live departures and arrivals for virtual airports.

Live application: **[flightboard.simfixr.com](https://flightboard.simfixr.com)**

---

## What's in this repo

This is not the core application. The FlightBoard engine (Python/Flask backend, JavaScript frontend, socket layer) is proprietary. This repository contains only the parts that the community can contribute to:

| Path | Contents |
|---|---|
| `static/css/themes/` | One CSS file per airport — controls colours, fonts, and layout styling |
| `data/airports.json` | Airport registry — ICAO codes, display names, geofencing ceilings, theme mappings |
| `docs/` | Contribution guides |

---

## How to contribute

**New airport theme:** create a CSS file in `static/css/themes/` scoped to `body.theme-<icao>` and add the airport entry to `data/airports.json`. See [`CONTRIBUTING.md`](CONTRIBUTING.md) for CSS conventions and [`docs/adding-an-airport.md`](docs/adding-an-airport.md) for the full field reference.

**Existing theme improvement:** fork the repo, edit the CSS file, submit a pull request.

**Stand data:** stand coordinates are not part of this repo. Contact Taz via [simfixr.com](https://www.simfixr.com) if you want to contribute stand data for a new airport.

---

## Stand data attribution

Stand coordinate data for Scandinavian airports is sourced from [VATSIM Scandinavia](https://vatsim-scandinavia.org) GRPlugin sector files, used under a non-commercial attribution licence. The VATSIM Scandinavia logo is displayed in the app footer whenever a Scandinavian airport is active. See [`docs/scandinavia_attribution.md`](docs/scandinavia_attribution.md) for details.

---

## Licence

Airport themes and registry data in this repository are licensed under [Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](LICENSE.md).

The core FlightBoard application is proprietary software. Copyright © 2026 Taz Mattar / Simfixr.

---

## Contact

- Website: [simfixr.com](https://www.simfixr.com)
- Live board: [flightboard.simfixr.com](https://flightboard.simfixr.com)
