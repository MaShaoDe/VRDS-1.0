# Changelog

All notable changes to the VRDS project are documented in this file.

The format follows the principles of Keep a Changelog.
This project uses semantic versioning where applicable.

---

## [Unreleased]

### Changed

- Defined mandatory use of transistor or MOSFET driver stages for all monostable automotive relays in Concept Phase 2
- Explicitly excluded direct relay coil switching via panel switches for monostable relays
- Updated system architecture to introduce a dedicated driver stage layer between control interface and relay layer
- Clarified separation between Phase 1 (bistable relays, impulse-driven) and Phase 2 (monostable relays, continuous coil current)
- Reduced continuous current load on switches and wiring harnesses by architectural design

### Added

- Driver stage concept as a core architectural element for Phase 2
- Architectural signal flow definitions for both system phases
- Design rationale regarding thermal, mechanical and EMC-related improvements

---

## [0.1.0] – Initial Concept Baseline

### Added

- Initial VRDS concept definition
- Phase-based relay strategy
- Bistable relay concept for manual switching
- Project structure and documentation baseline
