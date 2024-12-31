# MPU6050-Module-Arduino-Integration-and-Example-Code
This repository provides a comprehensive guide to connecting and programming the MPU6050 gyroscope and accelerometer module with Arduino. It includes detailed connection instructions, example code, troubleshooting tips, and a step-by-step setup process. Perfect for beginners and enthusiasts working on motion-sensing projects.
# MPU6050 Module Connections and Usage Guide

This README provides a comprehensive guide to connecting and using the MPU6050 gyroscope and accelerometer module with an Arduino.

---

## MPU6050 Module Connections

| **MPU6050 Pin** | **Arduino Pin** | **Description**                          |
|------------------|-----------------|------------------------------------------|
| VCC              | 5V             | Provides power to the module (3.3V also supported). |
| GND              | GND            | Ground connection for the module.        |
| SCL              | A5 (Uno) / D21 (Mega) | Serial Clock Line for I2C communication. |
| SDA              | A4 (Uno) / D20 (Mega) | Serial Data Line for I2C communication.  |
| INT              | D2 (Optional)  | Interrupt pin for motion detection.      |

---

## Description of Connections

1. **Power Supply**  
   - Connect the **VCC** pin to the **5V** pin of the Arduino to power the MPU6050. If using a 3.3V system, connect to the 3.3V pin.  
   - Connect the **GND** pin to any **GND** pin on the Arduino for proper grounding.

2. **I2C Communication**  
   - The **SCL** pin of the MPU6050 connects to the **A5** pin on Arduino Uno or **D21** on Arduino Mega.  
   - The **SDA** pin connects to the **A4** pin on Arduino Uno or **D20** on Arduino Mega.

3. **Interrupt Pin (Optional)**  
   - The **INT** pin can be used for interrupt-based motion detection. Connect it to any digital pin (e.g., **D2**) if needed.

---

## Installation and Setup

### Prerequisites
1. **Hardware**:
   - MPU6050 module
   - Arduino board (e.g., Uno, Mega)
   - Jumper wires
2. **Software**:
   - Arduino IDE
   - `MPU6050` library (installable via Arduino Library Manager)

### Steps to Set Up
1. **Wiring**: Follow the table above to connect the MPU6050 to the Arduino board.
2. **Library Installation**: Install the MPU6050 library:
   - Open Arduino IDE.
   - Navigate to **Sketch > Include Library > Manage Libraries**.
   - Search for "MPU6050" and click "Install".
3. **Upload Code**:
   - Use the example code provided below to verify the MPU6050 functionality.

---

## Example Code

```cpp
#include <Wire.h>
#include <MPU6050.h>

MPU6050 mpu;

void setup() {
  Serial.begin(9600);
  Wire.begin();
  mpu.initialize();

  if (mpu.testConnection()) {
    Serial.println("MPU6050 connection successful");
  } else {
    Serial.println("MPU6050 connection failed");
  }
}

void loop() {
  int16_t ax, ay, az;
  int16_t gx, gy, gz;

  mpu.getMotion6(&ax, &ay, &az, &gx, &gy, &gz);

  Serial.print("Accel: ");
  Serial.print("X = "); Serial.print(ax);
  Serial.print(" | Y = "); Serial.print(ay);
  Serial.print(" | Z = "); Serial.println(az);

  Serial.print("Gyro: ");
  Serial.print("X = "); Serial.print(gx);
  Serial.print(" | Y = "); Serial.print(gy);
  Serial.print(" | Z = "); Serial.println(gz);

  delay(500);
}


# MPU6050 Module Integration with Arduino

This repository provides a guide for connecting and coding the MPU6050 gyroscope and accelerometer module with an Arduino. The MPU6050 allows you to measure angular velocity, acceleration, and motion detection using I2C communication.

---

## Table of Contents
- [Connections](#connections)
- [Code](#code)
- [Setup Instructions](#setup-instructions)
- [Troubleshooting](#troubleshooting)
- [License](#license)

---

## Connections

| **MPU6050 Pin** | **Arduino Pin**        | **Description**                          |
|------------------|------------------------|------------------------------------------|
| VCC              | 5V                    | Provides power to the module (3.3V also supported). |
| GND              | GND                   | Ground connection for the module.        |
| SCL              | A5 (Uno) / D21 (Mega) | Serial Clock Line for I2C communication. |
| SDA              | A4 (Uno) / D20 (Mega) | Serial Data Line for I2C communication.  |
| INT              | D2 (Optional)         | Interrupt pin for motion detection.      |

---

## Code

Below is the example code to get started with the MPU6050 module:

```cpp
#include <Wire.h>
#include <MPU6050.h>

MPU6050 mpu;

void setup() {
  Serial.begin(9600);
  Wire.begin();
  mpu.initialize();

  if (mpu.testConnection()) {
    Serial.println("MPU6050 connection successful");
  } else {
    Serial.println("MPU6050 connection failed");
  }
}

void loop() {
  int16_t ax, ay, az;
  int16_t gx, gy, gz;

  mpu.getMotion6(&ax, &ay, &az, &gx, &gy, &gz);

  Serial.print("Accel: ");
  Serial.print("X = "); Serial.print(ax);
  Serial.print(" | Y = "); Serial.print(ay);
  Serial.print(" | Z = "); Serial.println(az);

  Serial.print("Gyro: ");
  Serial.print("X = "); Serial.print(gx);
  Serial.print(" | Y = "); Serial.print(gy);
  Serial.print(" | Z = "); Serial.println(gz);

  delay(500);
}



### How to Use
1. Replace `Ajaya Physics` and `[https://github.com/AjayaPhysics]` with your details.
2. Save this file as `README.md` in your repository.
3. Commit and push the file to your GitHub repository.

Let me know if you'd like to customise it further!
