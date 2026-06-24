# Project Architecture

## Overview

This document describes the architecture of the AI Autonomous DonkeyCar platform and the interaction between its hardware, software, communication, and control subsystems.

The platform was developed to support:

* Manual driving
* Data collection
* AI model training
* Autonomous driving
* Remote operation
* Future computer vision research

---

# High-Level System Architecture

```text
                Xbox Controller
                       │
                       ▼
              DonkeyCar Control
                       │
                       ▼
                Raspberry Pi 4
                       │
        ┌──────────────┼──────────────┐
        ▼              ▼              ▼
   Pi Camera      AI Model      Web Services
        │              │              │
        └──────┬───────┴───────┬──────┘
               ▼               ▼
          Vehicle Logic    Mobile App
               │
               ▼
            PCA9685
               │
        ┌──────┴──────┐
        ▼             ▼
     Steering       ESC
      Servo        Motor
```

---

# Hardware Architecture

## Raspberry Pi

The Raspberry Pi 4 serves as the central processing unit of the vehicle.

Responsibilities:

* Camera acquisition
* Data recording
* AI inference
* Vehicle control
* Network communication
* Controller integration

---

## Pi Camera

The Raspberry Pi Camera acts as the primary perception system.

Responsibilities:

* Image acquisition
* Lane detection through AI model
* Data collection for training

The camera is the primary sensor used during autonomous operation.

---

## PCA9685

The PCA9685 PWM controller generates steering and throttle signals.

Responsibilities:

* Steering PWM generation
* Throttle PWM generation
* Stable servo control

---

## Steering System

The steering servo controls vehicle direction.

Input:

```text
Steering Command
```

Output:

```text
Wheel Angle
```

---

## Drive System

The ESC controls motor speed.

Input:

```text
Throttle Command
```

Output:

```text
Motor Speed
```

---

# Software Architecture

## DonkeyCar Framework

The DonkeyCar framework coordinates all software components.

Responsibilities:

* Data collection
* Training support
* AI inference
* Vehicle operation

---

## Training Pipeline

```text
Manual Driving
      ↓
Data Collection
      ↓
Training Dataset
      ↓
TensorFlow Training
      ↓
Trained Model
      ↓
Deployment
      ↓
Autonomous Driving
```

---

## Autonomous Driving Pipeline

```text
Camera Image
      ↓
Neural Network
      ↓
Steering Prediction
      ↓
Throttle Prediction
      ↓
Vehicle Control
```

---

# Vehicle Control Architecture

Multiple control methods were implemented.

---

## Xbox Controller

Primary development interface.

Functions:

* Manual driving
* Data collection
* Mode switching
* Testing

---

## DonkeyCar Web Controller

Browser-based vehicle control.

Functions:

* Steering
* Throttle
* Camera monitoring
* Recording control

---

## DonkeyCar Mobile Application

Mobile control interface.

Functions:

* Vehicle monitoring
* Camera viewing
* Vehicle control

---

## Autonomous AI Control

Neural network driven operation.

Functions:

* Lane following
* Steering prediction
* Throttle prediction

---

# Remote Operation Architecture

A VPN-based architecture was investigated for remote vehicle operation.

```text
Operator Laptop
       │
       ▼
VPN Connection
       │
       ▼
Office Network
       │
       ▼
Raspberry Pi
       │
       ▼
Vehicle
```

Objectives:

* Remote monitoring
* Remote driving
* Future remote autonomous operation

---

# Experimental Architecture

## Time-of-Flight Obstacle Avoidance

An experimental obstacle avoidance system was evaluated.

Components:

* 3 × VL53L0X sensors
* TCA9548A I2C multiplexer

Architecture:

```text
VL53L0X Sensors
       │
       ▼
Obstacle Logic
       │
       ▼
Steering Override
       │
       ▼
Vehicle Control
```

Testing revealed significant interference with autonomous lane following.

The approach was therefore removed from the active autonomous stack.

---

# Final Active Architecture

The final vehicle configuration used for autonomous driving is:

```text
Pi Camera
      ↓
DonkeyCar AI Model
      ↓
PCA9685
      ↓
Steering + Throttle
```

This architecture provided the most reliable autonomous driving performance during testing.

---

# Future Architecture

Future work will focus on vision-based obstacle detection.

```text
Pi Camera
      ↓
OpenCV / YOLO
      ↓
Obstacle Detection
      ↓
AI Decision Layer
      ↓
Vehicle Control
```

Potential future additions include:

* OpenCV
* YOLO
* Sensor fusion
* Dynamic path planning
* Remote autonomous operation
