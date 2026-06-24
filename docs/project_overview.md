# Project Overview

## Introduction

This project documents the development of an autonomous vehicle platform based on DonkeyCar and Raspberry Pi technologies.

The project was developed in collaboration with a colleague within an industrial project environment involving Chipglobe GmbH and Infineon technologies.

The objective was to investigate autonomous driving, remote vehicle operation, machine learning deployment, and future computer vision based navigation using low-cost embedded hardware.

---

# Project Goals

The main objectives of the project were:

* Build an autonomous vehicle platform
* Train a neural network for lane following
* Deploy AI models on a Raspberry Pi
* Explore different vehicle control methods
* Investigate remote vehicle operation
* Evaluate obstacle avoidance approaches
* Establish a foundation for future computer vision research

---

# Hardware Platform

The vehicle platform consists of:

* Raspberry Pi 4 Model B
* Raspberry Pi Camera
* PCA9685 PWM Controller
* Steering Servo
* Electronic Speed Controller (ESC)
* Xbox Controller
* DonkeyCar chassis

The Raspberry Pi serves as the main computing platform responsible for data collection, AI inference, camera processing, and vehicle control.

---

# Development Journey

## Phase 1: Manual Vehicle Control

The project began with manual vehicle operation using an Xbox controller.

This phase focused on:

* Vehicle assembly
* Steering calibration
* Throttle calibration
* PCA9685 integration
* Controller integration

The goal was to establish a stable platform for data collection.

---

## Phase 2: Data Collection

Training data was collected by manually driving the vehicle around a test track.

The collected dataset included:

* Camera images
* Steering commands
* Throttle commands

These recordings formed the basis for neural network training.

---

## Phase 3: AI Model Training

Training was performed on a Windows workstation using TensorFlow and DonkeyCar.

Several challenges were encountered during this phase, including:

* TensorFlow installation issues
* Keras compatibility problems
* Python version conflicts
* Training environment configuration

After resolving these issues, multiple lane-following models were successfully trained.

---

## Phase 4: Autonomous Driving

The trained models were deployed to the Raspberry Pi.

The vehicle successfully demonstrated autonomous lane following using the Raspberry Pi camera as its primary perception system.

This represented the first fully autonomous operation of the platform.

---

## Phase 5: Alternative Control Methods

Multiple vehicle control approaches were investigated and successfully integrated.

### Xbox Controller

Used as the primary method for:

* Manual driving
* Data collection
* Testing
* Mode switching

### DonkeyCar Web Controller

The built-in DonkeyCar web interface was successfully configured and tested.

Capabilities included:

* Vehicle control
* Camera monitoring
* Recording management

### DonkeyCar Mobile Application

The DonkeyCar mobile application was successfully connected and tested.

Capabilities included:

* Remote monitoring
* Vehicle control
* Camera viewing

---

## Phase 6: Remote Vehicle Operation

A VPN-based architecture was investigated for remote vehicle operation.

The objective was to allow operators to access and control the vehicle from a different location while maintaining access to vehicle telemetry and camera feeds.

This work established a foundation for future teleoperation and remote autonomous deployment.

---

## Phase 7: Obstacle Avoidance Investigation

A Time-of-Flight based obstacle avoidance system was designed and evaluated.

The prototype used:

* VL53L0X distance sensors
* TCA9548A I2C multiplexer
* Custom DonkeyCar integration

Testing demonstrated successful obstacle detection but also revealed limitations:

* False-positive obstacle detections
* Interference with lane-following behaviour
* Reduced autonomous driving performance

Following evaluation, the sensor-based approach was removed from the active autonomous stack.

This outcome provided valuable insight into the challenges of integrating reactive obstacle avoidance with AI-based navigation systems.

---

# Lessons Learned

Throughout the project, several important engineering challenges were addressed:

* Embedded Linux configuration
* Raspberry Pi integration
* Controller communication
* AI model deployment
* TensorFlow environment management
* Remote networking
* Sensor integration
* Autonomous vehicle testing

The project demonstrated the importance of systematic testing and iterative development when building autonomous systems.

---

# Future Development

Future work will focus on:

* OpenCV-based obstacle detection
* YOLO object detection
* Vision-based navigation
* Sensor fusion
* Advanced path planning
* Remote autonomous operation

The long-term objective is to evolve the platform into a more capable autonomous vehicle capable of operating in increasingly complex environments.
