# Troubleshooting Guide

## Overview

This document summarizes major issues encountered during development and the solutions that were used to resolve them.

---

# Xbox Controller Issues

## Problem

Controller appeared connected but continued blinking.

## Symptoms

* Bluetooth connection established
* Controller LED continued flashing
* Controller not detected correctly by DonkeyCar

## Investigation

* Bluetooth configuration
* BlueZ settings
* Controller pairing modes
* Raspberry Pi compatibility

## Outcome

Stable operation achieved after controller configuration and testing.

---

# Raspberry Pi Zero 2 Bluetooth Issues

## Problem

Bluetooth pairing inconsistencies when attempting to use Xbox controllers.

## Symptoms

* Pairing failures
* Power-on failures
* Unstable controller detection

## Outcome

Development continued primarily on Raspberry Pi 4 where controller support proved more reliable.

---

# DonkeyCar Web Controller

## Problem

Web interface accessible but vehicle could not be controlled.

## Symptoms

* Browser interface loaded successfully
* Camera feed visible
* Steering and throttle commands ineffective

## Cause

Drivetrain control path not correctly configured.

## Outcome

Web control functionality successfully restored.

---

# DonkeyCar Mobile Application

## Problem

Application connected but vehicle did not respond to commands.

## Investigation

* Network configuration
* Vehicle address configuration
* DonkeyCar control mapping

## Outcome

Application successfully connected and tested.

---

# TensorFlow and Keras Compatibility

## Problem

Training failures caused by incompatible TensorFlow and Keras versions.

## Symptoms

AttributeError: Functional object has no attribute input_names

## Cause

Modern Keras releases introduced compatibility issues with DonkeyCar.

## Outcome

Training environment rebuilt using compatible software versions.

---

# PCA9685 Integration

## Problem

Steering and throttle control required calibration.

## Tasks Performed

* PWM calibration
* Servo center adjustment
* ESC configuration

## Outcome

Stable vehicle control achieved.

---

# Camera Integration

## Problem

Camera configuration and software compatibility issues.

## Investigation

* Picamera configuration
* Camera drivers
* DonkeyCar camera settings

## Outcome

Stable image capture achieved.

---

# VL53L0X Obstacle Avoidance Investigation

## Problem

False-positive obstacle detections interfered with autonomous driving.

## Symptoms

* Unexpected steering corrections
* Vehicle stopping without valid obstacles
* Reduced lane-following performance

## Outcome

Obstacle avoidance system removed from active autonomous stack and documented as experimental research.

---

# Lessons Learned

Major lessons from development:

* Hardware integration is often more challenging than software development.
* Version compatibility is critical for machine learning workflows.
* Testing under realistic conditions is essential.
* Multiple control methods improve development flexibility.
* Experimental features should be evaluated critically before deployment.
