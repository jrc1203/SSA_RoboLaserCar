# 🚗 SSA_RoboLaserCar

A WiFi-controlled robot car with a Pan-Tilt laser mount — built on ESP32.  
Control it from your phone browser. No app needed.

---

## 🧠 What It Does

| Feature | Details |
|---|---|
| 🚗 Car Movement | Forward, Backward, Left, Right |
| 🎯 Pan Servo | Rotates laser left/right (GPIO 25) |
| 🎯 Tilt Servo | Tilts laser up/down (GPIO 33) |
| ⏺️ Record | Records your servo movements |
| ▶️ Play | Replays recorded movements |
| 🌙 Dark Mode | Toggle on the web page |

---

## 🔧 Hardware Required

- ESP32
- L298N Motor Driver
- 2× DC Motors
- 2× Servo Motors
- 3× Li-ion Batteries (11.1V)
- Buck Converter (set to 5V) — for servos
- Laser module (optional)
- Jumper wires

---

## ⚡ Wiring (Quick Reference)

```
Battery (+) ──► L298N [12V pin]
Battery (-) ──► L298N [GND]  ──► Buck GND ──► ESP32 GND  ← common ground!

L298N [5V pin]   ──► ESP32 [VIN]
Buck [5V output] ──► Servo Red wires

ESP32 GPIO 25 ──► Pan  Servo (signal)
ESP32 GPIO 32 ──► Tilt Servo (signal)

ESP32 GPIO 16, 17, 32 ──► L298N (Right Motor)
ESP32 GPIO 18, 19, 23 ──► L298N (Left Motor)
```

> ⚠️ **Most important:** All GNDs must be connected together!

---

## 📲 How to Use

1. Flash the code to ESP32 using Arduino IDE
2. Power on the robot
3. On your phone/laptop — connect to WiFi:
   - **Network:** `SSA_RoboLaserCar`
   - **Password:** `12345678`
4. Open browser → go to **`192.168.4.1`**
5. Control the car and laser from the webpage!

---

## 📦 Libraries Needed

Install these from Arduino IDE → Library Manager:

- `ESPAsyncWebServer`
- `AsyncTCP`
- `ESP32Servo`

---

## 📁 File

| File | Description |
|---|---|
| `SSA_RoboLaserCar.ino` | Main code — upload this to ESP32 |

---

*Made at Sri Sri Academy (SSA) 🏫*