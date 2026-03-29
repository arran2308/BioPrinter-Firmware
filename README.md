# BioPrinter Firmware Configuration

Klipper-based firmware configuration for a custom low-cost biomedical extrusion 3D printer (“BioPrinter”).

This repository contains the machine configuration files used to run the BioPrinter hardware platform. It is primarily a **firmware configuration repository**, rather than a source-code firmware fork, and is intended to document the current machine setup, UI customisation, macros, and control logic.

## Overview

The BioPrinter is a custom extrusion-based biomedical 3D printer platform developed around low-cost, accessible hardware. This configuration stack is built on:

- **Klipper**
- **Moonraker**
- **KlipperScreen**
- **BigTreeTech Octopus Pro v1.1**
- **Raspberry Pi 5**

The current configuration supports motion control, chamber device switching, custom UI elements, syringe jogging, probe-based Z homing, and safety-oriented interlocks such as UV shutoff on door-open events.

## Repository purpose

This repository is intended to:

- document the active machine configuration
- provide a reproducible firmware-config baseline
- support development and testing of the BioPrinter platform
- track major configuration revisions over time

## Included files

- `printer.cfg` — primary Klipper machine configuration
- `KlipperScreen.conf` — custom touchscreen UI layout and controls
- additional config files may be added as the system develops

## Key features

### Motion system
- CoreXY kinematics
- TMC2209 stepper drivers
- sensorless X/Y homing
- probe-based Z homing
- bed mesh support

### User interface
- custom **BioPrinter** KlipperScreen menu
- syringe jog controls
- power/device access from the touchscreen
- status display integration

### Chamber controls
- HEPA filter
- chamber heater
- chamber light
- UV light
- rear fan

### Safety and workflow
- door interlock logic for UV shutdown
- machine utility macros
- commissioning/test macros
- print-state wrappers for pause, resume, and cancel

## Status

This repository is currently an **early development configuration release**.

It should not be treated as a universal or production-ready firmware package. Some functions are still being refined, particularly around toolhead heater handling and machine-specific workflow logic.

## Hardware context

Current configuration is written for:
- BigTreeTech Octopus Pro v1.1
- STM32H723 MCU
- Raspberry Pi host system
- custom BioPrinter CoreXY motion platform

## Disclaimer

This repository is specific to a custom machine. Anyone reusing these files should verify:
- pin assignments
- motor directions
- endstop/probe wiring
- heater and sensor definitions
- interlock behaviour
- travel limits and homing logic

Use at your own risk.

## Author
Arran Arthur
Developed for the BioPrinter project.
