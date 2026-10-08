# FYRE-Assignments

This repository contains my work from the **"Sensing the World"** module of **ENGR 095 at Lehigh University, Fall 2026**.

Throughout the module, I worked with materials science, sensor fabrication, circuits, MicroPython programming, microcontrollers, sensor data collection, and embedded-system design. The repository also documents the development of our final **automatic floodgate prototype**.

## Final Project — Automatic Floodgate

![Automatic Floodgate Prototype](Project/images/floodgate-open.jpeg)

Our final project was a small-scale automatic floodgate designed to respond to unsafe moisture conditions.

The system uses a homemade **PEDOT:PSS humidity sensor** and a commercial **rain sensor**. If either sensor detects an unsafe condition, a stepper motor automatically moves the floodgate into the closed position.

The prototype also includes red and green status LEDs, a manual reset pushbutton, an Arduino Nano ESP32, a ULN2003 stepper motor driver, and a pulley/spool mechanism.

[View the Automatic Floodgate Project](Project/)

## Programming Activities

The [Programming Activities](Programming%20Activities/) folder contains the MicroPython programs and sensor-data activities completed during the module.

Activities include:

- Basic MicroPython programs
- LED control
- Security system prototype
- Arduino Nano ESP32 inputs and outputs
- Servo motor control
- Rain sensor ADC measurements
- Automated sensor data collection
- CSV data generation
- Sensor performance analysis

The folder contains a [README](Programming%20Activities/README.md) explaining what each program corresponds to.

The [Lecture 8](Programming%20Activities/Lecture%208/) folder contains the servo motor activity, rain sensor ADC data collection, CSV datasets, and sensor performance analysis.

## Reflections

The [Reflections](Reflections/) folder contains all three reflections completed during the Sensing the World module.

- [Reflection 1](Reflections/Reflection%201.pdf) — Materials science, fabrication, resistivity measurements, and PEDOT:PSS sensor fabrication
- [Reflection 2](Reflections/Reflection%202.pdf) — Programming, circuits, microcontrollers, sensors, and data collection
- [Reflection 3](Reflections/Reflection%203.pdf) — Final project development and overall module experience

## Project Files

The [Project](Project/) folder contains the complete development of the automatic floodgate prototype.

Key project materials include:

- [Development Code](Project/development/) — Component tests and intermediate versions
- [Final Code](Project/final/automatic_floodgate_final.py) — Final integrated MicroPython program
- [Project Images](Project/images/) — Photographs of the prototype, sensors, electronics, and mechanical system
- [Final Presentation](Project/presentation/FYRE%20Project%20Presentation.pdf) — Final project presentation slides
- [Project README](Project/README.md) — Detailed explanation of the design, operation, testing, and development process

## Repository Organization

```text
FYRE-Assignments/
├── Programming Activities/
│   ├── Lecture 8/
│   ├── program1.py
│   ├── program2.py
│   ├── program3.py
│   ├── program4.py
│   ├── program5.py
│   └── README.md
│
├── Reflections/
│   ├── Reflection 1.pdf
│   ├── Reflection 2.pdf
│   └── Reflection 3.pdf
│
├── Project/
│   ├── development/
│   ├── final/
│   ├── images/
│   ├── presentation/
│   └── README.md
│
└── README.md
```

This repository serves as a record of my work and engineering design process throughout the **Sensing the World** module.
