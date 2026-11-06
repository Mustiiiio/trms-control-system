# 09 — Reproduction Guide

## What is included

- The supplied six-page manuscript in `paper/`.
- All eight embedded manuscript figures extracted as PNGs in `results/figures/`.
- Technical documentation of equations, controller parameters and reported results.

## What is not included

- Executable MATLAB `.m` or Simulink `.slx` project files.
- Physical TRMS firmware, board pinouts or wiring diagram.
- Raw experimental measurements, scripts that compute step-response metrics, or parameter-identification datasets.
- Exact MATLAB release, toolbox versions, solver/sample-time settings and controller deployment configuration.

**Therefore this ZIP is ready to publish as a documented research repository, but is not a turnkey executable reproduction package.**

## Recommended verification workflow once source files are available

1. Match MATLAB model matrices and state ordering to the original tested code.
2. Resolve the LQR input-dimension mismatch before reconstructing `lqr(A,B,Q,R)`.
3. Identify the exact pitch/yaw command channels and controller implementation used for Figures 3–8.
4. Record solver, sample time, actuator limits and reference signal.
5. Export raw timestamped simulation and hardware data.
6. Recompute rise time, settling time, overshoot and steady-state error with documented definitions.
7. Publish validated scripts, hardware wiring and source-code licenses.

No source code has been invented to fill these gaps.
