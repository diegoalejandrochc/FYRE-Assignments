# Automatic Floodgate Prototype

## Team Members
- Diego Chuquillanqui
- Diane Ngo
- Artur Kis

## Project Overview

This project is a small-scale automatic floodgate prototype designed to detect unsafe moisture conditions and automatically close a barrier to help protect an area from flooding.

The system uses two different sensors:

- A **homemade PEDOT:PSS humidity sensor** fabricated during the Sensing the World module
- A **commercial rain sensor** for detecting direct contact with water

When either sensor detects an unsafe condition, a stepper motor moves the floodgate into the closed position. A red LED indicates a detected moisture condition, while a green LED indicates safe conditions. A pushbutton allows the user to manually reopen the gate after the rain sensor no longer detects water.

## Humanitarian Purpose

Flooding can damage homes, shelters, infrastructure, and important supplies. The goal of this prototype was to demonstrate how sensors and automated systems could be used to respond to rising moisture or water without requiring a person to manually close a barrier.

The PEDOT:PSS sensor provides an early response to increased humidity, while the rain sensor provides confirmation of direct water exposure.

## Main Components

- Arduino-compatible microcontroller running MicroPython
- Homemade PEDOT:PSS humidity sensor
- Commercial rain/moisture sensor
- 28BYJ-48 stepper motor
- ULN2003 stepper motor driver
- Red LED
- Green LED
- Pushbutton
- Breadboard and jumper wires
- Resistors
- Sliding floodgate prototype
- String and spool mechanism

## System Operation

The final system follows this sequence:

1. The system starts with the gate open and the green LED on.
2. The PEDOT:PSS sensor is calibrated to establish a dry baseline.
3. Both the PEDOT:PSS sensor and rain sensor are continuously monitored.
4. If either sensor detects an unsafe moisture condition:
   - The green LED turns off.
   - The red LED turns on.
   - The stepper motor closes the floodgate.
5. After the PEDOT:PSS sensor triggers, it is temporarily disarmed because the material can take a relatively long time to return to its original dry value.
6. When the rain sensor is dry, the user can press the reset button to reopen the gate.
7. The PEDOT:PSS sensor automatically becomes active again once its reading returns sufficiently close to its dry baseline.

## Code Development

The project was developed by testing individual components before combining them into the final system.

### `development/01_stepper_motor_test.py`

Tests the 28BYJ-48 stepper motor by rotating it in both directions. This was used to determine the correct motor pins, stepping sequence, speed, and direction.

### `development/02_rain_sensor_test.py`

Reads and displays the ADC value from the commercial rain sensor. This allowed us to compare dry and wet readings and select an appropriate threshold for water detection.

### `development/03_pedot_sensor_response_test.py`

Tests the homemade PEDOT:PSS sensor. The program first determines a dry baseline and then displays:

- Current ADC reading
- Difference from baseline
- Percentage change from baseline

This helped characterize how the fabricated sensor responded to humidity.

### `development/04_initial_floodgate_control.py`

The first major integrated version of the project. It combines:

- PEDOT:PSS sensor
- Rain sensor
- Stepper motor
- Red and green LEDs
- Reset pushbutton

Either sensor can trigger the gate to close.

### `development/05_pedot_delta_threshold_test.py`

Tests an alternative method for detecting changes in the PEDOT:PSS sensor. Instead of triggering from percentage change, this version uses the absolute difference between the current ADC value and its dry baseline.

This experiment helped compare different approaches for determining when the homemade sensor should activate the floodgate.

### `final/automatic_floodgate_final.py`

The final integrated program used for the completed prototype.

The final version uses percentage change from the PEDOT:PSS dry baseline and includes logic that temporarily disarms the PEDOT:PSS sensor after activation because the sensor was observed to recover slowly after exposure to high humidity.

### Mechanical System

The floodgate moves vertically along guide rails. String attached near both sides of the gate joins into a central lifting line connected to a spool driven by the stepper motor. This helps keep the gate approximately level while it moves.

## Testing

The prototype was tested under several conditions:

- Both sensors dry
- Rain sensor exposed to water
- PEDOT:PSS sensor exposed to increased humidity
- Reset button pressed while water was still detected
- Reset button pressed after the rain sensor returned to dry conditions
- Multiple gate opening and closing cycles

A successful test required the correct LED indication and the expected gate response for each condition.
