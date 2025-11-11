# LX470 Raspberry Pi Head Unit — Embedded Audio + Linux DSP

## 1. Project Overview
**Goal:** Replace the factory head unit in a Lexus LX470 with a custom Raspberry Pi–based touchscreen system that provides:
- Reliable boot-to-audio performance
- High-quality DAC audio pipeline (sub + 4-channel door speakers)
- Bluetooth music + optional hands-free calling
- Configurable EQ and audio tuning
- Automotive-grade power behavior (ACC-on / soft shutdown)
- Documented, reproducible build for portfolio demonstration

**Motivation:** Combine embedded systems, DSP/audio engineering, Linux systems design, and automotive electronics into a cohesive project that bridges EE and CS domains. Overcome the limitations of standard car audio equipment such as: poor audio quality to price value ratio, lackluster UI design and customization, and built in audio tuning.

---

## 2. System Architecture
### 2.1 Block Diagram (Signal Path)


### 2.2 Power Path


### 2.3 Software Stack
- OS: Raspberry Pi OS Lite (read-only root overlay)
- Audio: PipeWire or PulseAudio + ALSA
- Bluetooth: BlueZ + A2DP + optional HFP support
- UI: OpenAuto Pro / Qt / or Browser-based UI
- Configuration managed via systemd services + shell scripts

---

## 3. Hardware BOM (with Low / Mid / High Options)
| Component | Low Tier | Mid Tier | High Tier | Notes |
|---------|---------|---------|----------|-------|
| Compute | RPi 4B (4-8GB) | RPi 5 | CM4 + Carrier Board | CM4 allows clean packaging |
| Display | 7" IPS Capacitive | 8" IPS | 9" Hi-Brightness Automotive Panel | Avoid resistive touch |
| DAC | PCM5122 (I2S) | Topping D10s (USB) | Khadas Tone2 Pro | USB simplest driver path |
| Line Driver | None | AudioControl LC1 | miniDSP 2x4HD | miniDSP allows serious tuning |
| 4ch Amp | Alpine KTP-445U | Rockford R2-300x4 | JL XD400/4 | Match RMS to speakers |
| Sub Amp | Existing | — | — | Already installed |
| Power | LM2596 + Filter | Noise-Hardened Buck | M2 Automotive DC-DC + UPS HAT | Key for low noise and safe shutdown |

---

## 4. Wiring & Installation
### 4.1 Vehicle Harness Map
Include:
- Wire color
- Pin number
- Signal purpose
- Destination in new system

Example format:


### 4.2 Grounding Strategy
- Single chassis ground point for all audio components
- Star ground layout to minimize loop noise

---

## 5. Software Configuration
### 5.1 OS Setup
- Flash OS Lite
- Set hostname + enable SSH + update packages

### 5.2 Audio Setup
- Detect DAC (`aplay -l`)
- Configure PipeWire default sinks
- Apply initial EQ profile

### 5.3 Safe Shutdown Service
- systemd service listening for GPIO ACC state
- Graceful write flush + display sleep

---

## 6. Tuning & Verification
- Gain staging (head → line → amp)
- Frequency sweeps + EQ
- Noise floor test (engine ON vs OFF)

Include screenshots / measurements.

---

## 7. Demo / Results
- Boot-to-audio time
- Latency behavior
- UI walk-through video
- Before/after audio impressions

---

## 8. Lessons Learned
Reflect on:
- Linux system control
- Automotive electrical noise mitigation
- DSP tuning strategy
- UI/UX considerations in embedded systems

---

## 9. Future Improvements
- Ambient light UI dimming
- Steering wheel button integration
- Offline maps / GPS feedback
- CAN bus integration


