# Ultra-Low-Power IoT Environmental Monitor

This project documents an ESP32-based environmental monitoring node for rural or remote deployments. The system reads temperature, humidity, and particulate-matter data, performs basic edge processing, and transmits events or summaries over LoRa or MQTT while minimizing power use.

## Quick Links

- [BOM](hardware/bom.xlsx)
- [Component List](hardware/component_list.md)
- [Pin Connections](hardware/pin_connections.md)
- [Circuit Schematic](docs/circuit/schematic.pdf)
- [Wiring Diagram](docs/circuit/wiring_diagram.png)
- [System Architecture](docs/architecture/system_architecture.png)
- [Firmware Flowchart](docs/architecture/firmware_flowchart.png)
- [Communication Flow](docs/architecture/communication_flow.png)
- [Power Budget](docs/power/power_budget.pdf)
- [Battery Life Calculation](docs/power/battery_life_calculation.xlsx)
- [Current Consumption Table](docs/power/current_consumption_table.pdf)

## Project Overview

The repository is organized so the top-level README acts as the entry point, while the supporting files live in focused folders:

- `hardware/` contains the BOM, component notes, and pin mapping
- `docs/architecture/` contains the flowcharts and system diagrams
- `docs/circuit/` contains the schematic and wiring references
- `docs/power/` contains power analysis and battery-life documents
- `docs/datasheets/` contains component datasheets
- `firmware/` contains the PlatformIO project and source code
- `simulations/` contains simulation projects and outputs
- `images/` contains prototype and demo media
- `results/` contains logs, captured data, and reports
- `presentation/` contains slides and poster files

## How The System Works

1. The device wakes from deep sleep.
2. Sensors are powered and read.
3. The firmware performs edge processing and packages the data.
4. The threshold check decides whether to send normal data or an alert.
5. Data is transmitted via MQTT or LoRa.
6. The backend can store the data in a database and surface it on a dashboard.
7. The device returns to deep sleep to preserve battery life.

The flowchart for this behavior is stored in [docs/architecture/firmware_flowchart.png](docs/architecture/firmware_flowchart.png).

## Hardware Summary

The prototype is documented around an ESP32, DHT11 for temperature and humidity, GP2Y1014 for particulate sensing, SX1278 for LoRa communication, and TP4056 for battery charging. The BOM and component references are kept in the `hardware/` folder.

## Firmware

Firmware sources live under `firmware/src/`, with `firmware/platformio.ini` providing the PlatformIO configuration. The folder is structured so each concern can be maintained separately:

- `main.cpp` for the application entry point
- `sensors.cpp` for sensor handling
- `lora.cpp` for LoRa communication
- `mqtt.cpp` for MQTT publishing
- `power.cpp` for power management
- `battery.cpp` for battery monitoring

## Getting Started

1. Open the repository in VS Code.
2. Review the BOM and hardware notes at the top of this README.
3. Open `firmware/` in PlatformIO to work on the embedded code.
4. Use the diagrams in `docs/architecture/` and `docs/circuit/` as the reference for wiring and data flow.

## License

This project is released under the MIT License.