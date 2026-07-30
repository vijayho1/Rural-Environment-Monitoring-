# Ultra-Low-Power IoT Environmental Monitor

This repository contains the scaffold for an ultra-low-power environmental monitoring node for rural deployments. The project is organized around documentation, firmware, hardware references, simulation assets, images, and results.

## What’s Included

The current repository structure includes:

- `docs/architecture/` for system, firmware, and communication diagrams
- `docs/circuit/` for the schematic and wiring assets
- `docs/power/` for battery and current-consumption analysis
- `docs/datasheets/` for component datasheets
- `hardware/` for the BOM, pin mapping, and component list
- `firmware/` for the PlatformIO project and source files
- `simulations/` for Proteus, Wokwi, and simulation outputs
- `images/` for prototype and demo media
- `results/` for logs, CSV data, and reports
- `presentation/` for slides and poster materials

## Flowchart

The device flowchart should live in `docs/architecture/firmware_flowchart.png`. It documents the wake-up, sensor read, edge processing, threshold check, MQTT/LoRa transmission, backend handoff, and deep-sleep cycle.

## Project Goal

The prototype is intended to measure environmental conditions such as temperature, humidity, and particulate matter while keeping power consumption low through sleep modes and short communication bursts.

## Hardware Reference

The repository is set up to document an ESP32-based prototype with sensors and a LoRa radio module. See the hardware notes and component list in `hardware/` and the circuit references in `docs/circuit/`.

## Firmware

Firmware sources live under `firmware/src/`, with `firmware/platformio.ini` providing the PlatformIO configuration.

## Getting Started

1. Clone the repository.
2. Open the `firmware/` folder in PlatformIO.
3. Review the documents in `docs/` and the wiring notes in `hardware/pin_connections.md`.

## License

This project is released under the MIT License.