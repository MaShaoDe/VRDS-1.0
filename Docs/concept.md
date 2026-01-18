# Vehicle Relay Distribution System (VRDS)
## Technical Concept

## 1. Objective

The Vehicle Relay Distribution System (VRDS) is a modular relay base board designed for 12 V vehicle electrical systems, primarily for campervans and similar mobile applications. Its purpose is to decouple user interface elements, logic and status indication from high load currents, enabling a robust, service friendly and expandable architecture.

Small and delicate push buttons or switches in the control panel shall only carry minimal control currents. Load currents up to approximately 8 or 10 A are switched exclusively by relays mounted on the base board. Higher loads are handled by automotive relays, which are also driven by the base board.

The system is intentionally kept simple, transparent and repairable. No active control electronics are mandatory.

## 2. Basic Principle

The VRDS clearly separates three functional layers:

1. Control layer
User interface with small push buttons or switches carrying minimal current

2. Relay and distribution layer
Bistable or monostable relays mounted on the base board
Fusing and power distribution

3. Load layer
Direct supply of consumers or control of automotive relays

The actual switching state is always derived from the relay itself, never from the control input.

## 3. Relay Concept

### 3.1 Level 1: Base Relays

The base board hosts multiple bistable or monostable 12 V PCB mounted relays.

Characteristics:
- Switching current typically 8 to 10 A
- Suitable for lighting, pumps, fans, small heaters
- Bistable relays preferred due to zero holding current
- Each channel individually fused

### 3.2 Level 2: Automotive Relays

For higher loads, standard automotive relays are used.

Characteristics:
- Switching current 30 to 40 A
- Relay sockets mounted directly on the board
- Relays are plug in and replaceable
- Controlled either by a base relay output or directly by a switch

Automotive relays are used exclusively for high power switching.

## 4. State Feedback

### 4.1 Principle

Each relay channel provides an unambiguous feedback signal indicating the current switching state. The indication always reflects the real relay state, independent of the control input or previous states.

### 4.2 Implementation

- Dedicated status output per channel
- Derived directly from the relay contact
- No possible back feeding into the control circuitry

### 4.3 Panel Connection

- Two pin connector per channel
- Automotive grade snap in connector
- Polarity protected and vibration resistant
- Suitable for:
  - Illuminated switches
  - Separate panel mounted LEDs

The LED series resistor is located on the base board.

### 4.4 Electrical Characteristics of Status Output

- Supply voltage 12 to 14.4 V
- Typical LED current 2 to 10 mA
- Short circuit protected
- No logical dependency on the control input

## 5. Protection and Safety

- Individual fuse per load channel
- Automotive blade fuses or PTC devices
- Optional separate fuse for control layer
- Flyback diodes or equivalent protection for relay coils
- Centralized and defined ground reference point

## 6. Mechanical Concept

- Screw terminals for all load connections
- Plug connectors for control and status signals
- Board suitable for screw mounting or DIN rail mounting
- Automotive relays mechanically fixed and plug in
- Modular expansion using identical boards

## 7. Optional 12 V Filter and Stabilization Module

### 7.1 Objective

An optional hardware module providing filtering and stabilization of the 12 V supply for the control and relay logic. The base system operates fully without this module.

### 7.2 Function

- Suppression of voltage spikes
- Filtering of high frequency noise
- Buffering of short voltage drops
- Protection of control circuitry

### 7.3 Technical Scope

Input:
- 9 to 16 V vehicle supply

Protection:
- Reverse polarity protection
- TVS diode
- Dedicated fuse

Filtering:
- LC or pi filter
- Ceramic capacitors
- Electrolytic capacitor for low frequency smoothing

Optional stabilization:
- Filter only, or
- Regulated 12 V using step down or buck boost converter

### 7.4 Integration

- Plug in module or small daughter board
- Clearly defined input and output interfaces
- Load power path remains unfiltered

## 8. Phase Model

### Phase 1 Mandatory

- Switching of 12 V loads up to 8 or 10 A
- Control via push buttons or switches
- State feedback per channel
- Individual fusing
- Screw terminals and plug connectivity
- No active logic required

### Phase 1 Nice to Have

- Status LED per channel
- Selectable high side or low side status switching
- Automotive relay option
- Measurement test points

### Phase 2 Extensions

- Optional MCU integration
- Per channel current measurement
- Stackable boards
- Galvanic isolation of control layer

## 9. Design Principles

- Robustness over complexity
- Repairability and transparency
- No unnecessary electronics
- Modular expandability
- Documentation as part of the system

## 10. Documentation and GitHub Structure

- README.md providing project overview
- Docs directory containing:
  - Concept.md
  - Requirements.md
  - Switching_Principle.md
  - Safety.md
- Hardware directory:
  - Schematics
  - PCB layout
  - BOM
- Version history

End of concept

