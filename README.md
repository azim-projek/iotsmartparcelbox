# 📦 Smart Parcel Box (ESP32 + Telegram + Keypad + Ultrasonic + Servo)

A Smart IoT Parcel Box system built using **ESP32**, **Ultrasonic Sensor**, **Keypad**, **Servo Motors**, and **Telegram Bot** integration.  
The system detects parcels, stores them safely, and allows secure retrieval using a password keypad.  
Password can be changed remotely via Telegram commands.

---

## 🚀 Features

✅ Detects parcels automatically using **HC-SR04 Ultrasonic Sensor**  
✅ Drops parcel inside storage using a **servo motor**  
✅ Secure parcel retrieval via **keypad password system**  
✅ Telegram notifications for parcel detection and door unlocks  
✅ Remote password change through **Telegram commands**  
✅ Compact and low-power ESP32-based IoT system  

---

## 🧩 Hardware Components

| Component | Function | ESP32 Pin |
|------------|-----------|-----------|
| **ESP32** | Main microcontroller + Wi-Fi | — |
| **HC-SR04 Ultrasonic Sensor** | Detects presence of parcel | TRIG → 16, ECHO → 34 |
| **Servo (dropServo)** | Drops parcel inside | 17 |
| **Servo (doorServo)** | Opens retrieval door | 18 |
| **4×4 Keypad** | User password input | Rows → 27,14,12,13 / Cols → 32,33,25,26 |

---

## ⚙️ Software Details

**Platform:** Arduino IDE  
**Libraries Required:**
- `WiFi.h`
- `WiFiClientSecure.h`
- `UniversalTelegramBot.h`
- `ESP32Servo.h`
- `Keypad.h`

**Default Password:** `1234`

---

## 🔐 Keypad Controls

| Key | Function |
|-----|-----------|
| `0–9, A–D` | Enter password |
| `*` | Clear entered password |
| `#` | Confirm password |

✅ **Correct Password:** Unlocks bottom door (servo moves)  
❌ **Wrong Password:** Sends "Wrong password!" message to Telegram  

---

## 💬 Telegram Commands

| Command | Description |
|----------|--------------|
| `/help` | Show available commands |
| `/getpass` | Display current password |
| `/setpass <newpass>` | Change password (4–8 digits only) |

Example:
