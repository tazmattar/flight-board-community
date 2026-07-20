# FlightBoard

**FlightBoard** is a VATSIM flight information display system (FIDS) showing live departures and arrivals for virtual airports, with a live traffic map, real-world-styled airport boards, and Navigraph-powered route data.

Live application: **[flightboard.simfixr.com](https://flightboard.simfixr.com)**

---

## Where to get help or report something

**Discord is the fastest route — [join here](https://discord.gg/kVUM9tYTN).** Bug reports, feature requests, questions and airport suggestions all belong there.

If you'd rather not use Discord, you can [open an issue](https://github.com/tazmattar/flight-board-community/issues) on this repository instead. Both are read by the same person.

---

## What this repository is

This is the **public home for FlightBoard's documentation, licensing and user reports**. The application itself — Python/Flask backend, JavaScript frontend, socket layer — is proprietary and lives in a private repository.

It previously also hosted airport theme CSS and the airport registry for community pull requests. Those were removed once FlightBoard gained a built-in theme builder: themes are now generated from a token-based design system through an admin interface with live preview, so hand-written CSS files are no longer how airport boards get made. The old files remain in this repository's git history.

---

## Why is the core application private?

FlightBoard integrates with third-party APIs — including Navigraph — whose terms require the implementation to remain closed-source.

---

## Contributing

Two kinds of contribution are genuinely useful and still very welcome:

- **Stand data** for an airport — improves gate detection accuracy
- **Virtual airline logos** — if you run a VA flying on VATSIM

See [`CONTRIBUTING.md`](CONTRIBUTING.md) for what's needed and how to send it.

**Airport suggestions:** you don't need to build anything. Ask on [Discord](https://discord.gg/kVUM9tYTN) and the airport can be added and themed directly.

---

## Stand data attribution

Stand coordinate data for Scandinavian airports is sourced from [VATSIM Scandinavia](https://vatsim-scandinavia.org) GRPlugin sector files, used under a non-commercial attribution licence. The VATSIM Scandinavia logo is displayed in the app footer whenever a Scandinavian airport is active. See [`docs/scandinavia_attribution.md`](docs/scandinavia_attribution.md) for details.

---

## Licence

Documentation in this repository is licensed under [Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](LICENSE.md).

The FlightBoard application is proprietary software. Copyright © 2026 Taz Mattar / Simfixr.

---

## Contact

- Discord: **https://discord.gg/kVUM9tYTN** (preferred — issues, feature requests and questions)
- Website: [simfixr.com](https://www.simfixr.com)
- Live board: [flightboard.simfixr.com](https://flightboard.simfixr.com)
