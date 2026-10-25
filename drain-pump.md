---
title: Drain Pump – Programmable Pump Control System
layout: default
---

# Drain Pump – Programmable Pump Control System

An STM32-based programmable pump control system featuring independent weekday and weekend schedules, Wi-Fi mobile application control, and reliable configuration retention during power loss.

[← Back to Projects](projects.html)

---

## Overview

This project involved the design and development of a programmable drain pump control system for commercial dishwashing environments. It allows users to configure operating days and times separately for weekdays and weekends, with control and configuration available through a mobile application.

A key engineering challenge was preserving the device's scheduling data during sudden power loss.

**Microcontroller:** STM32

**My Role:** Electronic circuit design, PCB design, embedded firmware development, power supply design, communication integration, and power-loss data preservation.

## Key Features

- **Programmable Scheduling:** Separate weekday and weekend schedules with configurable operating days and times.
- **Mobile Application Control:** Wi-Fi communication enables device control and configuration through a mobile application.
- **Power-Loss Data Preservation:** A voltage-fall interrupt initiates a Flash write before the supply voltage drops too far.
- **Manual Configuration:** UART communication provides an additional interface for manual configuration.
- **Custom Power Supply:** Designed an AC-DC power supply incorporating a transformer, bridge rectifier, and buck converter.
- **Project Approval:** The project was approved by Diversey.

## Scheduling & Control

The system supports configurable pump operating schedules for commercial dishwashing applications.

Users can set the operating days and times, with separate scheduling options for weekdays and weekends. The device can also be controlled and configured through a connected mobile application.

## Power-Loss Data Preservation

One of the main engineering challenges was ensuring that configuration data would not be lost when the power supply was interrupted.

I implemented a voltage-fall detection mechanism using an interrupt triggered when the 3.3 V supply dropped. The firmware used this event to initiate writing the required data to the STM32's internal Flash memory.

A capacitor provided temporary energy to keep the circuit powered long enough for the Flash write operation to complete.

This approach combined hardware-level power-failure detection with firmware-controlled data preservation.

## Power Supply Design

I designed the power supply circuitry for the system, using the following stages:

1. **AC Input and Transformer:** The mains input is stepped down through a transformer.
2. **Bridge Rectifier:** The transformer output is rectified to provide DC.
3. **Buck Converter:** A TPS54331-based step-down DC-DC converter generates the 3.3 V supply.

The power supply design was integrated into the custom electronic circuit and PCB.

## Communication Interfaces

### Wi-Fi

Wi-Fi communication connects the device to a mobile application, allowing users to control the pump and configure its operating schedule.

### UART

UART provides a serial communication interface for manual device configuration.

## My Contributions

- Electronic circuit and schematic design.
- Custom PCB design.
- STM32 embedded firmware development.
- Weekday and weekend scheduling logic.
- Wi-Fi communication and mobile application integration.
- UART-based manual configuration.
- Voltage-fall interrupt implementation.
- Flash memory data preservation during power loss.
- Capacitor-backed hold-up power design for completing Flash writes.
- AC-DC power supply design using a transformer, bridge rectifier, and TPS54331 buck converter.

## Engineering Scope

This project demonstrates experience in embedded control systems, scheduling logic, non-volatile data storage, interrupt-driven firmware, power-failure handling, wireless communication, and custom power supply design.

The power-loss mechanism highlights the integration of hardware and firmware to preserve critical configuration data during an unexpected interruption.

## Project Approval

The project was approved by Diversey.

