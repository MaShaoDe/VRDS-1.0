# Vehicle Relay Distribution System (VRDS)
## Concept and Requirements – Phase 2 (High Power, Automotive Relays)

---

## 1. Purpose of Phase 2

Phase 2 extends the VRDS with a dedicated solution for high current loads using automotive relays.

Phase 2 does not modify Phase 1.
Phase 1 remains complete and frozen.

The purpose of Phase 2 is to handle loads that exceed the electrical and thermal limits of Phase 1 channels.

---

## 2. Fundamental difference to Phase 1

Phase 2 intentionally differs from Phase 1 in relay type and control philosophy.

- Phase 1 uses bistable relays and push buttons
- Phase 2 uses monostable automotive relays and switches

This difference is deliberate and required by the characteristics of high power automotive relays.

---

## 3. Relay principle in Phase 2

### 3.1 Monostable automotive relays

Phase 2 is based on **monostable automotive relays**.

Monostable relays:

- require continuous coil power to remain activated
- return to a defined default state when power is removed
- are widely available in high current ratings
- are mechanically robust and vehicle proven

Typical ratings include 30 A, 40 A and higher, depending on relay type.

Because bistable automotive relays are rare, expensive or unavailable for many use cases, monostable relays are the practical and preferred choice in Phase 2.

---

## 4. Control philosophy in Phase 2

### 4.1 Use of switches instead of push buttons

Due to the use of monostable relays, Phase 2 is designed to be operated with **latching switches**, not momentary push buttons.

Key properties:

- switch position directly represents relay and load state
- continuous coil power is applied while the switch is on
- switching behavior is intuitive and immediately visible
- no internal state memory is required

Push buttons are not suitable as the primary control element in Phase 2.

---

### 4.2 Control signal behavior

- Switch ON:
  - relay coil energized
  - load switched on
- Switch OFF:
  - relay coil de-energized
  - load switched off

The electrical state of the switch directly defines the system state.

---

## 5. Architecture options

### 5.1 Phase 2 slave board

- board with automotive relay sockets
- high current terminals or studs
- individual fusing per channel
- control inputs designed for switch operation
- compatible control voltage with Phase 1 master board

### 5.2 Distributed relay layout

- relays mounted off board
- DIN rail or relay carriers
- wiring harness connection
- identical switch based control logic

---

## 6. Power handling and fusing

- high current supply must be fused at the source
- each load must be fused individually
- fuse ratings matched to cable size and load
- relays protected against overload and overheating

---

## 7. Ground handling

- VRDS does not route load ground
- load ground connected externally
- no ground loops through VRDS

---

## 8. Optional extensions

Phase 2 may include optional features such as:

- current measurement via shunt
- temperature monitoring at relays
- undervoltage protection
- delayed switching or interlocks

These features are optional and not required for basic operation.

---

## 9. Explicit non goals of Phase 2

- Phase 2 does not change Phase 1 behavior
- Phase 2 does not require software by default
- Phase 2 does not introduce cloud connectivity
- Phase 2 does not guarantee safety

---

**Status:**
Phase 2 control philosophy is defined.
Implementation details remain open.

