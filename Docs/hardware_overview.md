# Hardware Overview

## Purpose

This document describes the physical hardware layers of the Vehicle Relay Distribution System (VRDS).  
It provides a structured overview of required and optional hardware components without defining exact part numbers or layouts.

All detailed electrical designs and component selections derive from this overview.

## Hardware Layers

VRDS hardware is structured into distinct layers to ensure robustness, serviceability and modularity.

The primary layers are:

- Power Input Layer
- Protection Layer
- Power Distribution Layer
- Control Layer
- Relay Layer
- Status and Interface Layer

Each layer has a clearly defined role and interface.

## Power Input Layer

The power input layer connects VRDS to the vehicle electrical system.

Characteristics:
- Designed for automotive DC environments
- Supports a defined voltage input range
- Mechanically robust connection method

Responsibilities:
- Accept vehicle supply voltage
- Provide a reliable electrical entry point into the system

This layer does not perform protection or switching.

## Protection Layer

The protection layer protects sensitive electronics and wiring against electrical faults.

Protection strategy follows a functional separation approach.

Primary protection mechanisms:
- Verpolungsschutz on control, logic and feedback lines
- Short-circuit protection via fuses in load paths
- Controlled and filtered supply voltages for logic and indicators
- Targeted transient suppression at defined system boundaries

The protection layer is designed to be effective without unnecessary complexity.

### Verpolungsschutz

Verpolungsschutz is applied primarily to:
- Control inputs
- Logic supply lines
- Feedback and indicator circuits

Load paths are protected by fuses and relay isolation and do not require dedicated polarity protection.

### Short-Circuit Protection

Short-circuit protection is implemented using fuses.

Characteristics:
- Each load path is fused
- Fuse ratings reflect defined continuous and peak current limits
- Protection is mechanical, predictable and field-serviceable

### Transient Suppression

Transient suppression addresses short-duration voltage spikes typical in vehicle electrical systems.

Implementation is selective and limited to:
- Control voltage inputs
- Logic supply boundaries
- Defined interface points

Transient suppression is not applied universally across all load paths.

## Power Distribution Layer

This layer distributes protected power internally.

Responsibilities:
- Supply control electronics
- Supply relay drivers
- Isolate sensitive electronics from load disturbances

Voltage regulation and filtering may occur here as required.

## Control Layer

The control layer contains the logic that determines relay behaviour.

Characteristics:
- Low-power electronics
- Deterministic operation
- Electrically separated from load currents

Responsibilities:
- Interpret external control inputs
- Drive relay control signals
- Maintain stable relay states

No load current flows through this layer.

## Relay Layer

The relay layer performs physical switching of vehicle loads.

Characteristics:
- Designed for defined current limits
- Suitable for DC load switching
- Optimised for mechanical longevity

Responsibilities:
- Connect and disconnect loads
- Maintain bistable or latching states
- Remain safe under fault conditions

Relay contacts are polarity-agnostic and protected by upstream fusing.

## Status and Interface Layer

This layer provides visibility and external interaction.

Typical elements:
- Status LEDs
- Panel interface connectors
- Diagnostic signals

Responsibilities:
- Indicate relay state
- Indicate fault conditions
- Provide simple, reliable feedback

This layer must remain intuitive and unambiguous.

## Optional Hardware Modules

The following hardware modules are optional and not part of the VRDS core:

- Current sensing modules
- Voltage monitoring modules
- External communication modules
- Remote control interfaces

Optional modules must not compromise core system stability.

## Mechanical Considerations

Hardware design must consider:
- Vibration resistance
- Thermal behaviour
- Service accessibility
- Automotive mounting constraints

Mechanical design is implementation-specific and documented separately.

## Hardware Scope Boundaries

VRDS hardware explicitly does not include:
- Vehicle-specific loads
- User interface logic
- Network infrastructure
- Automation or decision-making systems

These belong to external systems if required.

## Architectural Consistency

All hardware implementations must conform to:
- System Architecture document
- Defined electrical boundaries
- Safety and serviceability principles

Deviation from this overview must be explicitly documented.

