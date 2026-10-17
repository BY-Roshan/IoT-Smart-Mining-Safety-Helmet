# 🪖 IoT Smart Mining Safety Helmet

An Arduino-based IoT smart safety helmet designed for underground miners. This wearable device continuously monitors hazardous environments for toxic gases, flame/fire hazards, and miner distress using an SOS push button, while transmitting live telemetry and GPS coordinates to an Android smartphone via Bluetooth.

---

## 🚀 Key Features

* **Hazard Detection:** 
  * **Flame Sensor:** Detects fire hazards using infrared light detection.
  * **MQ-2 / MQ-4 Gas Sensor:** Monitors for combustible gases, smoke, and methane leaks.
* **Emergency SOS System:** Dedicated physical push button that instantly triggers visual/audible alarms and sends distress signals.
* **Live GPS Tracking:** Integrates a **NEO-6M GPS module** to capture real-time latitude and longitude coordinates, generating clickable Google Maps links for emergency responders.
* **Bluetooth Telemetry:** Streams real-time safety status (`[SAFE]` or `🚨 DANGER ALERT 🚨`) directly to an Android phone using an HC-05/HC-06 Bluetooth module.
* **Visual & Audible Indicators:** Drives an emergency LED indicator and active buzzer on danger events.

---

## 🛠️ Hardware Components Required

| Component | Description | Connected Pin / Interface |
| :--- | :--- | :--- |
| **Arduino Uno** | Microcontroller board | Core processing unit |
| **HC-05 / HC-06** | Bluetooth Classic Module | Pins 10 (RX) & 11 (TX via SoftwareSerial) |
| **NEO-6M GPS** | GPS Receiver Module | Pins 3 (RX) & 4 (TX via SoftwareSerial) |
| **MQ-2 / MQ-4** | Gas / Smoke Sensor | Analog Pin `A0` |
| **Flame Sensor** | IR Flame Sensor Module | Digital Pin `5` (`D0`) |
| **Push Button** | Tactile 4-Pin SOS Switch | Digital Pin `2` (with `INPUT_PULLUP`) |
| **LED Indicator** | Emergency Status LED | Digital Pin `6` (via 220Ω resistor) |
| **Active Buzzer** | Alarm Buzzer (Optional) | Digital Pin `8` |

---

## 📌 Wiring Pinout Reference

```text
Arduino Uno <---> Peripherals
--------------------------------------------------
Pin 2  <---> SOS Push Button (Other leg to GND)
Pin 3  <---> NEO-6M GPS TX
Pin 4  <---> NEO-6M GPS RX
Pin 5  <---> Flame Sensor D0 / OUT
Pin 6  <---> SOS LED (+) [with 220Ω resistor]
Pin 8  <---> Buzzer (+) [Optional]
Pin 10 <---> HC-06 Bluetooth TXD
Pin 11 <---> HC-06 Bluetooth RXD
A0     <---> MQ-2 / MQ-4 Gas Sensor A0
5V     <---> Shared VCC Rail (GPS, Bluetooth, Sensors)
GND    <---> Shared Ground Rail
A0     <---> MQ-2 / MQ-4 Gas Sensor A0
5V     <---> Shared VCC Rail (GPS, Bluetooth, Sensors)
GND    <---> Shared Ground Rail
