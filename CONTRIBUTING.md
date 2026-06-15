# Contributing to FlightBoard

Thank you for your interest in contributing. This repository contains the community layer of FlightBoard — airport themes and the airport registry. The core application is proprietary and not part of this repo.

There are two ways to contribute:

---

## 1. Adding or improving an airport theme (CSS)

Theme files live in `static/css/themes/` — one CSS file per airport, named `<icao_lowercase>.css`.

**Conventions:**

- Scope every rule to `body.theme-<icao>` to prevent bleed into other themes:
  ```css
  body.theme-omdb .flight-table th { ... }
  ```
- Status colours use the `data-status` attribute on `.col-status`:
  ```css
  body.theme-omdb .col-status[data-status="Boarding"] { color: #00b050 !important; }
  body.theme-omdb .col-status[data-status="Departed"]  { color: #888 !important; }
  ```
  Text colour only — no background colours on status cells. Use `!important` to beat the global stylesheet.
- Gate column has class `col-gate` for theme-specific gate cell styling.
- Do **not** use `!important` on `.widget-icon` colour — it blocks the ATC radar-pulse CSS animation.
- To suppress uppercase from the global stylesheet, add (with `!important` if needed):
  ```css
  body.theme-omdb .flight-table th          { text-transform: none; }
  body.theme-omdb .col-status .flap-container { text-transform: none; }
  ```
- Use `eglc.css` or `egcc.css` as simple reference themes. `eddf.css` is a more advanced example with custom animations.

**Steps:**
1. Fork this repo
2. Create `static/css/themes/<icao>.css`
3. Add or update the airport entry in `data/airports.json` (see below)
4. Submit a pull request

---

## 2. Adding an airport to the registry (`data/airports.json`)

See `docs/adding-an-airport.md` for the full field reference and examples.

**Required fields for a PR:**

```json
"ICAO": {
  "name": "Airport Name",
  "selector_label": "Full Display Name in Dropdown",
  "ceiling": 6000,
  "has_stands": false,
  "theme_css": "/static/css/themes/icao.css",
  "theme_class": "theme-icao",
  "title_case": false,
  "flags": null,
  "footer_country": null,
  "group": "Western Europe"
}
```

- Set `"has_stands": false` — stand data contributions are handled separately (see below).
- `group` should be one of: `"United Kingdom"`, `"Scandinavia"`, `"Western Europe"`, `"North America"`, `"Middle East"`, `"Asia Pacific"`, or `null`.

---

## 3. Stand data contributions

Stand coordinate data is not part of this repository. Stand positions require careful manual verification against satellite imagery — even small errors break gate detection (the geofencing radius is 35 m).

If you want to contribute stand data for an airport, contact Taz directly via [simfixr.com](https://www.simfixr.com).

---

## 4. Airline logos (virtual airlines)

Real-world airline logos are pulled automatically by IATA code. Virtual / VATSIM-specific airlines aren't on any public logo CDN, so adding one requires a logo asset plus a small mapping in the core application — not something this repo's PRs can cover (CSS/JSON only, see above).

If you represent a virtual airline and would like your logo added, email Taz directly at [info@simfixr.com](mailto:info@simfixr.com) with:

- The ICAO callsign prefix(es) your airline uses on VATSIM
- A transparent PNG logo (square works best)

---

## Pull request guidelines

- One airport (or small set of related airports) per PR — keeps reviews focused
- CSS only — do not include changes to Python, JavaScript, HTML templates, or any file not listed in the repo
- Test your colour choices against the live board at [flightboard.simfixr.com](https://flightboard.simfixr.com) if possible
- Verify the ICAO code against the official ICAO airport designators list

---

## Licence

By contributing to this repository you agree that your contributions are licensed under [Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](LICENSE.md).
