# OpenMuscle FlexGrid (v2.0)

**OpenMuscle FlexGrid** is a modular wearable sensor grid with 60 analog pressure sensors arranged in a 15x4 matrix. It is the second-generation wearable in the OpenMuscle series and serves as the core interface for capturing muscle movement in prosthetic and robotics applications.

📍 Project Page: [openmuscle.org](https://openmuscle.org)

---

## 📐 System Overview

- **Sensor Grid**: 15 columns × 4 rows of Velostat pads
- **Flex PCB**: Thin and wearable with 21-pin output header
- **Rigid PCB**: ESP32-S3, haptic feedback, USB-C charging, multiplexer, OLED, IMU

---

## 🔧 Key Features

| Feature               | Description                                  |
|-----------------------|----------------------------------------------|
| MCU                   | ESP32-S3 (USB + BLE + ADC1)                  |
| Sensor Matrix         | 15×4 Velostat with voltage divider setup     |
| Multiplexer           | 74HC4067 (16-channel, 15 used)               |
| Row Reads             | 4x analog inputs on ADC1                     |
| OLED Display          | SSD1306 128x32 over I2C                      |
| IMU                   | ICM-42688-P 6-DOF sensor (optional)          |
| Haptic Feedback       | Motor driven by IRLML2060 MOSFET             |
| Power Management      | MAX16054 soft latch, TPS7A0333 LDO, LTC4054 LiPo charger |

---

## 🗂️ File Structure

```graphql
FlexGrid/
├── KiCad/ # Schematic and layout files
├── Images/ # Renders and photos
├── BOM.xlsx # Bill of materials (optional)
└── README.md # You're reading it!
```

# 📁 Repository Layout

```graphql
OpenMuscle-FlexGrid/
├── firmware/           # MicroPython or C code for scanning and I/O
├── hardware/
│   ├── KiCad/          # Schematics, PCB, BOMs
│   └── Images/         # Renders and assembly diagrams
├── docs/
│   └── Datasheets/     # ICs and reference materials
└── README.md
```
---

## 🛠️ How It Works

The 74HC4067 connects one column at a time to 3.3V. The Velostat pads act as pressure-sensitive resistors connected to row lines, which are pulled down with 10kΩ resistors and read via analog inputs.

A software loop cycles through all 15 columns, sampling all 4 rows each time for 60 total readings per frame.

---

## 🧪 Status

- ✅ Schematic Complete
- ✅ PCB Fabricated & Assembled
- 🛠️ Firmware In Progress
- 🧠 ML Integration Pipeline Active

---

## 🔗 Related Projects

- [SensorBracelet (OM-12)](../SensorBracelet/)
- [Labeler (LASK5)](../Labeler/)

---

## 📝 License

- **Hardware**: CERN-OHL-P v2
- **Software/Firmware**: MIT

---

## 🤝 Get Involved

We welcome contributions, feedback, and forks. This project is part of a broader mission to open-source biomechanical sensing tools for all.

Visit **[openmuscle.org](https://openmuscle.org)** or join our Discord (link coming soon).