<img width="1199" height="518" alt="{8CCD83B7-7E51-4EB5-BC00-117256F870E5}" src="https://github.com/user-attachments/assets/b21e8832-3f45-458c-bbca-89d5a4615198" />

# Automatic Optical Audio Switch (ESP32)

Automatic switch between **two TOSLINK/SPDIF audio sources** to **one output**.  
Ideal for home audio setups where only one optical input is available.

## Features

- Automatic switching between **2 optical audio inputs → 1 optical output**
- Works with **TOSLINK / SPDIF** signals
- Signal presence detection based on **frequency measurement**
- Configurable per channel:
  - Frequency threshold
  - Minimum active time before switching
- Anti-flicker logic to prevent rapid toggling
- ESPHome-based firmware with OTA updates
- Live configuration via:
  - Home Assistant
  - Integrated web interface
- No SPDIF decoding or audio processing required
- Supports S/PDIF clock rate up to 16 MHz
- Power Supply via USB-C
- Compact enclosure made from **3D-printed parts**

### Physical Connections
<img width="1133" height="421" alt="{75A2652D-B607-47E5-BACF-B1780177E79F}" src="https://github.com/user-attachments/assets/75cf7473-125e-4f13-a643-e44ace7cf6e6" />

### Web Interface
<img width="1651" height="476" alt="{3F8E21B6-B1A3-4344-B7FA-34EA117E3698}" src="https://github.com/user-attachments/assets/01123282-c29e-4b2a-ae40-9a5e5b0cae44" />

---

## How It Works

<img width="962" height="507" alt="ESP32-Optical-Audio-Switch-System-Diagram drawio" src="https://github.com/user-attachments/assets/dabcfd8a-5b40-4a0b-8f13-5f10740266a0" />

Each optical input is converted into a digital pulse signal using a standard TOSLINK receiver module.  
The ESP32 continuously monitors both inputs and evaluates their activity:

1. Incoming SPDIF signals are frequency-divided (division by 4096) to a measurable range  
2. The ESP32 counts pulses to determine signal activity  
3. If an input stays above a configurable frequency threshold for a defined time:
   - **Channel A → Switch OFF**
   - **Channel B → Switch ON**
4. Once switched, the system waits until the signal drops below the threshold before re-arming

This approach ensures:
- Stable switching behavior
- Immunity to short dropouts
- Deterministic selection of the active source

---

## Hardware Overview

<img width="573" height="494" alt="{08CA482D-D1EF-4FA0-8F68-E1E6B7A69B8E}" src="https://github.com/user-attachments/assets/88a98662-d8a8-4816-801d-fe976314749d" />

### Main Components
- **ESP32-C3** microcontroller
- 2× TOSLINK optical receivers (SPDIF input)
- Frequency divider logic for signal detection
- Digital 2:1 multiplexer for channel selection
- Optical transmitter for SPDIF output
- Status LEDs for basic feedback

### Optical Switching
> [!NOTE]
> The actual audio path is switched purely in hardware. The ESP32 only controls the selection logic and does not touch the audio data stream itself.

---

## Enclosure

The enclosure consists of **two 3D-printed parts**:

  <img width="567" height="444" alt="{B1711DB5-2587-472B-A74F-2275CF7FA31B}" src="https://github.com/user-attachments/assets/24449f8f-90f0-4175-b230-ff69b893a102" />

---

## Build
1. Assemble PCB according to the KiCad project
2. Flash ESPHome/OTA firmware
3. Use Web UI or Home Assistant for configuration
4. Connect device to optical audio setup
   
---

