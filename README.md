# Automatic Optical Audio Switch (ESP32)

<img width="1199" height="518" alt="{8CCD83B7-7E51-4EB5-BC00-117256F870E5}" src="https://github.com/user-attachments/assets/b21e8832-3f45-458c-bbca-89d5a4615198" />

Automatic switching between **two TOSLINK / SPDIF inputs** to **one output**
based on signal activity detection with an ESP32C3.

---

## Features
- 2× optical input → 1× optical output
- Automatic source selection (A/B)
- Signal detection via frequency measurement
- Configurable thresholds and timing
- Anti-flicker logic
- ESPHome firmware
- Web UI and Home Assistant integration
- No SPDIF decoding or audio processing
- USB-C powered
- 3D-printed enclosure

---

## Concept
Each optical input is converted into a digital pulse stream.
The ESP32 measures the divided SPDIF clock frequency and switches the output
to the active (playing) channel.

<img width="962" height="507" alt="ESP32-Optical-Audio-Switch-System-Diagram drawio" src="https://github.com/user-attachments/assets/dabcfd8a-5b40-4a0b-8f13-5f10740266a0" />

> [!NOTE]
> The actual audio path is switched purely in hardware. The ESP32 only controls the selection logic and does not touch the audio data stream itself.

---

## Build
1. Assemble PCB according to the KiCad project
2. Flash ESPHome/OTA firmware
3. Use Web UI or Home Assistant for configuration
4. Connect device to optical audio setup

---

## Documentation
Detailed explanations, diagrams and project logs are available on: **[Project page – Hackaday.io](https://hackaday.io/project/204791-automatic-optical-audio-switch-esp32)**

---

## PCBs
If you want to buy a bare or assembled PCB of this project, use this link to support me, thanks!

https://www.pcbway.com/project/shareproject/Automatic_Optical_Audio_Switch_ESP32_13712e76.html
