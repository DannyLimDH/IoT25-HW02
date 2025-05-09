# IoT25-HW02: ESP32 Button → LED Control

This project uses an ESP32 board to detect button input and control an LED accordingly.

---

## 🧾 Objectives

- Practice reading digital input (button)
- Control digital output (LED)
- Monitor input state via Serial Monitor

---

## 🧰 Components

- ESP32 DevKit v1  
- Push Button module  
- LED module  
- Jumper wires  
- Micro USB cable  

---

## 🔌 Circuit Connection

- **Button Module → ESP32**
  - V (VCC) → 3.3V
  - G (GND) → GND
  - S (Signal) → GPIO 4

- **LED Module → ESP32**
  - V (VCC) → 3.3V
  - G (GND) → GND
  - S (Signal) → GPIO 5

> 📸 Refer to the wiring photo below for exact connections.

---

## 🧾 Code

```cpp
const int buttonPin = 4;
const int ledPin = 5;
int buttonState = 0;

void setup() {
  Serial.begin(115200);
  pinMode(buttonPin, INPUT);
  pinMode(ledPin, OUTPUT);
}

void loop() {
  buttonState = digitalRead(buttonPin);
  Serial.println(buttonState);
  if (buttonState == HIGH) {
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
  }
}
```

---

## 📸 Screenshots

!![스크린샷 1](https://github.com/DannyLimDH/IoT25-HW02/blob/main/media/hw2.png)

---

## ▶ Demo GIF

![Demo](./media/IoT25-HW02.gif)

---
## References
Rui Santos, VSCode + PlatformIO IDE: ESP32 & ESP8266, Arduino (Random Nerd Tutorials)
(https://randomnerdtutorials.com/esp32-digital-inputs-outputs-arduino/)

---
