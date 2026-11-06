# 02 — Nonlinear Dynamic Model

*Based on paper Section III.A, equations (1)–(9). Equations below reproduce the paper's stated conventions; they have not been independently validated.*

## Pitch dynamics

$$J_v\ddot{\alpha}_v=\tau_v-\tau_{vg}-\tau_{vf}-\tau_{v,\mathrm{coup}}$$

$$\tau_v=a_1u_v^2+b_1u_v$$

$$\tau_{vg}=M_g\sin(\alpha_v)$$

$$\tau_{vf}=B_{1v}\dot{\alpha}_v+B_{2v}\operatorname{sign}(\dot{\alpha}_v)$$

$$\tau_{v,\mathrm{coup}}=K_{gy}\tau_h\dot{\alpha}_h\cos(\alpha_v)$$

## Yaw dynamics

$$J_h\ddot{\alpha}_h=\tau_h-\tau_{hf}-\tau_{h,\mathrm{coup}}$$

$$\tau_h=a_2u_h^2+b_2u_h$$

$$\tau_{hf}=B_{1h}\dot{\alpha}_h+B_{2h}\operatorname{sign}(\dot{\alpha}_h)$$

The manuscript prints the cross-reaction term as

$$\tau_{h,\mathrm{coup}}=\frac{k_c(a_1u_v^2+b_1u_v)}{J_h}.$$

**Dimensional review needed:** The manuscript calls this a torque, although division by inertia suggests angular-acceleration units. Do not silently substitute a different expression when reproducing the paper; check the original implementation and model derivation before using the equation in executable code.

## Modeling assumptions and limitations

The equations use static quadratic/linear motor-thrust characteristics and simple viscous/Coulomb friction. The experimental comparison indicates that unmodeled dead zones, delays and turbulent airflow may affect closed-loop behavior. The paper does not provide a complete independently verified nonlinear Simulink implementation in the supplied files.
