# Remote Control and Vehicle Operation

## Overview

One of the primary goals of this project was to investigate multiple methods of controlling and operating an autonomous vehicle platform.

Throughout development, several control architectures were implemented, tested, and evaluated.

These ranged from direct local control to remote operation over a VPN connection.

---

# Xbox Controller Integration

## Objective

Provide a reliable manual control interface for:

* Vehicle testing
* Data collection
* Calibration
* Autonomous mode switching

## Implementation

An Xbox controller was connected to the Raspberry Pi and integrated with DonkeyCar's joystick control system.

The controller became the primary interface used throughout development.

## Challenges

Several Bluetooth and controller detection issues were encountered:

* Controller connected but continued blinking
* Bluetooth pairing inconsistencies
* Raspberry Pi Bluetooth configuration issues
* Controller mapping problems
* Device recognition problems

## Outcome

After troubleshooting and configuration adjustments, stable controller operation was achieved and used throughout the project lifecycle.

---

# DonkeyCar Web Controller

## Objective

Evaluate browser-based vehicle control and monitoring.

## Features

The DonkeyCar Web Controller provided:

* Live camera streaming
* Steering control
* Throttle control
* Recording management
* Autonomous mode selection

## Challenges

Initial testing revealed:

* Connection issues
* Network accessibility problems
* Drivetrain control configuration issues

## Outcome

After configuration corrections, the Web Controller successfully provided vehicle control and monitoring capabilities.

---

# DonkeyCar Mobile Application

## Objective

Evaluate mobile device based vehicle operation.

## Features

The DonkeyCar mobile application enabled:

* Vehicle monitoring
* Camera viewing
* Steering and throttle control
* Autonomous mode management

## Challenges

Initial connection attempts failed due to networking and configuration issues.

Further testing and configuration adjustments resulted in successful operation.

## Outcome

The mobile application was successfully connected and demonstrated functional vehicle control capabilities.

---

# Remote Vehicle Operation

## Objective

Enable remote vehicle access from outside the local network.

## Architecture

The project investigated VPN-based remote operation.

Development laptops were connected to the office network through a VPN connection, enabling communication with the vehicle system.

Architecture:

Operator Laptop
↓
VPN Connection
↓
Office Network
↓
Raspberry Pi
↓
Vehicle

## Goals

* Remote monitoring
* Remote control
* Camera access
* Future autonomous deployment

## Outcome

The work established a foundation for future teleoperation and remote autonomous vehicle experiments.

---

# Control Methods Summary

The final platform supported multiple methods of operation:

1. Xbox Controller
2. DonkeyCar Web Controller
3. DonkeyCar Mobile Application
4. Autonomous AI Control

This flexibility allowed the platform to be used for testing, data collection, development, and autonomous operation under different conditions.

---

# Lessons Learned

The evaluation of multiple control methods demonstrated the importance of:

* Reliable communication systems
* Controller compatibility
* Network accessibility
* Robust software configuration
* Flexible control architectures

The project showed that combining manual, web-based, mobile, and autonomous control methods creates a versatile development platform for autonomous vehicle research.
