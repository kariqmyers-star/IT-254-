# AI Enabled Smart Lighting System with YOLO Human Detection

## Overview

This project demonstrates an embedded smart lighting system that combines computer vision, serial communication, and Arduino based hardware control to create an adaptive lighting environment. The system uses YOLO object detection through Python and OpenCV to identify human presence in real time. Detection data is transmitted to an Arduino microcontroller, which then adjusts lighting behavior based on occupancy and ambient light conditions.

Developed for IT 254 at Illinois State University, this project integrates concepts from embedded systems, hardware software communication, pulse width modulation, analog sensing, and basic artificial intelligence.

## Project Objective

The purpose of this system is to create an intelligent lighting controller capable of:

1. Detecting human presence through real time camera based object recognition  
2. Communicating detection results from Python to Arduino via serial connection  
3. Dynamically adjusting LED brightness using ambient light sensor input  
4. Conserving energy by modifying lighting output based on occupancy and environment  

## Technologies Used

### Software
Python  
OpenCV  
Ultralytics YOLOv8  
PySerial  

### Hardware
Arduino Uno  
Photoresistor  
LED  
Breadboard and jumper wires  
USB camera / webcam  

## System Architecture

The system operates through the following pipeline:

1. Python captures live video feed from webcam  
2. YOLOv8 processes each frame and detects humans  
3. Detection result is sent over serial communication to Arduino  
4. Arduino reads ambient light level from photoresistor  
5. Arduino adjusts LED brightness according to human presence and ambient lighting conditions  

## File Structure

### IT 254 DEMO 1.py
Primary Python script for webcam capture, YOLO inference, detection, and serial transmission.

### main.ino.txt
Arduino sketch for serial input processing, ambient light monitoring, and PWM LED control.

### IT 254 CIRCUIT SETUP.jpeg
Circuit diagram and hardware layout for the prototype.

## Installation and Setup

### Python Dependencies
```bash
pip install opencv-python ultralytics pyserial
```

### YOLO Model
Ensure the pretrained YOLOv8 nano model is available:
```python
yolov8n.pt
```

### Serial Port Configuration
Update the COM port in the Python script:
```python
ser = serial.Serial('COM9', 9600)
```

## How to Run

1. Upload Arduino sketch to board  
2. Connect hardware according to circuit diagram  
3. Verify COM port in Python script  
4. Run Python detection script  
5. Stand in front of webcam to trigger lighting response  

## Core Concepts Demonstrated

Pulse Width Modulation  
Analog to Digital Conversion  
Serial Communication  
Embedded Decision Logic  
Sensor Interfacing  
Hardware Software Integration  
Edge Based AI Processing  

## Challenges Encountered

Sensor calibration required for accurate ambient light readings  
Serial synchronization between Python and Arduino required timing adjustments  
YOLO inference latency affected response timing  
Ambient lighting variation impacted threshold tuning  

## Future Improvements

Multi room smart lighting support  
Bluetooth or WiFi remote control integration  
Behavioral learning for predictive lighting patterns  
Mobile dashboard for monitoring system status  

## Authors

Kariq Myers  
Daniel Edet  
Marcus Nguyen  
Noah Adams  

## Course Information

IT 254 Hardware and Software  
Illinois State University  
Professor Dr. Meenal Chaudhari
