
# Twin Rotor MIMO System — Experimental Control

### PID | LQR | Sliding Mode Control | Arduino | MATLAB/Simulink

## Overview

This project presents the experimental implementation of multiple control strategies on a real Twin Rotor MIMO System (TRMS).

The objective is to investigate and compare the performance of classical and advanced control algorithms on a nonlinear, coupled electromechanical system.

The project combines MATLAB/Simulink-based control design with Arduino-based hardware interfacing and real-time experimental testing.

## Hardware Platform

- Twin Rotor MIMO System (TRMS)
- Arduino microcontroller
- Rotary encoders for angular position feedback
- PWM-based motor actuation
- Motor driver interface
- PC running MATLAB/Simulink

## System Architecture

The control system follows a closed-loop architecture:

Reference Signal
    |
    v
MATLAB/Simulink Controller
    |
    v
Arduino Hardware Interface
    |
    v
Motor Driver
    |
    v
Physical TRMS
    |
    v
Encoder Feedback
    |
    +----> MATLAB/Simulink Controller

## Implemented Controllers

### 1. PID Control

A proportional-integral-derivative controller was implemented to regulate the TRMS angular position.

### 2. Linear Quadratic Regulator (LQR)

An optimal state-feedback controller was designed using a mathematical model of the TRMS and evaluated experimentally.

### 3. Sliding Mode Control (SMC)

A robust nonlinear control strategy was implemented and tested on the physical system.

## Development Tools

- MATLAB
- Simulink
- Arduino IDE
- Embedded C/C++

## Experimental Evaluation

The project includes real-system testing of the implemented control strategies.

Experimental results will be documented using:

- Reference tracking responses
- Angular position measurements
- Tracking error
- Control signals
- Comparative controller performance

## Project Status

Experimental controller implementations completed.

Source code, Simulink models, hardware documentation, and experimental results are being organized for publication.

## Author

**Mustafa Deri**

Electrical & Electronics Engineering

İzmir Kâtip Çelebi University

[GitHub](https://github.com/Mustiiiio)
