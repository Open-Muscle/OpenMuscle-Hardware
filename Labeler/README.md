# LASK5 - A Gloveless Smart Glove Controller

![LASK5 Demo](https://img.shields.io/badge/Open%20Source-Yes-brightgreen)
![ESP32-S3](https://img.shields.io/badge/MCU-ESP32--S3-blue)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

LASK5 is a compact, gloveless smart glove controller designed for robotics, machine learning, and human-computer interaction projects. Originally created to assist with labeling movement data for the [OpenMuscle](https://openmuscle.org) project, this controller is now a fully open-source interface capable of controlling robotic hands, LED sculptures, and more.

---

## 📽️ Watch the Demo

🎥 **YouTube Video:** [LASK5: The Gloveless Smart Glove](https://youtu.be/DJxaf0ww6us)

---

## 🔧 Features

- ESP32-S3 based (Wi-Fi + ESP-NOW enabled)
- 4-piston finger input with hall sensors
- Thumb joystick
- 128x32 OLED display for menus and feedback
- 4 SMD buttons for UI control
- Modular headers for add-ons (gyroscope, additional sensors)
- Written in MicroPython
- 3D-printable enclosure

---

## 📁 Repository Structure

This repo is split into two main components:

### 🛠️ Hardware
📂 [OpenMuscle-Hardware → Labeler](https://github.com/Open-Muscle/OpenMuscle-Hardware/tree/main/Labeler)  
Includes schematics, board files (KiCad), and 3D printable STL files.

### 💾 Software
📂 [OpenMuscle-Software → embedded/Labeler](https://github.com/Open-Muscle/OpenMuscle-Software/tree/main/embedded/Labeler)  
Includes MicroPython source code and menu system.

---

## 🧠 Use Cases

- Robotics hand control (e.g., HiWonder robotic hand)
- LED and art installations
- Machine learning data labeling
- Experimental HCI and VR interface development

---

## 🚀 Getting Started

1. Clone the hardware and software repos.
2. Flash the ESP32-S3 with the provided MicroPython firmware.
3. Assemble the hardware using the STL and PCB files.
4. Power it up and start controlling your devices wirelessly via ESP-NOW!

---

## 🤝 Contribute

Got improvements, ideas, or bug fixes? PRs are welcome!  
If you're using this for your own project, we'd love to see it—tag [@OpenMuscle](https://openmuscle.org)!

---

## 📜 License

This project is open-source and licensed under the MIT License.

---

Made with 💡 by [TURFPTAx](https://github.com/turfptax) for the [OpenMuscle](https://openmuscle.org) initiative.
