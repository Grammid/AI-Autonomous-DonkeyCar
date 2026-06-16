# AI Autonomous DonkeyCar

## Project Overview

This repository documents the development of an autonomous Raspberry Pi based vehicle using DonkeyCar.

The project was developed in collaboration with a colleague within an industrial project environment involving Chipglobe GmbH and Infineon technologies.

The objective was to design, train, and deploy an autonomous vehicle capable of lane following, remote operation, and future computer vision based navigation.

---

## Objectives

* Develop an autonomous driving platform using DonkeyCar
* Train AI models for lane following
* Enable multiple vehicle control methods
* Investigate obstacle avoidance techniques
* Build a foundation for future computer vision research

---

## Hardware

* Raspberry Pi 4 Model B
* Raspberry Pi Camera
* PCA9685 PWM Controller
* RC Servo
* ESC
* Xbox Controller
* DonkeyCar Chassis

---

## Software

* DonkeyCar 5.x
* Python
* TensorFlow
* Raspberry Pi OS
* OpenCV (planned)
* YOLO (future work)

---

## System Architecture

Pi Camera
↓
DonkeyCar AI Model
↓
PCA9685
↓
Steering + Throttle

---

## Vehicle Control Methods

### Xbox Controller

Primary control method used for:

* Manual driving
* Data collection
* Testing
* Autonomous mode switching

### DonkeyCar Web Controller

Successfully configured and tested.

Capabilities:

* Camera streaming
* Steering control
* Throttle control
* Recording control

### DonkeyCar Mobile Application

Successfully connected and tested.

Capabilities:

* Vehicle monitoring
* Vehicle control
* Camera viewing

### Autonomous AI Control

A trained neural network model was deployed to the Raspberry Pi and used for autonomous lane following.

---

## Key Achievements

* Autonomous lane following
* Xbox controller integration
* Bluetooth controller support
* DonkeyCar Web Controller integration
* DonkeyCar Mobile App integration
* VPN-based remote driving architecture
* Windows-based AI training pipeline
* PCA9685 drivetrain integration
* Experimental obstacle avoidance evaluation

---

## Experimental Work

### VL53L0X Time-of-Flight Obstacle Avoidance

A three-sensor obstacle avoidance system was designed and evaluated using VL53L0X ToF sensors and a TCA9548A I2C multiplexer.

The sensors successfully detected nearby objects and were integrated into the DonkeyCar control pipeline.

However, testing revealed false-positive obstacle detections and interference with the autonomous lane-following model.

Following evaluation, the ToF-based approach was removed from the active autonomous stack.

Future work will focus on camera-based obstacle detection using OpenCV and YOLO.

---

## Development Timeline

Phase 1: Manual driving using Xbox controller

Phase 2: Data collection

Phase 3: AI model training

Phase 4: DonkeyCar Web Controller integration

Phase 5: DonkeyCar Mobile App integration

Phase 6: VPN-based remote control

Phase 7: Obstacle avoidance investigation

Phase 8: Future computer vision development

---

## Future Work

* OpenCV obstacle detection
* YOLO object detection
* Sensor fusion
* Remote autonomous operation
* Dynamic path planning
* Safety layer development

---

## Contributors

* Deogratius Nkelejiwa
* Project Collaborator

---

## Acknowledgements

This project was developed within an industrial project environment involving Chipglobe GmbH and Infineon technologies.
