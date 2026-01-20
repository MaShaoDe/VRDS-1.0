# VRDS – Vehicle Relay Distribution System

VRDS is a modular relay-based distribution system designed for automotive and campervan applications, focusing on reliability, clarity and long-term robustness.

---

## Core Design Principles

- Clear separation between control and power domains
- Automotive-grade reliability
- Reduced thermal and mechanical stress
- Predictable electrical behaviour

---

## System Phases

### Phase 1 – Bistable Relays

- Impulse-driven bistable relays
- No continuous relay coil current
- Direct interaction with switches possible
- Optimised for manual control scenarios

---

### Phase 2 – Monostable Automotive Relays

- Classic monostable automotive relays (typically 30–40 A)
- Continuous coil current during activation
- Relay coils are driven exclusively via transistor or MOSFET driver stages
- Panel switches never carry relay coil current

This approach protects switches, reduces wiring load and improves system longevity.

---

## Architectural Summary

Control Interface  
→ Driver Stage (Phase 2)  
→ Relay  
→ Load

Direct switching of monostable relay coils via panel switches is intentionally excluded.

---

## Project Status

VRDS is under active development.  
Design decisions documented in the concept and architecture files are binding for all future extensions.

---

## License

See LICENSE file.
