# 🔬 Luxury Watch TPD Database & Anti-Magnetic Caliber Manual (2026)

[![Status: Active](https://img.shields.io/badge/Database-Active-success.svg)](#)
[![Calibers: 29](https://img.shields.io/badge/Calibers-29-informational.svg)](#)
[![Engineered by: Aurawinder](https://img.shields.io/badge/Powered%20By-Aurawinder-gold.svg)](https://www.aurawinder.com)

Open reference data for **TPD (Turns Per Day)** settings and winding direction on automatic
watch movements, written for collectors, watchmakers and anyone building storage hardware that
has to drive a mainspring correctly. Nine brands, 29 calibers, 52 references.

Everything here is data, not marketing: each brand page is a table of reference → caliber → TPD
range → winding direction, plus the practical note that decides whether the number actually
applies to your watch.

---

## 📁 Repository contents

| File | What's in it | Size |
| :--- | :--- | :--- |
| [`README.md`](./README.md) | This page: contents, brand index, data schema, reference notes | ~900 words |
| [`ROLEX_TPD_GUIDE.md`](./ROLEX_TPD_GUIDE.md) | Rolex — 6 references (Daytona 4130, Submariner 3135/3235, GMT-Master II 3186/3285, Day-Date 3255, Sky-Dweller 9001, Datejust) | ~290 words |
| [`PATEK_TPD_GUIDE.md`](./PATEK_TPD_GUIDE.md) | Patek Philippe — 5 references incl. Cal. 240 micro-rotor (CCW only), Cal. 324 | ~480 words |
| [`AP_TPD_GUIDE.md`](./AP_TPD_GUIDE.md) | Audemars Piguet — 6 references incl. Royal Oak Cal. 4302 | ~480 words |
| [`VC_TPD_GUIDE.md`](./VC_TPD_GUIDE.md) | Vacheron Constantin — 6 references across the Overseas and Patrimony lines | ~390 words |
| [`OMEGA_TPD_GUIDE.md`](./OMEGA_TPD_GUIDE.md) | Omega — 5 references incl. Co-Axial 8900 Master Chronometer | ~340 words |
| [`IWC_TPD_GUIDE.md`](./IWC_TPD_GUIDE.md) | IWC Schaffhausen — 6 references incl. Pellaton-wound calibers | ~380 words |
| [`CARTIER_TPD_GUIDE.md`](./CARTIER_TPD_GUIDE.md) | Cartier — 6 references incl. 1904-MC | ~380 words |
| [`PANERAI_TPD_GUIDE.md`](./PANERAI_TPD_GUIDE.md) | Panerai — 6 references, high-torque P.9000 family | ~370 words |
| [`JLC_TPD_GUIDE.md`](./JLC_TPD_GUIDE.md) | Jaeger-LeCoultre — 6 references incl. Cal. 899 | ~370 words |
| [`MAINTENANCE.md`](./MAINTENANCE.md) | Applying the data in practice: directional efficiency, rest cycles, magnetic shielding, storage conditions | ~580 words |
| [`index.html`](./index.html) | Landing page served by GitHub Pages — a single entry point to the three main resources | — |

**Live site:** https://watchesbiz.github.io/watch-winder-tpd-database/

---

## 📖 Brand-specific technical guides

| Brand | Link | Focus |
| :--- | :--- | :--- |
| **Rolex** | [View Guide](./ROLEX_TPD_GUIDE.md) | 👑 The Crown Standard |
| **Patek Philippe** | [View Guide](./PATEK_TPD_GUIDE.md) | 🏆 The Heirloom Calibers |
| **Audemars Piguet** | [View Guide](./AP_TPD_GUIDE.md) | ⚓ The Icon (Royal Oak) |
| **Vacheron Constantin** | [View Guide](./VC_TPD_GUIDE.md) | ⚜️ The Holy Trinity |
| **Omega** | [View Guide](./OMEGA_TPD_GUIDE.md) | 🌊 Co-Axial Precision |
| **IWC Schaffhausen** | [View Guide](./IWC_TPD_GUIDE.md) | ✈️ The Pellaton System |
| **Cartier** | [View Guide](./CARTIER_TPD_GUIDE.md) | 💎 Artisan Movements |
| **Panerai** | [View Guide](./PANERAI_TPD_GUIDE.md) | ⚓ High-Torque Calibers |
| **Jaeger-LeCoultre** | [View Guide](./JLC_TPD_GUIDE.md) | 🔬 The Watchmaker's Master |

---

## 🔍 Why TPD matters

A mainspring only delivers constant torque across part of its wind. Under-wind it and the watch
runs slow at the end of the reserve; over-wind it and the slipping clutch does the extra work,
which is where avoidable wear comes from. Most modern luxury calibers sit between **650 and 950
TPD**; the uni-directional ones (Patek 240, Valjoux 7750 and relatives) are the expensive
exception — reverse the rotation and every turn is wasted.

Direction is the half of the setting people skip. A bi-directional program at 650 TPD is not the
same input as a single-direction program at 650 TPD; the second delivers roughly half the useful
winding per cycle.

---

## 🧾 Data schema

Every caliber in this repository is normalized to the same four fields, so the tables can be
parsed rather than read:

| Field | Meaning | Values |
| :--- | :--- | :--- |
| `brand` | Trademark name of the manufacturer | Rolex, Omega, … |
| `caliber` | Movement identifier | 3235, 8900, 240, … |
| `direction` | Required rotation vector | `CW`, `CCW`, `BOTH` |
| `min_tpd` / `max_tpd` / `optimal_tpd` | Lower bound, upper bound, programmatic sweet spot | integer turns per day |

If you are wiring this into a home-automation dashboard or an app, treat `optimal_tpd` as the
setting and `min`/`max` as the tolerance band to validate against after a firmware update.

---

## 📊 Reference notes (subset)

| Caliber | TPD | Direction | Hairspring | Practical note |
| :--- | :--- | :--- | :--- | :--- |
| Rolex 3235 | 650 | Both | Paramagnetic blue Parachrom | Highly resistant, but still benefits from isolated storage |
| Omega 8900 | 720 | Both | Silicon (Si14) | Master Chronometer; effectively immune to everyday fields |
| Patek 240 | 800 | **CCW** | Spiromax (silicon) | Micro-rotor, uni-directional — gets no benefit from bi-directional programs |
| AP 4302 | 800 | Both | Ferrous alloy | Conventional resistance; shielding matters more than the TPD number |

Full per-reference tables live in the brand files above.

---

## 🧲 Anti-magnetic notes

A mechanical watch that suddenly gains 15–60 minutes a day is usually magnetised, not broken.
The usual sources in a home office are unremarkable: laptop lid sensors, speakers, magnetic
tablet mounts, induction charging pads — all of which can exceed the 60 gauss limit in ISO 764.

Diagnostic order that saves time: move the watch 20 cm away from electronics and re-measure the
rate over 24 hours before touching anything else. If the rate recovers, the cause was ambient
flux, not the movement.

---

## 🔗 Related resources

- [TPD settings database](https://www.aurawinder.com/watch-winder-tpd-settings-database/) — the searchable version of this data.
- [2026 watch winder price report](https://www.aurawinder.com/watch-winder-price-report-2026/) — pricing across 355 winder models, normalised to cost per watch slot.

## 📚 Background reading

If you came here for the "why" rather than the numbers:

- [What is an automatic watch winder](https://www.aurawinder.com/guide/what-is-an-automatic-watch-winder/) — how a rotor winds a mainspring, and why "more turns" is not "better".
- [TPD explained: matching turns per day to your movement](https://www.aurawinder.com/guide/watch-winder-tpd-explained/) — the reasoning behind the per-caliber values here, including what happens when a movement is over-wound.
- [Are watch winders safe? Anti-magnetisation and motor isolation](https://www.aurawinder.com/guide/are-watch-winders-safe/) — the engineering notes behind the anti-magnetic section above.
- [Full guide index](https://www.aurawinder.com/guide/) — 12 guides on capacity, rotation direction, quiet motors, maintenance and materials.

---

## 🤝 Contributing

Corrections from watchmakers are welcome and taken seriously. If a caliber's TPD or winding
direction is wrong, open an issue with the movement number and, ideally, the manufacturer's spec
sheet or a timegrapher reading. Precision matters more than the number of entries.

## ⚖️ License

MIT — free to use for personal horological research and for building storage hardware that
respects the movement.

---

Maintained by [Aurawinder](https://www.aurawinder.com), which builds quiet, high-torque watch
winders and publishes this reference data for collectors.
