# AI Autonomous DonkeyCar

## Project Overview

This repository documents the development of an autonomous Raspberry Pi based vehicle using the DonkeyCar framework.

The project was developed in collaboration with a colleague within an industrial project environment involving ChipGlobe GmbH and Infineon technologies.

The objective was to investigate autonomous driving, machine learning deployment, remote vehicle operation, and future computer vision based navigation using low-cost embedded hardware.

---

## Key Features

* Autonomous lane following
* Raspberry Pi camera perception
* PCA9685 steering and throttle control
* Xbox controller integration
* Bluetooth controller support
* DonkeyCar Web Controller
* DonkeyCar Mobile App
* VPN-based remote operation architecture
* Windows-based AI model training
* Experimental obstacle avoidance evaluation
* Future OpenCV and YOLO integration

---

## Vehicle Control Methods

### Xbox Controller

Primary interface used for:

* Manual driving
* Data collection
* Testing
* Autonomous mode switching

### DonkeyCar Web Controller

Successfully configured and tested.

Capabilities:

* Live camera feed
* Steering control
* Throttle control
* Recording management
* Autonomous mode selection

### DonkeyCar Mobile Application

Successfully connected and tested.

Capabilities:

* Vehicle monitoring
* Vehicle control
* Camera viewing

### Autonomous AI Control

A trained neural network model was deployed to the Raspberry Pi and successfully demonstrated autonomous lane following.

---

## Hardware

* Raspberry Pi 4 Model B
* Raspberry Pi Camera
* PCA9685 PWM Controller
* Steering Servo
* ESC
* Xbox Controller
* RC Car Chassis

Additional hardware details are available in:

```text
hardware/bill_of_materials.md
```

---

## Software

* DonkeyCar 5.x
* Python
* TensorFlow
* Raspberry Pi OS
* Git
* OpenCV (Future Work)
* YOLO (Future Work)

---

## Final System Architecture

```text
Pi Camera
      ↓
DonkeyCar AI Model
      ↓
PCA9685
      ↓
Steering + Throttle
```

---

## Development Timeline

### Phase 1

Vehicle assembly and drivetrain calibration

### Phase 2

Xbox controller integration and manual driving

### Phase 3

Data collection and dataset generation

### Phase 4

TensorFlow model training on Windows

### Phase 5

Autonomous lane-following deployment

### Phase 6

DonkeyCar Web Controller integration

### Phase 7

DonkeyCar Mobile App integration

### Phase 8

VPN-based remote operation investigation

### Phase 9

VL53L0X obstacle avoidance evaluation

### Phase 10

Future OpenCV and YOLO development

---

## Experimental Work

### VL53L0X Time-of-Flight Obstacle Avoidance

A three-sensor obstacle avoidance system was designed and evaluated using:

* VL53L0X Time-of-Flight sensors
* TCA9548A I2C multiplexer
* Custom DonkeyCar integration

Testing confirmed successful obstacle detection.

However, the system introduced:

* False-positive detections
* Unwanted steering corrections
* Interference with lane-following behaviour

Following evaluation, the ToF-based approach was removed from the active autonomous driving stack.

Future obstacle avoidance work will focus on computer vision techniques.

---

## Documentation

### Project Overview

```text
docs/project_overview.md
```

### System Architecture

```text
docs/project_architecture.md
```

### Setup Guide

```text
docs/setup.md
```

### Training Pipeline

```text
docs/training_pipeline.md
```

### Remote Control

```text
docs/remote_control.md
```

### Troubleshooting

```text
docs/troubleshooting.md
```

### Experimental ToF Research

```text
docs/experimental_tof_obstacle_avoidance.md
```

---

## Future Work

* OpenCV obstacle detection
* YOLO object detection
* Vision-based navigation
* Dynamic path planning
* Sensor fusion
* Remote autonomous operation

---

## Contributors

* Deogratius Nkelejiwa
* Project Collaborator

---

## Acknowledgements

This project was developed within an industrial project environment involving ChipGlobe GmbH and Infineon technologies.

Special thanks to the DonkeyCar open-source community for providing the framework used throughout development.
