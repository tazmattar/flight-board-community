# Adding a New Airport

## Minimal airport (no custom branding)

Add one entry to `data/airports.json` following the field reference below. The airport will appear in the selector using the default theme.

```json
"OMDB": {
  "name": "Dubai International",
  "selector_label": "Dubai International Airport",
  "ceiling": 6000,
  "has_stands": false,
  "theme_css": "/static/css/themes/default.css",
  "theme_class": "theme-default",
  "title_case": false,
  "flags": null,
  "footer_country": null,
  "group": "Middle East"
}
```

Submit a pull request with the `airports.json` change. That's it.

---

## Fully themed airport

### 1. Add to `data/airports.json`

```json
"OMDB": {
  "name": "Dubai International",
  "selector_label": "Dubai International Airport",
  "ceiling": 6000,
  "has_stands": false,
  "theme_css": "/static/css/themes/omdb.css",
  "theme_class": "theme-omdb",
  "title_case": false,
  "flags": null,
  "footer_country": null,
  "group": "Middle East"
}
```

### 2. Create `static/css/themes/omdb.css`

Scope all rules to `body.theme-omdb`. See `CONTRIBUTING.md` for the full CSS conventions, but the key rules:

- Status colours: `body.theme-omdb .col-status[data-status="Boarding"] { color: #... !important; }`
- Title case text (if `title_case: true`): add `text-transform: none` to `.flight-table th` and `.col-status .flap-container`
- Do **not** use `!important` on `.widget-icon` colour — breaks the ATC radar animation

Look at `eglc.css` or `egcc.css` as simple reference themes.

### 3. Submit a pull request

Include both the `airports.json` entry and the CSS file in one PR.

---

## Optional fields

### Multi-country flags
```json
"flags": ["ae", "xx"]
```
Uses ISO 3166-1 alpha-2 country codes. `null` lets the app auto-detect from ICAO prefix.

### Move flags to footer-left
```json
"flags_position": "left"
```

### Override gate label in footer
```json
"gate_label_override": "Gates"
```

### Override footer language/country
```json
"footer_country": "United Arab Emirates"
```

---

## Stand data

Stand coordinate data is not part of this repository. If you'd like to contribute stand data for a new airport, contact Taz directly via [simfixr.com](https://www.simfixr.com). Leave `"has_stands": false` in your PR.

---

## Field reference

| Field | Type | Notes |
|---|---|---|
| `name` | string | Shown in the board header |
| `selector_label` | string | Shown in the airport dropdown |
| `ceiling` | int | Geofencing altitude in feet — how high aircraft can be and still appear on the board |
| `has_stands` | bool | Whether stand data exists for this airport — leave `false` in community PRs |
| `theme_css` | string | Path to CSS file, e.g. `/static/css/themes/omdb.css` |
| `theme_class` | string | Body class applied when active, e.g. `theme-omdb` |
| `title_case` | bool | `true` = Title Case status text, `false` = UPPERCASE |
| `flags` | array\|null | ISO country codes e.g. `["ch", "fr"]`. `null` = auto-detect |
| `flags_position` | string\|null | `"left"` to move flags to footer-left group |
| `footer_country` | string\|null | Country name for footer language. `null` = auto-detect |
| `gate_label_override` | string\|null | Overrides the gate/stand label in the footer |
| `group` | string\|null | Dropdown group label — use one of: `"United Kingdom"`, `"Scandinavia"`, `"Western Europe"`, `"North America"`, `"Middle East"`, `"Asia Pacific"`. `null` = appears under "Other" |
