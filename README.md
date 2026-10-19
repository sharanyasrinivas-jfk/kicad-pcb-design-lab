<div align="center">

# 🔌 KiCad PCB Design Lab

**Nine lessons. Nine complete boards. From a through-hole ATmega328P breakout to 4-layer USB-C, WiFi, and motor-driver designs, all in KiCad 9.**

![KiCad](https://img.shields.io/badge/KiCad-9-314CB0?logo=kicad&logoColor=white)
![Lessons](https://img.shields.io/badge/lessons-9-brightgreen)
![Boards](https://img.shields.io/badge/boards-9-orange)
![License](https://img.shields.io/badge/license-MIT-blue)
![Fork](https://img.shields.io/badge/fork-SiliconWit%2Fpcb--design--kicad-lightgrey)

[Overview](#-overview) · [Lessons](#-lessons) · [Skill progression](#-skill-progression) · [Repository layout](#-repository-layout) · [Getting started](#-getting-started) · [Credits](#-credits-and-license)

</div>

---

## 📖 Overview

A hands-on, build-it-yourself course on designing and manufacturing real printed circuit boards with **KiCad 9**. Each lesson walks through one complete board end to end:

1. **The board:** what it is, why it is useful, and the design choices behind it
2. **Schematic capture:** component selection, wiring, power distribution, ERC
3. **PCB layout:** placement, routing, copper pours, design rules, DRC
4. **Manufacturing output:** Gerbers, drill files, BOM, and the fabrication method for that lesson
5. **Build and test:** assembly notes, first power-on checklist, and minimal firmware to prove the board works

Fabrication methods covered: **home etching**, **CNC milling**, and **professional fab houses (JLCPCB)**.

## 🧪 Lessons

| # | Lesson | Board | Layers | Fabrication | Firmware check |
|:-:|--------|-------|:------:|-------------|----------------|
| 1 | [ATmega328P Breakout (Through-Hole)](atmega328p-breakout-board-through-hole.mdx) | ATmega328P, ISP header, crystal, power LED | 2 | Home etching, CNC, or fab house | Blink LED over ISP |
| 2 | [ATmega328P Sensor Shield (SMD)](atmega328p-sensor-shield-smd-components.mdx) | ATmega328P TQFP-32, I2C temp/humidity, SPI light sensor | 2 (double-sided) | CNC milling | Read sensors |
| 3 | [STM32 USB Development Board](stm32-usb-development-board.mdx) | STM32F103C8T6, USB, SWD, dual crystals | 2 | JLCPCB (first fab order) | USB CDC serial |
| 4 | [STM32 USB-C Four-Layer Board](stm32-usb-c-four-layer-pcb.mdx) | STM32F411CEU6, USB-C, LDO | 4 | Fab house | USB CDC virtual COM port |
| 5 | [ESP32 WiFi/Bluetooth DevKit](esp32-wifi-bluetooth-devkit.mdx) | ESP32-WROOM-32, CP2102N USB-UART, auto-reset | 2 | Fab house | WiFi scan |
| 6 | [ESP32 Battery IoT Sensor Node](esp32-battery-iot-sensor-node.mdx) | ESP32-C3, TP4056 charger, solar input, BME280 | 2 | Fab house | Deep-sleep sensor reading |
| 7 | [RP2040 USB-C Development Board](rp2040-usb-c-development-board.mdx) | RP2040 (QFN-56), QSPI flash, PIO headers, RGB LED | 4 | Fab house | USB blink with UF2 |
| 8 | [Motor Driver and Sensor Integration](motor-driver-sensor-integration-board.mdx) | DRV8833 H-bridge, MPU6050 IMU, current sensing | 2 | Fab house | Motor control with IMU feedback |
| 9 | [Code-Based PCB Design](code-based-pcb-design-kicad-scripting.mdx) | Lesson 1 board rebuilt with Python and SKiDL | Any | Scripted output | None |

Start with [`index.mdx`](index.mdx) for the course overview. Schematic PDFs for lessons 1 to 8 are in [`schematics/`](schematics/).

## 📈 Skill progression

| Skill | Lessons 1-2 | Lessons 3-4 | Lessons 5-6 | Lessons 7-8 | Lesson 9 |
|-------|-------------|-------------|-------------|-------------|----------|
| **Components** | Through-hole, basic SMD | Fine-pitch SMD, USB | RF modules, battery ICs | QFN, motor drivers | Programmatic |
| **Routing** | Manual, wide traces | Differential pairs intro | RF keepout, impedance | High-speed, power | Automated |
| **Manufacturing** | Etching, CNC mill | Fab house (JLCPCB) | Fab house | Fab house | Scripted output |

## 🎯 Topics covered

- Schematic capture, ERC, and DRC workflow in KiCad 9
- Through-hole to fine-pitch SMD and QFN footprint selection
- 4-layer stackups: power and ground planes, via stitching, impedance-aware USB routing
- RF-aware layout: antenna keepout zones and ground-plane continuity
- Low-power design: Li-ion charging, solar input, deep-sleep current optimization
- Mixed-signal layout: motor power versus sensitive sensor signals, thermal management, protection circuits
- Manufacturing outputs: Gerbers, drill files, BOM, pick-and-place
- Code-driven design with the KiCad Python API and SKiDL

## 🗂️ Repository layout

```
kicad-pcb-design-lab/
├── index.mdx                                  # Course overview and lesson index
├── atmega328p-breakout-board-through-hole.mdx # Lesson 1
├── atmega328p-sensor-shield-smd-components.mdx # Lesson 2
├── stm32-usb-development-board.mdx            # Lesson 3
├── stm32-usb-c-four-layer-pcb.mdx             # Lesson 4
├── esp32-wifi-bluetooth-devkit.mdx            # Lesson 5
├── esp32-battery-iot-sensor-node.mdx          # Lesson 6
├── rp2040-usb-c-development-board.mdx         # Lesson 7
├── motor-driver-sensor-integration-board.mdx  # Lesson 8
├── code-based-pcb-design-kicad-scripting.mdx  # Lesson 9
├── schematics/                                # Schematic PDFs for lessons 1-8
└── README.md
```

## 🚀 Getting started

1. **Install KiCad 9** from [kicad.org/download](https://www.kicad.org/download/) (Linux, macOS, Windows).
2. **Read the lessons in order.** Each one builds on patterns from the previous lessons.
3. **Open the `.mdx` files** in any editor or Markdown viewer. They are written for the Astro/Starlight site engine, so components such as `<Card>` or `<Steps>` show as plain tags in a basic viewer.
4. **Compare against the schematic PDFs** in `schematics/` as you build.
5. **Build the boards.** Etch or mill Lesson 1 at home, or order Lesson 3 from JLCPCB.

**Prerequisites:** basic electronics (Ohm's law, reading a simple schematic). No prior KiCad experience needed. Soldering and Arduino basics help but are optional.

## 🙌 Credits and license

- **Maintained by:** [Sharanya S (Shine)](https://github.com/sharanyasrinivas-jfk), fork maintainer
- **Original course:** [SiliconWit/pcb-design-kicad](https://github.com/SiliconWit/pcb-design-kicad) by SiliconWit and its contributors (Sam Macharia, Julius Righa)
- **Published course:** [siliconwit.com/education/pcb-design-kicad](https://siliconwit.com/education/pcb-design-kicad/)

Course content is released under the **MIT License**. See the upstream repository for the license text, and keep the original copyright notice when redistributing.
