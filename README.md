# 💡 Sound-Reactive Dancing LED Micro Project

An upgraded version of the classic Dancing LED project that uses a **sound sensor** to trigger LED patterns—making the LEDs dance in sync with claps, music, or other sounds.

## 🎯 Project Overview

This project demonstrates how LEDs can be made to "dance" not only in programmed sequences but also in response to **sound inputs** like claps or beats. A sound sensor (e.g., microphone module) detects vibrations, which are then processed by a microcontroller to light up LEDs in real time.

Perfect for beginners in electronics and embedded systems who want to explore real-world interactivity.

## ⚙️ Hardware Components

- 🧠 Microcontroller: Arduino UNO / ESP8266 / ATmega328
- 🔊 Sound Sensor Module (e.g., KY-038 or LM393)
- 🔴 8x LEDs
- 🛡️ Resistors (220Ω – 330Ω)
- 🔗 Breadboard & Jumper Wires
- 🔋 9V Battery or USB Power Supply

## 🔄 Working Principle

- The **sound sensor** detects loud sounds or vibrations.
- When sound exceeds a threshold, the microcontroller turns on LEDs in a dancing or pulsing pattern.
- If no sound is detected, LEDs remain off or blink at a slower pace.

## 📟 Features

- 🔊 Sound-triggered LED response
- 🧠 Programmed dancing LED patterns
- 🔀 Mix of manual sequence and real-time input
- 🔋 Low-power and beginner-friendly
- 📲 Easily expandable with more sensors


##Setup Image

![image alt](https://github.com/Ann-mary20/Sound-Reactive-Dancing-LED-Mini-Project/blob/main/WhatsApp%20Image%202025-07-05%20at%201.52.52%20PM.jpeg)
![image alt](https://github.com/Ann-mary20/Sound-Reactive-Dancing-LED-Mini-Project/blob/main/WhatsApp%20Image%202025-07-05%20at%201.52.53%20PM%20(1).jpeg)
![image alt](https://github.com/Ann-mary20/Sound-Reactive-Dancing-LED-Mini-Project/blob/main/WhatsApp%20Image%202025-07-05%20at%201.52.53%20PM.jpeg)

## 💻 Sample Arduino Code

```cpp
const int soundSensorPin = A0;
int ledPins[] = {2, 3, 4, 5, 6, 7, 8, 9};

void setup() {
  Serial.begin(9600);
  pinMode(soundSensorPin, INPUT);
  for (int i = 0; i < 8; i++) {
    pinMode(ledPins[i], OUTPUT);
  }
}

void loop() {
  int soundValue = analogRead(soundSensorPin);
  Serial.println(soundValue);

  if (soundValue > 500) {  // Adjust threshold as needed
    for (int i = 0; i < 8; i++) {
      digitalWrite(ledPins[i], HIGH);
      delay(50);
      digitalWrite(ledPins[i], LOW);
    }
  } else {
    // Optional: Dim all LEDs or keep them OFF
    for (int i = 0; i < 8; i++) {
      digitalWrite(ledPins[i], LOW);
    }
  }
}
