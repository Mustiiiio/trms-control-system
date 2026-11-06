# 10 — Source Review Notes

## Required before publishing executable implementations

- [ ] Confirm whether the tested TRMS hardware was driven by Arduino, STM32 or another target; the manuscript does not identify it.
- [ ] Obtain original Simulink diagrams (`.slx`) and MATLAB scripts (`.m`).
- [ ] Verify seventh-order state vector and all entries of $A,B,C,D$.
- [ ] Resolve the printed two-input $B$, scalar $R$, one-row $K$ inconsistency.
- [ ] Confirm whether the listed PID gains apply to pitch only or to both axes.
- [ ] Check units and definition of steady-state error in each reported result.
- [ ] Confirm experimental sample time, encoder scaling, motor voltage saturation and filtering.
- [ ] Verify the cross-coupling equation units in paper Eq. (9).
- [ ] Review permissions for manuscript figures and source files.
- [ ] Add reproducible scripts and data only after validation.

## Evidence discipline

Do not describe manufacturer-provided parameters as newly identified data. Do not claim SMC, H∞, LQI, energy savings, or yaw decoupling was experimentally established by the numerical results of this paper. These may be separate projects or future work, but require separate evidence.
