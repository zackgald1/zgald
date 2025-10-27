# String Machine

[🎥 Watch Demonstration of commucation over UART]([https://youtu.be/example](https://youtube.com/shorts/tUUIbMUjmYQ)) <!-- replace with your video link -->

---

## Summary

The **String Machine** is an interactive K–8 educational exhibit that visualizes **sound frequency** using a vibrating string driven by a **NEMA-17 stepper motor**.  
It demonstrates how frequency, wavelength, and pitch relate — transforming invisible sound waves into a visible physical medium.  

This system integrates **embedded motor control**, **SPI communication**, and **firmware-level motion commands** to create precise harmonic vibrations corresponding to musical notes.

---

## System Overview

| Component | Description |
|------------|-------------|
| **Microcontroller** | PIC18F46Q10 — orchestrates SPI communication and timing control |
| **Motor Driver** | Trinamic TMC5072 — dual stepper driver with microstepping and velocity mode |
| **Motor** | NEMA-17 stepper — physically vibrates the string |
| **Power Supply** | 9 V barrel-jack through onboard regulators (3.3 V logic) |
| **Interface** | UART daisy-chain for control messages and parameter feedback |
| **PCB** | Custom-designed in OrCAD/Allegro with bypass capacitors and labeled connectors |

---

## How It Works

1. **Frequency Command Input**  
   A user selects or sends a desired pitch frequency via UART.

2. **Microcontroller Processing**  
   The PIC18F46Q10 receives the command, converts it to a **velocity value**, and sends it through SPI to the TMC5072.

3. **Motor Actuation**  
   The TMC5072 outputs precisely timed step pulses to the NEMA-17 motor, producing a standing wave on the string.

4. **Visual Feedback**  
   A fixed laser line or LED light across the string reveals stationary wave patterns proportional to the drive frequency.

5. **Interactive Operation**  
   Multiple modes — constant frequency, sweep, or random note selection — let students visualize pitch and wavelength.

---

## Skills I Gained

- **Embedded SPI communication** with a multi-axis stepper driver (TMC5072).  
- **PCB design** with proper decoupling, annular ring sizing, and signal routing.  
- **Stepper motion control theory** — microstepping, waveform synthesis, and vibration frequency mapping.  
- **UART daisy-chain protocol design** for sending and receiving frequency/speed data.  
- **Firmware integration** between motion IC, MCU, and user interface.  
- **System-level debugging** (oscilloscope signal verification, SPI timing, and logic analysis).  

---
