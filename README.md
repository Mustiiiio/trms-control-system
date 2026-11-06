# Twin Rotor MIMO System — PID and LQR Control

**Modeling, Simulation, and Real-Time Implementation of Classical and Optimal Control Strategies**

A comparative study of **Proportional–Integral–Derivative (PID)** and **Linear Quadratic Regulator (LQR)** control strategies for a Twin Rotor Multi-Input Multi-Output System (TRMS), combining mathematical modeling, MATLAB/Simulink simulation, and experimental implementation on physical hardware.

## Project Overview

The Twin Rotor MIMO System is a nonlinear, coupled, two-degree-of-freedom laboratory platform used to investigate control challenges associated with helicopter-like dynamics.

The system consists of two independently driven DC motors:

- **Main rotor:** Generates thrust to control vertical motion (pitch).
- **Tail rotor:** Generates thrust to control horizontal motion (yaw).

Its dynamics involve aerodynamic nonlinearities, gravitational effects, friction, and cross-coupling between the two rotational axes.

This project investigates the performance of classical PID control and state-space-based LQR control under simulated and real operating conditions.

## Research Objectives

1. Develop a mathematical representation of the TRMS dynamics.
2. Investigate a linearized state-space model suitable for optimal control design.
3. Design and tune PID and LQR controllers.
4. Evaluate both controllers in MATLAB/Simulink.
5. Implement the controllers on the physical TRMS.
6. Compare simulation and experimental performance using time-domain response metrics.
7. Identify the effects of model uncertainty and unmodeled physical dynamics.

## System Description

| Property | Description |
|---|---|
| Platform | Twin Rotor MIMO System |
| Degrees of freedom | 2 |
| Controlled variables | Pitch and yaw angles |
| Actuators | Two DC motors |
| Control strategies | PID and LQR |
| Simulation environment | MATLAB/Simulink |
| Experimental validation | Physical TRMS setup |
| Primary experimental focus | Pitch-axis tracking and stabilization |

## Mathematical Modeling

The nonlinear TRMS model is developed using Newton–Euler formulations, incorporating aerodynamic thrust, gravitational moments, friction, and coupling effects.

The pitch dynamics are represented by:

\[
J_v\ddot{\alpha}_v =
\tau_v-\tau_{vg}-\tau_{vf}-\tau_{v,coup}
\]

The yaw dynamics are represented by:

\[
J_h\ddot{\alpha}_h =
\tau_h-\tau_{hf}-\tau_{h,coup}
\]

For LQR design, a linear state-space representation is considered:

\[
\dot{x}=Ax+Bu
\]

\[
y=Cx+Du
\]

The final controller design uses a seventh-order state-space model based on manufacturer-provided system parameters. Direct experimental identification of this model was not performed as part of the reported study.

## Controller Design

### 1. PID Control

A decentralized PID control approach is considered for regulating the TRMS axes.

The classical PID control law is:

\[
u(t)=K_pe(t)+K_i\int_0^t e(\tau)d\tau+
K_d\frac{de(t)}{dt}
\]

The final tuned parameters reported in the paper are:

| Parameter | Value |
|---|---:|
| \(K_p\) | 0 |
| \(K_i\) | 0.9 |
| \(K_d\) | 0.2 |

The PID controller provides a practical baseline with relatively limited dependence on a detailed plant model.

### 2. Linear Quadratic Regulator (LQR)

LQR is a model-based state-feedback controller designed to minimize the quadratic cost function:

\[
J=\int_0^\infty(x^TQx+u^TRu)\,dt
\]

The control law is:

\[
u=-Kx
\]

The weighting matrices are selected to balance state regulation and control effort.

The paper reports the following feedback gain:

\[
K=
\begin{bmatrix}
-1.777 & 1.000 & 1.018 & 0.219 &
1.323 & 0.703 & 6.427
\end{bmatrix}
\]

This gain is reported for the seventh-order model used in the study.

## Results and Performance Comparison

### Simulation Results

| Performance metric | PID | LQR |
|---|---:|---:|
| Rise time | 4.950 s | 16.306 s |
| Settling time | 7.754 s | >30 s |
| Peak time | 11.820 s | 30.000 s |
| Overshoot | 1.15% | 0% |
| Steady-state error | 0.0002 | 0.0101 |

In simulation, PID demonstrated faster tracking and settling, while LQR exhibited a more heavily damped response without overshoot.

### Real-Time Experimental Results

| Performance metric | PID | LQR |
|---|---:|---:|
| Rise time | 2.84 s | 0.065 s |
| Settling time | 19.40 s | >30 s |
| Overshoot | 0.7% | 38.50% |
| Steady-state error | 0.0272 | 0.0202 |

The experimental results reveal substantial differences between simulated and physical behavior.

**PID** produced a slower initial response than LQR but maintained low overshoot and reached the reported settling criterion.

**LQR** produced an extremely fast initial response but exhibited significant overshoot and sustained oscillations, preventing settling within the experimental observation window.

These results highlight the importance of accurate plant modeling, actuator dynamics, and experimental validation when implementing optimal controllers.

## Key Findings

- Classical PID provided more consistent stabilization performance on the physical system.
- LQR demonstrated significantly faster experimental rise time, but with reduced damping.
- The seventh-order model did not fully predict the physical system's closed-loop response.
- Motor dead zones, actuator delays, aerodynamic effects, and other unmodeled dynamics were identified as possible contributors to the simulation-to-hardware discrepancy.
- Experimental validation was essential for evaluating controller performance beyond idealized simulations.

## Limitations

The study has several important limitations:

- The seventh-order model was adopted from manufacturer documentation rather than directly identified on the experimental apparatus.
- The primary quantitative experimental comparison focuses on pitch-axis tracking.
- The reported LQR response did not settle within the 30-second observation window.
- Quantitative energy-consumption measurements were not provided.
- The effects of cross-axis coupling were discussed, but a complete numerical coupling-rejection comparison was not presented.
- Performance conclusions are specific to the reported models, controller gains, operating conditions, and hardware configuration.

## Future Work

Potential extensions include:

- Experimental system identification and model validation.
- Integral LQR (LQI) for improved steady-state tracking.
- Improved actuator saturation and dead-zone modeling.
- Robust and adaptive control strategies.
- Expanded pitch–yaw coupling experiments.
- Quantitative control-effort and energy measurements.

## Research Paper

**Comparative Analysis of Classical PID and Optimal LQR Control Strategies for a Twin Rotor MIMO System: Simulation and Real-Time Implementation**

**Authors:** Yusuf Selim Şentürk, Ömer Hamza Acar, Mustafa Deri

**Affiliation:** Department of Electrical and Electronics Engineering, İzmir Kâtip Çelebi University, Türkiye.

This repository is based on the six-page research paper and its reported simulation and experimental results.

## Repository Status

Technical documentation is being organized. MATLAB/Simulink models, experimental data, and embedded source files will be added after review and verification.

## Keywords

`TRMS` · `PID` · `LQR` · `MATLAB` · `Simulink` · `Control Systems` · `State-Space Modeling` · `Real-Time Control` · `Robotics` · `Experimental Validation`
