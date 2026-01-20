# Vehicle Relay Distribution System (VRDS)

## What is VRDS?

The Vehicle Relay Distribution System is a modular relay based switching and distribution system for 12 V DC electrical systems in campervans and similar vehicles.

VRDS Phase 1 is explicitly designed as a **bistable relay system**.

It solves a common problem in vehicle builds:
Small switches and buttons are not suitable for directly switching DC loads over long periods of time.

VRDS separates these concerns clearly:

- user input and control
- electrical load switching

Loads are switched by relays.
Buttons and control wiring only carry low power signals.

---

## Core design principle: bistable relays

VRDS Phase 1 is built primarily around **bistable relays**.

A bistable relay changes its state using a short control pulse and then mechanically remains in that state without consuming any further power.

### Properties of bistable relays

- no holding current required
- no continuous coil power
- minimal heat generation
- stable state even during power loss
- energy efficient by design

This makes bistable relays ideal for vehicle applications.

---

## Monostable relays explained

A monostable relay behaves differently:

- it requires continuous coil power to stay active
- when power is removed, it returns to its default state
- it consumes energy as long as it is switched on
- it generates continuous heat

Monostable relays are common, but they are **not the primary target** of VRDS Phase 1.
They are treated as exceptions or as part of Phase 2 for high power applications.

---

## Why VRDS uses push buttons instead of switches

Because VRDS Phase 1 uses bistable relays, it is designed to be operated with **momentary push buttons**, not latching switches.

Important consequences:

- the button position does not represent the load state
- the relay stores the state internally
- the actual load state is always indicated by LEDs
- no mismatch between switch position and load state

Push buttons are therefore the natural and preferred control element.
Latching switches are not required.

---

## Control flow overview

The functional flow in VRDS Phase 1 is always the same:

1. A push button is pressed
2. A short control pulse is generated
3. The bistable relay toggles its state
4. The load is switched on or off
5. The status LED updates to reflect the new state

The button itself never carries load current.
The LED always represents the real relay state, not the button state.

---

## Who VRDS is for

VRDS is intended for:

- campervan builders
- technically interested makers
- workshops focusing on clean vehicle electrics

It is suitable for non professionals as long as sufficient electrical knowledge is present or installation is performed by a qualified person.

---

## What VRDS is not

VRDS is not:

- a complete vehicle electrical system
- a smart home platform
- a bus system
- a software based controller
- a certified safety device

VRDS does not guarantee safety.
It provides a transparent and structured switching system.

---

## Safety and responsibility

Designing and installing a 12 V DC system is an electrical engineering task.

Incorrect planning or installation may cause damage or fire.

Responsibility for sizing, wiring and installation lies entirely with the user.

---

## Repository structure

- `concept.md`
  Complete technical concept and requirements for Phase 1

---

## Status

Phase 1 is complete and frozen.

