# Training Pipeline

## Overview

The objective of the training pipeline was to collect driving data, train an AI model, and deploy the trained model to the Raspberry Pi for autonomous lane following.

The complete workflow consisted of:

1. Manual driving and data collection
2. Dataset transfer to a Windows workstation
3. Model training using TensorFlow and DonkeyCar
4. Model deployment to the Raspberry Pi
5. Autonomous vehicle testing

---

# Data Collection

## Objective

Generate training data for lane-following behaviour.

## Method

The vehicle was manually driven around a closed test track using an Xbox controller.

During operation, DonkeyCar recorded:

* Camera images
* Steering commands
* Throttle commands

These recordings were stored in DonkeyCar tubs.

---

# Test Track

The training track consisted of:

* Indoor environment
* Light wooden floor
* White tape lane boundaries
* Circular driving path

Multiple laps were recorded to generate a diverse dataset.

---

# Dataset Transfer

After data collection, the recorded tubs were transferred from the Raspberry Pi to a Windows workstation.

This allowed training to be performed on more powerful hardware.

---

# Training Environment

## Software

* Python
* TensorFlow
* DonkeyCar
* Windows

## Challenges Encountered

Several software issues were encountered:

### TensorFlow Compatibility

Modern TensorFlow and Keras versions introduced compatibility issues with DonkeyCar.

### Python Version Conflicts

Python version mismatches caused installation and execution problems.

### Dependency Issues

Additional package installation and environment management were required.

---

# Model Training

A lane-following model was trained using the collected driving data.

Typical training command:

```bash
python train.py --tubs ./data --model ./models/mypilot.h5 --type linear
```

The objective was to learn the relationship between:

* Camera images
* Steering commands
* Throttle commands

---

# Model Deployment

After training, the model was transferred back to the Raspberry Pi.

Example deployment:

```bash
python manage.py drive --model models/mypilot.h5 --js
```

The Xbox controller remained available for manual override and mode switching.

---

# Autonomous Driving

The trained model successfully demonstrated autonomous lane following.

The Raspberry Pi camera served as the primary perception system.

The vehicle was able to navigate the training track without direct human steering input.

---

# Lessons Learned

Key observations from the training process included:

* Dataset quality is critical
* Consistent driving behaviour improves model performance
* Training environment compatibility is important
* Hardware acceleration significantly reduces training time
* AI models can be sensitive to lighting conditions and track appearance

---

# Future Improvements

* Larger datasets
* Improved track diversity
* Better lighting consistency
* OpenCV integration
* YOLO object detection
* Advanced autonomous navigation
