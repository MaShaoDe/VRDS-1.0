# VRDS – Concept Phase 2  
## Monostable Automotive Relays and Active Driver Stages

### Scope of Phase 2

Concept Phase 2 extends the VRDS system with classic monostable automotive relays (typically 30–40 A), mainly used for automatic or logic-controlled switching scenarios.

Unlike Phase 1, which is based on bistable relays with impulse operation, Phase 2 explicitly avoids any direct relay coil control via panel switches.

---

### Fundamental Design Decision

All monostable automotive relays in Phase 2 are driven exclusively via an active driver stage.

Direct switching of relay coils through panel switches is explicitly excluded.

This decision is mandatory and applies to all Phase 2 implementations.

---

### Reasons for Using Driver Stages

The driver stage concept is used for the following reasons:

- Mechanical and thermal relief of panel switches  
- Elimination of continuous relay coil current through control panels  
- Reduced current load in wiring harnesses  
- Improved reliability in automotive environments  
- Better EMC behaviour and reduced inductive stress  
- Clear separation between control level and power level  

Even though typical relay coil currents (approx. 120–180 mA at 12 V) may appear low, continuous operation via small switches leads to contact heating, ageing and unpredictable long-term behaviour.

---

### Driver Stage Characteristics

Each monostable relay coil is controlled by one of the following:

- Transistor driver stage (BJT)
- Logic-level MOSFET driver stage (preferred)

Mandatory characteristics:

- Relay coil powered directly from the supply rail
- Switches handle only logic-level current
- Flyback protection (diode or equivalent) directly at the relay coil
- Defined ground reference and short return paths

The driver stage acts as the only electrical interface between control logic and relay coil.

---

### Separation of System Phases

- Phase 1  
  Bistable relays  
  Impulse-driven  
  No continuous coil current  
  Direct switch interaction acceptable

- Phase 2  
  Monostable automotive relays  
  Continuous coil current during activation  
  Active driver stage required  
  No direct switch-to-coil connection

This separation is intentional and forms a core architectural principle of VRDS.

---

### Resulting Benefits

- Longer switch lifetime
- Reduced thermal stress in panels
- Cleaner wiring architecture
- Higher robustness under vibration and temperature variation
- Clear and maintainable electrical structure

Phase 2 is therefore optimised for durability, serviceability and automotive-grade operation.

