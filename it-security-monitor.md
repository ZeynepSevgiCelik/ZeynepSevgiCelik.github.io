---
title: IT Security Monitor
layout: default
---

# IT Security Monitor – Multi-Sensor Environmental Monitoring System

An STM32-based environmental monitoring system designed to collect sensor data and transmit it to a server database over Wi-Fi.

[← Back to Projects](projects.html)

---

## Overview

This project integrates multiple environmental sensors into a custom embedded monitoring platform. The system collects gas, light, motion, temperature, humidity, and sound-presence data, then transmits the readings to a server endpoint over Wi-Fi.

**Microcontroller:** STM32

**Programming Language:** C

**My Role:** Circuit design, custom PCB design, hardware development, embedded firmware, communication configuration, and server integration.

## Key Features

- **Multi-Sensor Monitoring:** Collects data from five sensors, producing six measurement or status values.
- **Gas Detection:** Uses an MQ-135 sensor for environmental gas detection.
- **Light Detection:** Uses an LDR to detect ambient light changes.
- **Motion Detection:** Uses a PIR sensor module for movement detection.
- **Temperature and Humidity:** Measures temperature and relative humidity using an AHT15 sensor.
- **Sound Presence Detection:** Uses a microphone circuit to report sound presence as a binary value.
- **Device Configuration:** Supports board-address configuration over RS485 and configurable Wi-Fi credentials.
- **Wi-Fi Data Transmission:** Sends sensor data to a server endpoint for database storage.

## Hardware Design & PCB

I designed the electronic circuit and custom PCB and developed the hardware platform around the STM32 microcontroller.

The board includes the sensor interfaces, communication circuitry, and USB Type-C power input.

**Power Input:** 5–5.2 V DC through USB Type-C.

## Integrated Sensors

### MQ-135 Gas Sensor

The MQ-135 is used for general environmental gas detection. It provides a sensor response related to the presence of detectable gases.

### LDR Light Sensor

The LDR detects changes in ambient light intensity.

### PIR Motion Sensor

The PIR module uses circuitry based on the BISS0001 IC to detect movement through changes in infrared radiation. Its Fresnel lens and installation position are important for reliable operation.

### AHT15 Temperature and Humidity Sensor

The AHT15 measures:
- Temperature in °C.
- Relative humidity in %RH.

The sensor was selected based on component availability.

### Microphone Sound Detection

The microphone circuit detects sound presence using binary logic:
- **1:** Sound detected.
- **0:** Sound not detected.

This is a sound-presence status, not a continuous sound-level measurement.

## Firmware Development

I developed the embedded C firmware for sensor acquisition, communication, configuration, and data transmission.

The firmware gathers six values from five sensors: gas, light, motion, temperature, humidity, and sound-presence status.

## Communication & Data Flow

### UART and RS485

UART is used for serial communication, while RS485 supports communication and board-address configuration at 9600 baud.

### Wi-Fi

The Wi-Fi network name and password can be configured. The device sends the collected sensor data to a provided server endpoint, where the data is stored in a database.

After a data record is sent, the system waits approximately 60 seconds before beginning the next measurement cycle. The observed interval between database records is approximately 80 seconds.

## My Contributions

- Electronic circuit and schematic design.
- Custom PCB design and hardware development.
- STM32 embedded firmware development in C.
- Integration of five sensors.
- UART and RS485 communication implementation.
- Board-address and Wi-Fi configuration.
- Wi-Fi data transmission and server integration.
- Hardware testing and debugging.

## Engineering Scope

This project demonstrates practical experience in embedded systems, sensor integration, custom PCB development, serial communication, firmware engineering, and server-connected environmental monitoring.

## Hardware Images & Documentation

The project thumbnail is available on the Projects page. Additional hardware images and documentation may be added where sharing is permitted.

*Detailed schematics, firmware source code, server credentials, and other implementation materials are not included in this overview.*
