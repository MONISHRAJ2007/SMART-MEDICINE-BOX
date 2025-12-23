# SMART-MEDICINE-BOX


An **IoT-based smart medicine reminder system** designed to ensure **timely medicine intake**, reduce missed doses, and monitor medicine availability in real time.

Built using **ESP32**, **RTC DS3231**, **IR sensors**, **Ultrasonic sensors**, and **Blynk IoT**, this project combines hardware + software to solve a real-world healthcare problem.

---

## 🚀 Features

- ⏰ **Smart Alarm System**
  - User-defined alarm time via Blynk app
  - Buzzer repeats until the medicine box is opened

- 📦 **Medicine Taken Detection**
  - IR sensors confirm whether medicine is taken or not
  - Logs displayed in Blynk Terminal

- 📉 **Medicine Level Monitoring**
  - Ultrasonic sensors detect low medicine levels
  - Automatic warning alerts

- 🕒 **Accurate Time Management**
  - RTC DS3231 with NTP synchronization
  - Real-time clock display in Blynk

- 📲 **IoT Dashboard (Blynk)**
  - Live data visualization
  - Alerts, logs, and remote monitoring

---

## 🧩 Hardware Components Used

- ESP32 Dev Board  
- RTC DS3231  
- IR Sensors (4x)  
- Ultrasonic Sensors (2x)  
- Limit Switches (Morning & Evening)  
- Buzzer  
- Medicine Box Enclosure  

---

## 📱 Blynk Virtual Pins

| Virtual Pin | Purpose |
|------------|--------|
| V0 | Alarm Hour |
| V1 | Alarm Minute |
| V5 | Medicine Level Alerts |
| V6 | IR Status Terminal |
| V7 | Live Time Display |
| V30 | Slot 2 Medicine Level |
| V31 | Slot 4 Medicine Level |

---

## ⚙️ Working Principle

1. User sets alarm time in the Blynk app  
2. At the scheduled time, the buzzer turns ON  
3. Alarm stops **only when the box is opened**  
4. IR sensors verify if medicine is taken  
5. Ultrasonic sensors monitor medicine quantity  
6. Status and alerts are sent to Blynk in real time  

---

## 🧠 System Intelligence

- Alarm continues until the correct compartment is opened
- Prevents false confirmation without box interaction
- Differentiates **morning & evening doses**
- Avoids ultrasonic errors when the box is open
- Timestamped logs ensure traceability and accountability


## 🏆 Why This Project Is Unique

Unlike basic reminder systems, this solution:
- Confirms **actual medicine intake**, not just alarms
- Tracks **remaining medicine quantity**
- Provides **real-time cloud monitoring**
- Is low-cost, scalable, and elderly-friendly


