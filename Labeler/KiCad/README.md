# LASK5 – OpenMuscle Sensor Device

**Version:** `V3 (Proposed)`  
**Target Microcontroller:** ESP32-S3-WROOM-1-N16R8  
**Project:** OpenMuscle – Biomechanical Sensing for Prosthetics & Robotics  
**Repository:** https://github.com/turfptax/OpenMuscle-Hardware

---

## 📐 Overview

The LASK5 board is a wearable sensor platform for real-time finger movement detection, developed as part of the OpenMuscle project. It integrates Hall effect sensors, a joystick, buttons, a low-power screen, and wireless communication via ESP32-S3.

Version 3 introduces multiple improvements in usability, sensing accuracy, and expandability.

---

## 🚀 New in V3 (Proposed)

| Feature | Description |
|--------|-------------|
| 🔌 USB Detection | VBUS now routed to a GPIO via voltage divider, allowing firmware to detect USB connection. |
| 🔋 USB Boot Without Battery | Modified power logic enables powering on via USB without a battery installed, using diode-based OR logic to control LDO enable line. |
| 📉 Improved ADC Accuracy | Voltage divider for battery monitoring updated to 10k/10k, reducing impedance for better ESP32-S3 ADC readings. |
| 🧭 6-Axis Gyroscope Support | IMU footprint and I²C headers added for optional motion sensing (MPU6050 or ICM-42688). |
| ⚙️ Charging Status Feedback | CHRG pin from LTC4054 connected to GPIO for in-software charge status indication. |


---
## 📦 Block Diagram
```
Battery ─────┐
├─> Charger (LTC4054) ──> Power Rail (+3.3V)
USB ───────┐ │
│ └─> VBUS GPIO (USB Detect)
└───> LDO EN Logic ──> TPS7A0333 LDO ──> ESP32-S3
```
---

## 📊 Hardware Specifications

- **MCU:** ESP32-S3-WROOM-1-N16R8 (dual-core, WiFi/BLE, 16MB flash, 8MB PSRAM)
- **Power:**
  - USB-C with VBUS detection
  - 1-cell LiPo battery
  - TPS7A0333 LDO (3.3V, low quiescent current)
  - MAX16054 latched soft-power button
- **Sensing:**
  - 4x Hall effect analog sensors
  - 1x Joystick (XY + button)
  - 0.96” SSD1306 OLED display (I²C)
  - Optional 6-axis gyro (MPU6050, ICM-42688, etc.)
- **Inputs:**
  - `menu` and `select` tactile buttons
  - Power button
- **Charging:**
  - LTC4054ES5-4.2 Li-Ion charger
  - CHRG status indicator routed to GPIO
- **Communication:**
  - ESP-NOW, WiFi, BLE
- **Headers:**
  - I²C breakout
  - SPI/debug/jumper expansion

---

## 🛠️ Setup & Firmware

- Flash via USB-C using esptool or Micropython.
- Default I²C pins: `SDA=GPIO15`, `SCL=GPIO16`
- ADC battery read: `GPIO4` (adjusted via voltage divider)
- USB detect pin: `GPIO10` *(example)*
- CHRG detect pin: `GPIO11` *(example)*

---

## 📚 Resources

- [OpenMuscle.org](https://openmuscle.org)
- [KiCad Schematic Viewer](https://kicad.org)
- [ESP32-S3 Datasheet](https://www.espressif.com/sites/default/files/documentation/esp32-s3_datashee---

## 🙌 Contributing

Interested in testing or improving the hardware? Submit a pull request or open an issue with your suggestions.

---

## 🧪 Version History

| Version | Date | Notes |
|---------|------|-------|
| V1 | 2024-02 | Initial prototype, using ESP32-S3 Dev-Kit |
| V2 | 2024-05 | 4-Layer PCB with 4x1 Hall sensors & Joystick |
| V3 | 25-XX | USB logic, gyro, and ADC improvements |

---