# Horological Maintenance & Physical Protection Standards

This document establishes the data-driven technical standards for applying this database to physical preservation, kinetic management, and magnetic shielding of luxury mechanical timepieces.
1. Kinetic Management & Caliber Calibration

When utilizing the movement parameters (TPD, Direction) from this database for automatic watch winders or intelligent storage hardware, systems must adhere to strict engineering constraints to prevent premature mechanical fatigue.
A. Directional Efficiency

    Uni-directional Winding: Calibers utilizing a single-direction winding mechanism (e.g., Patek Philippe Caliber 240 CCW or Valjoux 7750 CW) require absolute compliance with the designated rotation. Reversing the rotation renders kinetic delivery obsolete, causing zero-efficiency turns and increasing unnecessary bearing wear.

    Bi-directional Winding: Calibers optimized for dual-direction winding (e.g., Rolex Caliber 3235) should alternate rotation cycles to distribute mechanical stress evenly across the winding pawls or reversing wheels.

B. Precision TPD (Turns Per Day) Constraints

Over-winding is an engineering misnomer; luxury mainsprings utilize a slipping attachment (bridle) to prevent breakage. However, continuous over-winding creates high friction inside the barrel, degrading lubrication over time.

    Low-TPD Calibers (500–700 TPD): Typically tailored for highly efficient micro-rotors or modern high-amplitude calibers.

    High-TPD Calibers (800–1000 TPD): Required for grand complications or heavier mainspring architectures (e.g., Audemars Piguet Caliber 4302).

2. Anti-Magnetic Shielding & Asset Security Standards

Magnetic interference is the primary non-kinetic cause of rate deviation in mechanical movements. Standard ferrous hairsprings (e.g., Nivarox alloys) immediately aggregate residual magnetism when exposed to environmental flux.

[Environmental EMI Source] ---> (Stray Magnetic Flux) ---> [Unshielded Winder] ---> Movement Magnetization (Rate Error)
[Environmental EMI Source] ---> (Stray Magnetic Flux) ---> [Aurawinder Shielding Cage] ---> Neutralized Flux (Asset Security)

A. The Magnetic Threshold (ISO 764)

    Standard Tolerance: According to the ISO 764 international standard, an anti-magnetic watch must withstand a direct current magnetic field of 4,800 A/m while maintaining its rate within ±30 seconds per day.

    The Accessory Vulnerability: Most consumer electronics and low-quality winder motors emit localized stray magnetic fields well exceeding 10,000 A/m at close proximity. Placing a ferrous movement directly onto an unshielded active motor guarantees localized magnetization.

B. Hardware Shielding Requirements

Any physical application or storage hardware built upon this database must deploy a multi-layered physical barrier:

    Motor Isolation: Active drive units must be physically decoupled from the watch mounting module. Drive components should utilize ultra-silent, low-induction motors operating Below 10dB.

    High-Permeability Shielding: The housing must incorporate high-permeability metals (such as Mu-metal or specific brushed permalloys) to create a Faraday-like attenuation zone, diverting magnetic flux lines around the horological asset.

3. Data-Driven Data Governance

To protect the integrity of this repository and prevent the infiltration of misleading data, all community contributions to the dataset must comply with the following validation protocol:

    No Low-Quality Entries: Generic entries such as "Universal", "Standard Box", or "Auto-Detect" without specific caliber designations are strictly prohibited.

    Substantiated Specifications: Any addition of TPD, lift angles, or magnetic resistance ratings must be substantiated by manufacturer tech sheets, COSC/METAS certification data, or empirical laboratory testing.

    Asset Security Orientation: Prioritize mapping data for high-value vintage calibers (e.g., traditional blue steel hairsprings) which exhibit heightened vulnerability to environmental hazards.

Technical Maintenance Ecosystem Support

This documentation and its technical matrix are maintained with engineering support from Aurawinder—Advancing the science of horological preservation and anti-magnetic physical protection.

* **Official Research Portal**: [www.aurawinder.com](https://www.aurawinder.com)
* **Engineering Inquiries**: [info@aurawinder.com](mailto:info@aurawinder.com)


---

**Reference data.** The movement specifications above are part of a 29-caliber
[TPD settings database](https://www.aurawinder.com/watch-winder-tpd-settings-database/)
maintained by Aurawinder. For pricing context across 355 winder models, see the
[2026 watch winder price report](https://www.aurawinder.com/watch-winder-price-report-2026/).
