# Nandi-On-Device-Voice-Activator-for-Edge-Devices
Nandi is a low-latency, on-device voice activator built on a custom ESP32-S3 hardware platform. An ultra-lightweight keyword-spotting model runs entirely on the device and wakes a remote Indic ASR service only when the wake word is heard — the edge handles wake-up, the cloud handles the heavy lifting.

*Team Novadian, IERT Prayagraj · Team ID KT-2073**
**KAYA'26 Buildathon — Problem Statement 4: Low Latency and Efficient Voice
Activator for Edge Devices**

| | |
|---|---|
| Target hardware | ESP32-S3-WROOM-1-N16R8 |
| Microphone | I2S MEMS (ICS-43434) |
| Amplifier | MAX98357A class-D |
| Display | 1.3" OLED (128×64) |
| Power | USB-C + 1-cell Li-ion (MCP73831 charger, AP2112K-3.3 LDO) |
| Board | 2 layers, 70 × 60 mm, 1.6 mm FR-4, rev 1.0 |
| Wake word | "Nandi" — custom keyword, TFLite-Micro, ~14 KB int8 model |
| Wake accuracy | 97.4% catch rate, near-zero false activations |
| End-to-end latency | ~1.5 s median to first word of the answer |
| Languages | 11 Indian languages, mid-conversation switching |
| Live demo | nandi.spectrumlynk.com |

## How it answers Problem Statement 4

- **Efficiency** — the ~14 KB KWS model runs in a fraction of an audio frame;
  idle CPU stays under 10% in continuous-listening mode.
- **Accuracy** — 97.4% wake catch rate; a confidence threshold plus
  multi-frame confirmation drives false activations toward zero.
- **Latency** — streaming starts on the keyword's trailing edge, minimising the
  gap between keyword-end and the ASR server receiving audio.
- **Open KWS pipeline** — TensorFlow Lite for Microcontrollers; no proprietary
  voice-activation SDK, no pre-trained global-assistant keywords.

## Repository contents

| File | What it is |
|---|---|
| `hardware/BOM-and-Schematic.pdf` | Bill of materials + full circuit schematic |
| `hardware/schematic.pdf` | Full circuit schematic |
| `hardware/BOM-redacted.csv` | Bill of materials (Qty, Reference, Value, Footprint) |
| `hardware/assembly-drawing.pdf` | Top/bottom assembly drawing with reference designators |
| `hardware/3d/` | 3D renders of the assembled board (top, bottom, isometric) |
| `hardware/KT-2073_Buildathon_Deck.pdf` | 10-slide presentation deck |

The Nandi firmware and software stack are proprietary.

## License

Hardware design package © Team Novadian. All rights reserved.
"# NANDI--Low-latency-edge-device" 

