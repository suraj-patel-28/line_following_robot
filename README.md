
---

# Line Following and Parking Robot

This project implements a line-following and parking robot using an Arduino-based Alphabot. The robot is capable of following a line using a PID controller and can also detect parking spots and park autonomously.

## Table of Contents

- [Introduction](#introduction)
- [Features](#features)
- [Project Structure](#project-structure)
- [Hardware Requirements](#hardware-requirements)
- [Software Requirements](#software-requirements)
- [Setup and Installation](#setup-and-installation)
- [How It Works](#how-it-works)
- [Usage](#usage)
- [Contributing](#contributing)
- [License](#license)

## Introduction

This project is designed to control an Alphabot equipped with sensors to follow a line and park itself in designated spots. The main logic is implemented in an Esterel file (`.ept`) for state machine management and an Arduino `.ino` file for sensor reading and motor control.

## Features

- **Line Following:** The robot follows a line using sensor readings and a PID controller to adjust the motor speeds.
- **Parking Detection:** The robot can detect parking spots and execute a parking maneuver.
- **State Machine Control:** The robot's behavior is managed through an automaton defined in the Esterel file, handling different states like idle, turning, parking, and more.

## Project Structure

- **line_follower.ept:** The Esterel file that defines the state machine for controlling the robot.
- **line_follower.ino:** The Arduino file that interfaces with the Alphabot hardware and executes the control logic.
- **alphabot_drivers.h:** Header file containing drivers for controlling the Alphabot's motors and sensors.
- **line_follower.h:** Header file containing function declarations related to the line-following and parking logic.

## Hardware Requirements

- Alphabot platform with the following sensors:
  - 5 IR sensors for line detection
  - 2 IR sensors for parking detection
- Arduino-compatible microcontroller (e.g., Arduino Uno)
- Motor drivers
- Power supply

## Software Requirements

- [Arduino IDE](https://www.arduino.cc/en/software) for compiling and uploading the `.ino` file.
- Esterel compiler or any compatible tool for handling the `.ept` file.

## Setup and Installation

1. **Hardware Setup:**
   - Connect the IR sensors to the appropriate pins on the Alphabot.
   - Connect the motor drivers to the Arduino.
   - Power the Alphabot and ensure all connections are secure.

2. **Software Installation:**
   - Clone this repository:
     ```bash
     git clone https://github.com/yourusername/line-following-parking-robot.git
     ```
   - Open `line_follower.ino` in the Arduino IDE.
   - Upload the code to your Arduino board.

3. **Compiling the Esterel File:**
   - Use an Esterel compiler to process `line_follower.ept` if you need to modify the state machine logic.
   - Integrate the compiled output with the Arduino code if necessary.

## How It Works

- **PID Controller:** The PID (Proportional-Integral-Derivative) controller adjusts the robot's speed based on the difference between the center and the edge sensors.
- **State Machine:** The robot's behavior is managed through states like Idle, Pid, Turnleft, Turnright, Stop, and Parking. Transitions between these states are based on sensor readings.

## Usage

1. Place the robot on a line track with designated parking spots.
2. Power on the robot.
3. The robot will start following the line automatically and will park itself when it detects a parking spot.

## Contributing

Contributions are welcome! Please feel free to submit a pull request or open an issue.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---
