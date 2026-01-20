# Vehicle Relay Distribution System (VRDS)
## Concept and Requirements – Phase 1

---

## 1. Goal of Phase 1.

Phase 1 defines a stable, purely hardware based bistable relay system for 12 V DC electrical systems in campervans.

The goal is a system that:

- operates without software or microcontrollers
- is modular and expandable
- strictly separates control and load paths
- is robust, durable and serviceable
- remains transparent and well documented

Phase 1 is the binding foundation for all future phases.

---

## 2. System boundaries and responsibility

- Use exclusively in 12 V DC systems
- Supply voltage approximately 11 to 14.4 V
- VRDS does not guarantee safety
- VRDS does not replace proper electrical planning
- Incorrect installation may cause damage or fire
- Installation only by qualified persons or with sufficient competence
- No warranty or liability

---

## 3. Relay principle and control philosophy

### 3.1 Bistable relays as the default

VRDS Phase 1 is explicitly designed around **bistable relays**.

Bistable relays change their state by a short control pulse and do not require continuous coil power to maintain that state.

Key characteristics:

- no holding current
- low power consumption
- reduced thermal stress
- state retention during power interruptions

This relay principle defines the entire control philosophy of Phase 1.

---

### 3.2 Control elements

Because of the bistable relay principle:

- momentary push buttons are the default control element
- latching switches are not required
- the electrical state of the button has no meaning by itself
- the relay state defines the system state

The real system state is always communicated via LEDs.

---

### 3.3 Monostable relays

Monostable relays are not the primary design target of Phase 1.

If monostable relays are used:

- continuous coil power is required
- additional thermal considerations apply
- control behavior differs from the bistable default

Such use cases are considered exceptions and are typically addressed in Phase 2.

---

## 4. System architecture

### 4.1 Master board

- One master board with eight bistable relays
- Fully functional on its own
- Provides centrally:
  - stabilized control voltage
  - stabilized LED supply
  - analog day night dimming
- No software
- No microcontroller

### 4.2 Slave boards

- Boards with 4, 6 or 8 bistable relays
- No own logic
- No own voltage regulation
- Control and LED supply from master board
- Power paths electrically independent

### 4.3 High power boards

- Separate boards using automotive relays
- Intended for loads beyond Phase 1 limits
- Control interface compatible with Phase 1

---

## 5. Channel definition

- One relay equals one channel
- Each channel is a fully defined functional unit
- All channels behave identically

---

## 6. Control flow description

The control flow of a VRDS Phase 1 channel is defined as follows:

1. A momentary push button is pressed
2. A short control pulse is applied to the relay input
3. The bistable relay toggles its mechanical state
4. The load contact opens or closes accordingly
5. The green status LED updates to reflect the relay state
6. If the channel fuse is blown, the red fault LED indicates the error condition

At no point does the push button carry load current.

The LED indication always reflects the actual relay and load state, never the button state.

---

## 7. On board test button

- Each channel includes a soldered micro push button
- Used for testing, commissioning and diagnostics
- Electrically identical to the external button input
- Not intended as a permanent user interface

---

## 8. Status and diagnostics

### 8.1 Green LED

- Indicates channel on off state
- Visible on the board
- Screw terminal for external status LED
- Current limiting integrated

### 8.2 Red LED

- Indicates a blown channel fuse
- Active when relay is on but no current flows
- Diagnostic function only

---

## 9. LED supply and day night dimming

- Mandatory part of Phase 1
- Stabilized against supply voltage variation
- Central analog day night dimming
- No software or controller involved
- Affects indication only, not relay operation

---

## 10. Fusing

### 10.1 Supply fusing

- Main supply must be fused at the source

### 10.2 Channel fusing

- Each channel individually fused
- Inline blade fuse directly after relay contact
- Fuse holder soldered on board
- Fuse located before output terminal

---

## 11. Current limits

- Nominal continuous current per channel: 4 A
- Maximum exceptional current: 6 A
- Fuses above 6 A are not permitted

Loads exceeding these limits must be handled outside Phase 1.

---

## 12. PCB traces and design reserve

- Load traces designed for at least 8 A per channel
- Output screw terminals rated for at least 8 A
- Fuse defines operational limit

---

## 13. Load supply input

- Exactly one load supply input per board
- Feeds all relays on the board

### 13.1 Mechanical implementation

- Stud or bolt pad
- Ring terminal connection
- No small PCB screw terminals

### 13.2 Supply cable

- 4 mm² nominal
- 6 mm² with reserve
- External source fusing required

---

## 14. Ground handling

- No load ground routed through VRDS
- Ground only used for control reference and LED logic
- Load ground handled externally

---

## 15. Plus only signal logic

- All board terminals are plus side only

### 15.1 Button wiring

- One common plus feed from master board to button panel
- Individual return lines per channel
- No ground return through VRDS

### 15.2 LED wiring

- VRDS supplies LED plus
- LED minus connected directly to vehicle ground

---

## 16. Connections

All connections are soldered and permanent:

- Load input via stud
- Load outputs via screw terminals
- Button inputs via screw terminals
- LED plus via screw terminals
- Control supply via screw terminal

No temporary or flying connections.

---

## 17. Mechanics

- Boards stackable or modularly mounted
- No electrical dependency due to proximity
- High power relays may be mounted separately

---

## 18. Philosophy

- transparent
- understandable
- serviceable
- no hidden logic
- no implicit return paths

---

## 19. Explicit non goals for Phase 1

- no software
- no bus system
- no addressing
- no automatic module detection
- no cloud integration
- no liability

---

**Status:**
Phase 1 is complete and frozen.

