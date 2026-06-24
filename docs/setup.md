# Setup Guide

## Autonomous Model Car Platform

This project is an autonomous model car based on the DonkeyCar framework running on a Raspberry Pi 4. The platform is being developed in collaboration with ChipGlobe GmbH and serves as a research and development platform for autonomous navigation, remote operation, and sensor fusion.

---

# Hardware Components

## Main Computing Unit

* Raspberry Pi 4 Model B
* Raspberry Pi Camera Module V2

## Vehicle Platform

* RC Car Chassis (1:10 Scale)
* Steering Servo
* DC Motor
* Motor Driver

## Sensors

* Raspberry Pi Camera
* Time-of-Flight (ToF) Sensors

## Power

* Vehicle Battery Pack
* Raspberry Pi Power Bank

---

# Software Architecture

The project is based on:

* Raspberry Pi OS (64-bit)
* Python
* DonkeyCar
* OpenCV
* ROS2 (future integration)
* VPN-based remote control system
* Sensor fusion framework

---

# Raspberry Pi Setup

## Install Raspberry Pi OS

Using Raspberry Pi Imager:

1. Select Raspberry Pi 4.
2. Select Raspberry Pi OS (64-bit).
3. Configure:

   * Username
   * Password
   * Hostname
   * Wi-Fi credentials
   * Enable SSH

Flash the SD card and boot the Raspberry Pi.

---

## Update System

```bash
sudo apt update
sudo apt upgrade -y
```

---

## Enable Interfaces

Run:

```bash
sudo raspi-config
```

Enable:

* I2C
* Camera Interface

Expand filesystem if necessary.

Reboot:

```bash
sudo reboot
```

---

# Camera Verification

Verify camera functionality:

```bash
rpicam-hello
```

If camera issues occur:

```bash
sudo apt upgrade python3-libcamera
```

Then reboot.

---

# Python Virtual Environment

Create a dedicated environment:

```bash
python3 -m venv env --system-site-packages
```

Activate:

```bash
source env/bin/activate
```

Optional automatic activation:

```bash
echo "source ~/env/bin/activate" >> ~/.bashrc
source ~/.bashrc
```

---

# DonkeyCar Installation

Install dependencies:

```bash
sudo apt install -y \
libcap-dev \
libhdf5-dev \
libhdf5-serial-dev
```

Install DonkeyCar:

```bash
pip install donkeycar[pi]
```

Verify installation:

```bash
donkey --help
```

---

# Create Vehicle Project

Create the project:

```bash
donkey createcar --path ~/mycar
```

Navigate into the project:

```bash
cd ~/mycar
```

---

# Vehicle Calibration

## Throttle

Run:

```bash
donkey calibrate --pwm-pin PCA9685.1:40.0
```

Determine:

* Maximum Forward PWM
* Neutral PWM
* Maximum Reverse PWM

Update:

```python
THROTTLE_FORWARD_PWM
THROTTLE_STOPPED_PWM
THROTTLE_REVERSE_PWM
```

inside:

```bash
nano ~/mycar/myconfig.py
```

---

## Steering

Run:

```bash
donkey calibrate --pwm-pin PCA9685.1:40.1
```

Determine:

* Full Left PWM
* Full Right PWM

Update:

```python
STEERING_LEFT_PWM
STEERING_RIGHT_PWM
```

inside:

```bash
nano ~/mycar/myconfig.py
```

---

# Manual Driving

Start the vehicle:

```bash
cd ~/mycar
python manage.py drive
```

Open:

```text
http://<raspberry-pi-ip>:8887
```

Features:

* Manual Driving
* Data Recording
* Pilot Mode
* Throttle Adjustment

---

# Data Collection

Record driving sessions for training.

Collected data includes:

* Camera Images
* Steering Commands
* Throttle Commands

The generated dataset will later be used to train autonomous driving models.

---

# Machine Learning Workflow

## Data Collection

Drive manually and record training data.

## Model Training

Train neural networks using collected driving data.

## Inference

Deploy trained models back to the Raspberry Pi for autonomous operation.

---

# Planned Extensions

## Remote Control over VPN

Goals:

* Access vehicle from external networks
* Secure communication
* Remote monitoring and teleoperation

Possible solutions:

* WireGuard
* Tailscale

---

## Sensor Fusion

Current Sensors:

* Pi Camera
* ToF Sensors

Goals:

* Obstacle Detection
* Collision Avoidance
* Improved Environmental Awareness

Fusion Pipeline:

```text
Camera Data
       +
ToF Distance Data
       ↓
Sensor Fusion Layer
       ↓
Decision Making
       ↓
Steering + Throttle Commands
```

---

# Development Tools

## Languages

* Python
* C++
* MATLAB

## Version Control

```bash
git init
git add .
git commit -m "Initial setup"
```

GitHub repository recommended for version tracking and collaboration.

---

# Future Work

* ROS2 integration
* SLAM implementation
* Autonomous navigation
* Object detection
* Path planning
* Multi-sensor perception
* Reinforcement learning experiments

---

# Project Status

Current Phase:

✅ Hardware Assembly

✅ Raspberry Pi Setup

✅ DonkeyCar Installation

✅ Manual Driving

🚧 VPN Remote Control

🚧 Sensor Fusion

🚧 Autonomous Navigation

🚧 Model Training

---

# Collaboration

Developed in collaboration with ChipGlobe GmbH.
