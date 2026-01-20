# VRDS – System Architecture

## Overview

The Vehicle Relay Distribution System (VRDS) is structured into clearly separated functional layers to ensure robustness, scalability and long-term reliability.

This document describes the logical and electrical architecture independent of specific hardware implementations.

---

## Functional Layers

### 1. Control Interface Layer

- Panel switches
- Buttons
- Logic inputs

Characteristics:

- Low current
- No direct power switching
- Human-machine interface only

---

### 2. Driver Stage Layer

The driver stage forms the electrical boundary between control inputs and relay hardware.

Functions:

- Current amplification
- Electrical isolation between control and relay coil
- Protection against inductive loads

Typical implementations:

- Transistor driver stages
- Logic-level MOSFET stages

This layer is mandatory for all monostable relay implementations.

---

### 3. Relay Layer

- Bistable relays (Phase 1)
- Monostable automotive relays (Phase 2)

Characteristics:

- Handles inductive loads
- Switches supply power to consumers
- Electrically separated from control interfaces

---

### 4. Load and Distribution Layer

- Consumers
- Fused power distribution
- External wiring and connectors

---

## Signal Flow

### Phase 1 (Bistable Relays)

Control Interface  
→ Relay (impulse-driven)  
→ Load

---

### Phase 2 (Monostable Relays)

Control Interface  
→ Driver Stage  
→ Relay (continuous coil current during activation)  
→ Load

Direct control interface to relay connections are not permitted in Phase 2.

---

## Architectural Principles

- Control elements never carry relay coil current
- Wiring harnesses are relieved from unnecessary continuous current
- Relay coils are always driven via defined electronic stages
- Power and control domains remain clearly separated

---

## Design Intent

This layered architecture ensures:

- Predictable electrical behaviour
- Reduced thermal stress
- Improved EMC characteristics
- High maintainability
- Automotive-grade reliability

All future VRDS extensions must respect this architecture.
