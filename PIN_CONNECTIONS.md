# 🔌 ESP32 Pin Connections – Smart Medicine Reminder Box


This document explains the **exact pin-to-pin wiring** between the ESP32 and all sensors/modules used in the project.

---

## 📟 ESP32 ↔ Hardware Mapping

### 🔔 Buzzer
| Component | ESP32 Pin |
|---------|-----------|
| Buzzer + | GPIO 27 |
| Buzzer – | GND |

---

### 🔴 IR Sensors (Medicine Taken Detection)

| Slot | Signal | ESP32 Pin |
|----|--------|----------|
| IR Sensor – Slot 1 | OUT | GPIO 13 |
| IR Sensor – Slot 2 | OUT | GPIO 14 |
| IR Sensor – Slot 3 | OUT | GPIO 26 |
| IR Sensor – Slot 4 | OUT | GPIO 25 |

**Logic Used**
- LOW → Medicine Taken  
- HIGH → Not Taken  
- Mode: `INPUT_PULLUP`

---

### 🚪 Limit Switches (Box Open Detection)

| Box Type | Signal | ESP32 Pin |
|--------|--------|----------|
| Morning Box | Signal | GPIO 32 |
| Evening Box | Signal | GPIO 33 |

**Logic Used**
- HIGH → Box Open  
- LOW → Box Closed  
- Mode: `INPUT_PULLDOWN`

---

### 📡 Ultrasonic Sensors (Medicine Level Detection)

#### Slot 2
| Signal | ESP32 Pin |
|------|-----------|
| TRIG | GPIO 17 |
| ECHO | GPIO 5 |

#### Slot 4
| Signal | ESP32 Pin |
|------|-----------|
| TRIG | GPIO 16 |
| ECHO | GPIO 4 |

**Notes**
- Distance measured only when box is closed  
- Used to detect **low medicine level**

---

### ⏰ RTC DS3231 (Time Management)

| RTC Pin | ESP32 Pin |
|-------|-----------|
| SDA | GPIO 21 |
| SCL | GPIO 22 |
| VCC | 3.3V |
| GND | GND |

Used for:
- Accurate alarm timing
- Timestamped logs
- NTP synchronization backup

---

## ⚡ Power Connections

| Device | VCC | GND |
|------|-----|-----|
| ESP32 | USB / 5V | GND |
| IR Sensors | 3.3V / 5V | GND |
| Ultrasonic Sensors | 5V | GND |
| RTC DS3231 | 3.3V | GND |
| Buzzer | 3.3V | GND |

⚠️ **All grounds must be common**

---

## 🧠 Design Logic Summary

- Alarm rings until **correct box is opened**
- Medicine intake is confirmed using **IR sensors**
- Ultrasonic sensors prevent **empty-box situations**
- RTC ensures alarms work even without internet
- Blynk provides **real-time monitoring & logs**

---

## ✅ Tested & Working Setup

- ESP32 Dev Board  
- HC-SR04 Ultrasonic Sensors  
- IR Obstacle Sensors  
- DS3231 RTC  
- Blynk IoT Platform  

This pin configuration is **fully tested and stable** with the current firmware.

---


