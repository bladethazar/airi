# AIRI - Autonomous Intelligent Reactive Interface

**AIRI** (Autonomous Intelligent Reactive Interface) is a modular, AI-driven vehicle assistant developed for a 2016 Subaru WRX STI. Inspired by KITT (Knight Rider), AIRI blends modern AI technology with Japanese engineering aesthetics.  
AIRI is designed as an autonomous and personal co-pilot, offering voice interaction, real-time vehicle data visualization, and adaptive learning behavior.

---

## 🌸 Meaning & Personality of AIRI

**AIRI (アイリ)** represents:

- **A**utonomous  
- **I**ntelligent  
- **R**eactive  
- **I**nterface  

AIRI’s personality is a blend of **professional** efficiency and **japanese** charm, with a calm, competent demeanor mixed with a hint of **TARS-like** wit. She is always ready to assist, bringing both helpfulness and a bit of friendly banter when needed. AIRI is designed to:

AIRI is designed to:

- Provide vehicle insights and diagnostics in real-time.
- Engage in natural voice conversations (local or remote).
- Learn user preferences over time, offering a tailored experience.
- Execute tasks and fetch online information when connected.

---

## 🚗 Project Overview

AIRI is a hybrid AI platform running on a **ROG X13**, interacting with vehicle systems via **ESP32**, and offering a custom UI through an **Android Headunit** with LTE connectivity.  
Data flows through WebSockets and integrates into a home **K3s cluster** running InfluxDB and Home Assistant.

---


---

## 🎯 Project Goals

- Run **AIRI AI assistant** locally with offline capability.
- Voice-command interface for vehicle data and information retrieval.
- Real-time telemetry monitoring and reporting.
- Remote and local vehicle management features (future).
- Integration into **K3s Home Cluster** for long-term analytics and automations.

---

## 🛠️ Hardware Components

| Component            | Purpose                                   |
|----------------------|-------------------------------------------|
| **ROG X13 (2021)**   | AIRI AI Server (LLM, STT, TTS, WebSocket) |
| **ESP32 NodeMCU**    | OBD2 Vehicle Telemetry & Sensor Node      |
| **Android Headunit** | UI, Voice Input/Output, LTE Hotspot       |
| **OBD2 Adapter**     | Vehicle Data Capture (via ESP32)          |
| **K3s Cluster**      | InfluxDB, Home Assistant, Remote Access   |

---

## 🧰 Software Stack

| Software            | Function                                   |
|---------------------|--------------------------------------------|
| **Ollama (Mistral)**| AIRI LLM (Persona & Contextual Reasoning)  |
| **Whisper (Wyoming)**| Speech-to-Text Engine                     |
| **Piper (Wyoming)** | Text-to-Speech Engine                     |
| **ESP32 Firmware**  | OBD2 Data Capture & WebSocket Client      |
| **WebSocket Server**| Data Ingestion Service on ROG X13         |
| **InfluxDB (K3s)**  | Vehicle Telemetry Database                |
| **Home Assistant**  | Visualization and Automation Rules        |

---

## 🚦 Communication Flow

[Android Headunit]
   ⇄ Voice Commands (Whisper STT)
   ⇄ UI Feedback from AIRI

[ESP32 NodeMCU]
   ⇄ Sends OBD2 Telemetry to AIRI WebSocket Server
   ⇄ Optional: Sensor Data (Temp, Accel, GPS)

[ROG X13 - AIRI]
   ⇄ Runs LLM (Mistral) + AIRI Persona
   ⇄ Receives voice input, telemetry, and processes actions
   ⇄ Sends data to K3s InfluxDB

---

## 🚙 OBD2 Integration

The **OBD2 Adapter** connects to the vehicle's **CAN Bus** to capture real-time telemetry data, including vehicle speed, RPM, engine temperature, and other critical diagnostics. The data is sent via **ESP32** to the AIRI AI server, which processes it and offers insights, updates, and visualizations through the Android Headunit UI.

### Key OBD2 Data:

- Vehicle Speed (mph/kmh)
- Engine RPM
- Throttle Position
- Fuel Level
- Engine Temperature
- DTC (Diagnostic Trouble Codes)

This data is captured by the **ESP32 NodeMCU** via the OBD2 interface and transmitted in **JSON** format over **WebSocket** to the **ROG X13**, where AIRI processes it.

---

📖 License
This project is intended for personal and educational use only.
Ensure you comply with local laws before implementing vehicle control functionality.

---

👨‍💻 Author
M.F.
GitHub: [bladethazar]
Project AIRI © 2025
