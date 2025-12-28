NOTE: WORK IN PROGRESS! MORE INFO COMING SOON.

<img width="1599" height="690" alt="{8CCD83B7-7E51-4EB5-BC00-117256F870E5}" src="https://github.com/user-attachments/assets/b21e8832-3f45-458c-bbca-89d5a4615198" />

## Overview

The **Automatic Optical Audio Switch** is a compact, ESP32-based device that automatically switches between **two TOSLINK / SPDIF optical audio inputs** and routes the active signal to a **single optical output**.

Instead of relying on manual buttons or audio decoding, the device detects **real signal activity** on each input and switches autonomously once a configurable condition is met.  
This makes it ideal for home audio setups where multiple optical sources are used but only one downstream optical input is available.

The project is designed as a **DIY-friendly, low-cost solution**, fully configurable via **ESPHome**, Home Assistant, or a built-in web interface.

---

## Features

- Automatic switching between **2 optical audio inputs → 1 optical output**
- Works with **TOSLINK / SPDIF** signals
- Signal presence detection based on **pulse/frequency measurement**
- Configurable per channel:
  - Frequency threshold
  - Minimum active time before switching
- Anti-flicker logic to prevent rapid toggling
- ESPHome-based firmware with OTA updates
- Live configuration via:
  - Home Assistant
  - Integrated web interface
- No SPDIF decoding or audio processing required
- Compact enclosure made from **3D-printed parts**

---

## How It Works

Each optical input is converted into a digital pulse signal using a standard TOSLINK receiver module.  
The ESP32 continuously monitors both inputs and evaluates their activity:

1. Incoming SPDIF signals are frequency-divided to a measurable range  
2. The ESP32 counts pulses to determine signal activity  
3. If an input stays above a configurable frequency threshold for a defined time:
   - **Channel A → Switch OFF**
   - **Channel B → Switch ON**

This approach ensures:
- Stable switching behavior
- Immunity to short dropouts
- Deterministic selection of the active source

---

## Hardware Overview

### Main Components
- **ESP32-C3** microcontroller
- 2× TOSLINK optical receivers (SPDIF input)
- Frequency divider logic for signal detection
- Digital 2:1 multiplexer for optical signal routing
- Optical transmitter for SPDIF output
- Status LEDs for basic feedback

### Optical Switching
The actual audio path is switched purely in hardware.  
The ESP32 only controls the selection logic and does not touch the audio data stream itself.

---

## Enclosure

The enclosure consists of **two 3D-printed parts**:

  <img width="567" height="444" alt="{B1711DB5-2587-472B-A74F-2275CF7FA31B}" src="https://github.com/user-attachments/assets/24449f8f-90f0-4175-b230-ff69b893a102" />

---

## Typical Use Cases

- Automatically switching optical audio between **TV and game console**
- Clean audio routing in minimalist setups
- DIY smart-home audio integration

---

