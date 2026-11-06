# 11 — Source traceability and evidence map

This documentation is based on the six-page research paper in `paper/`. Page numbers refer to the PDF pages, not section numbering.

| Claim / artifact | Paper location | Status |
|---|---|---|
| Experimental TRMS platform and pitch/yaw description | pp. 1–2, Fig. 1 | Described in paper |
| Nonlinear equations and physical parameters | p. 2, Eqs. (1)–(9), Table I | Transcribed from paper |
| Seventh-order state-space model | p. 3, Eqs. (10)–(15) | Manufacturer-derived; not identified on this setup |
| PID gains | p. 4, Table II | Reported gains |
| LQR weighting and gain | p. 4, Eqs. (17)–(20) | Reported; dimensional inconsistency requires verification |
| Simulation diagrams and step responses | p. 4, Figs. 3–6 | Extracted from paper |
| Simulation metrics | p. 5, Table III | Reported, not independently recomputed |
| Hardware pitch response figures | p. 5, Figs. 7–8 | Extracted from paper |
| Hardware performance metrics | p. 5, Table IV | Reported, not independently recomputed |
| Coupling, energy and uncertainty discussion | pp. 5–6 | Qualitative discussion; no raw datasets included |

## Important boundaries

- The paper describes a figure titled *System Identification Result* but explicitly says direct identification was not performed on this apparatus (p. 3). Do not present it as a newly identified plant.
- The paper reports `R=[1]` and a 1×7 `K` while showing a 7×2 `B` (pp. 3–4). This is not a reproducible two-input LQR configuration without further clarification.
- The manuscript reports unusually short experimental LQR rise time (0.065 s); preserve the published value without asserting it has been independently validated.
- The paper discusses energy consumption but does not provide a numerical energy table or logged electrical measurements.
