# Ultra-Low-Power IoT Environmental Monitor

This project documents an ESP32-based environmental monitoring node for rural or remote deployments. The system reads temperature, humidity, and particulate matter data, performs basic edge processing, and transmits environmental information over LoRa to a designated mobile number or displays it on a modern web interface.

---

# 🔗 Quick Links

| Resource | Link |
|----------|------|
| 🔌 Complete Circuit | [Circuit Designer](https://app.cirkitdesigner.com/project/72f4accd-b4bb-4687-a699-8c45e1bc3c0c) |
| 📦 Bill of Materials | [Notion BOM](https://viridian-path-34d.notion.site/Aakashvani-3adc78e01c3d80f9a7f2f4c04ff93067?source=copy_link) |
| 🔄 Firmware Flowchart | [Eraser.io Flowchart](https://app.eraser.io/workspace/saOYZ587aT2T2XnHdCFs?origin=share) |
| 🔋 Battery Life Analysis | [Notion Power Analysis](https://viridian-path-34d.notion.site/Battery-Life-Estimation-ESP32-LoRa-Sensor-Node-3aec78e01c3d80c3be53f0dbc6ac5a15?source=copy_link) |

---

# 📂 Project Structure

| Folder | Description |
|--------|-------------|
| 📁 [`hardware/`](hardware/) | BOM, component notes and pin mapping *(create later if needed)* |
| 📁 [`docs/architecture/`](docs/architecture/) | Firmware flowcharts and system architecture |
| 📁 [`docs/circuit/`](docs/circuit/) | Circuit diagrams, schematics and wiring |
| 📁 [`docs/power/`](docs/power/) | Power consumption and battery analysis |
| 📁 [`docs/datasheets/`](docs/datasheets/) | Datasheets of all components |
| 📁 [`firmware/`](firmware/) | ESP32 transmitter and receiver firmware |
| 📁 [`images/`](images/) | Prototype images and development journey |
| 📁 [`presentation/`](presentation/) | Poster and presentation slides |
| 📁 [`results/`](results/) | Experimental results and reports |

---

# ⚙️ How the System Works

1. Device wakes up from deep sleep.
2. Sensors are powered.
3. Temperature, humidity and dust readings are collected.
4. Edge processing classifies the readings.
5. Firmware checks predefined thresholds.
6. Sensor data is transmitted through LoRa.
7. Gateway receives the packet.
8. Data is stored in the backend/database.
9. Dashboard displays live readings.
10. Alerts are generated if thresholds are exceeded.
11. Device returns to deep sleep.

📄 **Firmware Flowchart**

- [`docs/architecture/firmware_flowchart.png`](docs/architecture/firmware_flowchart.png)

---

# 🔌 Hardware Summary

The prototype uses

- ESP32 DevKit V1
- DHT11 Temperature & Humidity Sensor
- GP2Y1014AU0F Dust Sensor
- SX1278 LoRa Module
- TP4056 Charging Module
- 18650 Li-ion Battery

### Circuit References

- [Complete Circuit](docs/circuit/05_Complete_Circuit.png)
- [Combined Wiring Diagram](docs/circuit/03_Dht11+PM2.5+Lora_Reciever+Lora_Transmitter.png)
- [Transmitter Circuit](docs/circuit/01_Dht11_Pm2.5.png)
- [Receiver Circuit](docs/circuit/02_Lora_reciever.png)
- [TP4056 Battery Circuit](docs/circuit/04_tp4056_42.png)
- [Circuit README](docs/circuit/Readme.md)
---

# 💻 Firmware

Firmware source files are located in the [`firmware/`](firmware/) directory.

| File | Purpose |
|------|---------|
| [`esp32_only_transmitter.cpp`](firmware/esp32_only_transmitter.cpp) | Reads sensors and transmits data |
| [`Esp32_only_reciever.cpp`](firmware/Esp32_only_reciever.cpp) | Receives LoRa packets and forwards data |

---

# 📈 Results

The following experiment outputs are available.

| File | Description |
|------|-------------|
| [`sample_sensor_data.csv`](results/sample_sensor_data.csv) | Sample collected readings |
| [`serial_logs.txt`](results/serial_logs.txt) | Serial monitor output |

---

# 📸 Prototype Images

| Image |
|-------|
| [`breadboard.jpg`](images/breadboard.jpg) |
| [`wiring.jpg`](images/wiring.jpg) |
| [`upclose.png`](images/upclose.png) |
| [`esp32_with_pm2.5.png`](images/esp32_with_pm2.5.png) |
| [`lora_with_esp32.png`](images/lora_with_esp32.png) |
| [`dht11_pm2.5.png`](images/dht11_pm2.5.png) |

---

# 🚀 Getting Started

1. Clone this repository.

2. Open the project in **VS Code**.

3. Open the [`firmware/`](firmware/) folder in Arduino IDE.

4. Refer to the circuit diagrams in [`docs/circuit/`](docs/circuit/).

5. Follow the firmware flowchart in [`docs/architecture/`](docs/architecture/).

6. Upload the transmitter and receiver firmware to their respective ESP32 boards.

---

# 📄 License

This project is released under the **MIT License**.

See the [`LICENSE`](LICENSE) file for details.