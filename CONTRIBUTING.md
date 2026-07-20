# Contributing to FlightBoard

Thank you for your interest. FlightBoard's application code is proprietary and lives in a private repository, so this repo doesn't take code pull requests. Everything below is still genuinely useful, and all of it is welcome.

---

## 1. Reporting a bug or requesting a feature

**[Discord](https://discord.gg/kVUM9tYTN) is the fastest route**, but a [GitHub issue](https://github.com/tazmattar/flight-board-community/issues) works just as well if you prefer.

What helps most:

- The **airport** (ICAO code) and whether you were on the board or the live map
- The **callsign** involved, if it's about a specific flight
- What you expected versus what you saw
- A screenshot — especially for anything visual
- Roughly **when** it happened, so it can be matched against the VATSIM feed

Small details matter more than polish. "EGLL arrivals showed WAIT for 20 minutes after landing at about 19:30Z" is a great report.

---

## 2. Airport suggestions

You don't need to build anything. Ask on [Discord](https://discord.gg/kVUM9tYTN) or open an issue naming the airport, and it can be added and themed directly — airport boards are now built with FlightBoard's built-in theme builder rather than hand-written CSS.

---

## 3. Stand data

Stand coordinates drive gate detection, and accuracy matters: the geofencing radius is 35 m, so even small errors put aircraft on the wrong stand. Positions need careful manual verification against satellite imagery.

If you'd like to contribute stand data for an airport, get in touch on [Discord](https://discord.gg/kVUM9tYTN) or via [simfixr.com](https://www.simfixr.com) before starting, so the format and the airport's current status can be confirmed.

---

## 4. Virtual airline logos

Real-world airline logos are pulled automatically by IATA code. Virtual and VATSIM-specific airlines aren't on any public logo CDN, so adding one needs a logo asset plus a small mapping in the application.

If you represent a virtual airline and would like your logo on the boards, email [info@simfixr.com](mailto:info@simfixr.com) with:

- The ICAO callsign prefix(es) your airline uses on VATSIM
- A transparent PNG logo (square works best)

---

## Licence

By contributing to this repository you agree that your contributions are licensed under [Creative Commons Attribution-NonCommercial 4.0 International (CC BY-NC 4.0)](LICENSE.md).
