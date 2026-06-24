# Bill of Materials (BOM)

## Overview

This document lists the primary hardware components used during the development of the AI Autonomous DonkeyCar platform.

The system is based on a Raspberry Pi powered DonkeyCar architecture and was developed in collaboration with a colleague within an industrial project environment involving ChipGlobe GmbH and Infineon technologies.

---

# Core Computing Components

| Component                  | Quantity | Purpose                      |
| -------------------------- | -------- | ---------------------------- |
| Raspberry Pi 4 Model B     | 1        | Main onboard computer        |
| MicroSD Card               | 1        | Operating system and storage |
| Raspberry Pi Camera Module | 1        | Vision and AI perception     |
| Power Bank                 | 1        | Raspberry Pi power supply    |

---

# Vehicle Platform

| Component                         | Quantity | Purpose              |
| --------------------------------- | -------- | -------------------- |
| RC Car Chassis                    | 1        | Vehicle platform     |
| Steering Servo                    | 1        | Steering control     |
| Electronic Speed Controller (ESC) | 1        | Motor speed control  |
| DC Motor                          | 1        | Vehicle propulsion   |
| Drive Battery                     | 1        | Vehicle power source |
| Wheels and Tires                  | 4        | Vehicle movement     |

---

# Control Electronics

| Component              | Quantity | Purpose                              |
| ---------------------- | -------- | ------------------------------------ |
| PCA9685 PWM Controller | 1        | Steering and throttle PWM generation |
| Jumper Wires           | Various  | Electrical connections               |
| Mounting Hardware      | Various  | Component mounting                   |

---

# User Control Devices

| Component       | Quantity | Purpose                                    |
| --------------- | -------- | ------------------------------------------ |
| Xbox Controller | 1        | Manual driving and data collection         |
| Smartphone      | 1        | DonkeyCar mobile application               |
| Laptop/PC       | 1        | Training, configuration and remote control |

---

# Networking Components

| Component             | Quantity | Purpose                  |
| --------------------- | -------- | ------------------------ |
| Wi-Fi Network         | 1        | Vehicle communication    |
| VPN Connection        | 1        | Remote vehicle operation |
| Router / Access Point | 1        | Network infrastructure   |

---

# Experimental Components

The following components were evaluated during obstacle avoidance research.

These components are not part of the final autonomous driving stack.

| Component                | Quantity | Purpose                    |
| ------------------------ | -------- | -------------------------- |
| VL53L0X ToF Sensor       | 3        | Distance measurement       |
| TCA9548A I2C Multiplexer | 1        | Multi-sensor communication |

---

# Software Environment

| Software             | Purpose                      |
| -------------------- | ---------------------------- |
| Raspberry Pi OS      | Vehicle operating system     |
| DonkeyCar            | Autonomous driving framework |
| Python               | Development language         |
| TensorFlow           | Model training and inference |
| Git                  | Version control              |
| OpenCV (Future Work) | Computer vision              |
| YOLO (Future Work)   | Object detection             |

---

# Final System Configuration

The final autonomous driving configuration consists of:

Pi Camera
↓
DonkeyCar AI Model
↓
PCA9685
↓
Steering + Throttle

Obstacle avoidance sensors were evaluated separately and documented as experimental research.

---

# Future Hardware Upgrades

Potential future additions include:

* Higher-resolution camera
* Raspberry Pi 5
* OpenCV vision pipeline
* YOLO object detection
* Additional computing acceleration
* Advanced telemetry systems
* Vision-based obstacle avoidance
