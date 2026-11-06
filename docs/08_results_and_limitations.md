# 08 — Results, Discussion and Limitations

## Overall comparison

| Context | PID | LQR |
|:--|:--|:--|
| Simulation | Fast rise, low overshoot, settles | Slow, overdamped, no overshoot, does not settle in window |
| Hardware | Low overshoot; settles at 19.40 s | Fast rise; 38.50% overshoot; does not settle in window |
| Main engineering trade-off | Simpler baseline, more consistent stabilization in reported test | Strong dependence on accuracy of the state-space model |

## Simulation-to-hardware discrepancy

The reported LQR rise time changes from 16.306 s in simulation to 0.065 s on hardware; overshoot changes from 0% to 38.50%. The paper attributes the discrepancy to possible unmodeled motor dead zones, actuator lags and turbulent aerodynamic effects. These are **hypotheses discussed by the authors**, not separately validated causal estimates.

## Limitations of the evidence

1. **Model provenance:** The seventh-order model was adopted from manufacturer documentation; direct identification on the tested apparatus was not performed.
2. **Experimental scope:** The principal numerical comparison concerns pitch stabilization; the paper does not present a full quantitative two-axis tracking benchmark.
3. **Observation window:** LQR did not settle within the reported 30-second window; `>30 s` is not a measured eventual settling time.
4. **Missing reproducibility assets:** The manuscript does not supply `.slx`/`.m` source files, embedded firmware, original time-series logs, hardware schematics, sampling interval or exact controller deployment steps.
5. **Energy and coupling:** Energy-efficiency and decoupling benefits are discussed, but numerical energy/coupling metrics are absent.
6. **Model dimension ambiguity:** The two-input $B$ matrix, scalar $R$ and one-row $K$ as printed do not establish a reproducible two-input LQR implementation.
7. **Presentation inconsistencies:** Some narrative descriptions of simulation overshoot differ from the numeric table; the paper's Figure 2 caption also uses “System Identification Result” despite the stated lack of direct identification on the apparatus.
8. **No uncertainty estimates:** The performance tables do not provide repetitions, confidence intervals, sensor uncertainty or robustness statistics.

## Next engineering steps

- Validate the model state ordering, actuator channels, and LQR dimensions against original code.
- Repeat hardware step tests with timestamped pitch, yaw, control-input and reference logs.
- Quantify cross-coupling with a defined disturbance protocol.
- Measure electrical power/control effort rather than infer energy savings from smoothness.
- Investigate LQI and model improvements, as proposed in the paper.

These are **proposed future tasks**, not completed experimental results.
