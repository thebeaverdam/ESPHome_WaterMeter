# 📟 ESPHome Water Meter 

[![ESPHome Version](https://img.shields.io/badge/ESPHome-2026.1.0+-00b0ff.svg?logo=esphome&logoColor=white)](https://esphome.io/)
[![Hardware](https://img.shields.io/badge/Hardware-ESP32-blue.svg)](https://www.espressif.com/en/products/socs/esp32)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains the ESPHome configuration for the **ESPHome Water Meter** using the [ESP32 MultiBoard](https://github.com/thebeaverdam/ESP32_MultiBoard) and the FS300A flow meter. This hardware is designed to integrate natively with Home Assistant, providing local control and real-time telemetry.

---

## 🛠️ Prerequisites

Before you begin, ensure you have:
* [ESPHome](https://esphome.io/guides/installing_esphome.html) installed (CLI or Dashboard).
* An ESP32 MultiBoard.
* A FS300A flow meter.
* Cloned this repository to your local machine.

## 🚀 Quick Start

1.  **Configure your secrets:**
    Create a file named `secrets.yaml` in the root directory (if it doesn't exist) and add your credentials:
    ```yaml
    wifi_ssid: "Your_WiFi_SSID"
    wifi_password: "Your_WiFi_Password"
    api_encryption_key: "Your_Generated_Key"
    ```

2.  **Compile and Flash:**
    Connect your ESP32 via USB and run:
    ```bash
    esphome run water_meter.yaml
    ```

---


## 🔌 Connections with FS300A

The FS300A works at 5V, so we need to use the I2C 5V connector from the MultiBoard to take advantage of the level shifter that comes integrated and protect the board.

| FS300A | MultiBoard | Function |
| :--- | :--- | :--- |
| **Red** | +5V | VCC |
| **Black** | GND | Ground |
| **Yellow** | GPIO21 | Pulse counter |


---

## 📈 Home Assistant Entities

Once flashed, the device will automatically expose:
* **Binary Sensors:** Connectivity status and input buttons.
* **Sensors:** Voltage readings, temperature, and RSSI signal strength.
* **Switches:** Manual control for integrated relays.

## 🤝 Contributions & Issues

If you find a bug or have an improvement for this board:
1. Check the [existing Issues](#).
2. Use the **Bug Report** template to report hardware or firmware faults.

---

> **⚠️ Safety Note:** Always ensure that mains power (AC) is disconnected before handling wiring or connecting the ESP32 to your computer for programming.
