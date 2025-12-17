# BV Budget Computing from GFDL CM4X


## Overview

In this task, the suite of the GFDL coupled model (CM), CM4X, is used. The GFDL CM4X simulations are used to compute and store the terms of the Barotropic Vorticity budget following the depth‐integrated Boussinesq‐hydrostatic ocean primitive equations.


In a non-steady state, the following balance holds

$$
\beta \int_{-H}^{\eta} v \, dz
= \frac{1}{\rho_o} J(p_b, H)
- \frac{f Q_m}{\rho_o}
+ f \, \partial_t \eta
- \nabla \wedge \int_{-H}^{\eta} \mathbf{u} \, dz
+ \frac{1}{\rho_o} \nabla \wedge (\boldsymbol{\tau_s - \tau_b})
+ \nabla \wedge \int_{-H}^{\eta} \mathbf{a} \, dz
+ \nabla \wedge \int_{-H}^{\eta} \mathbf{b} \, dz
\tag{1}
$$

$$
\beta V
= \frac{1}{\rho_o} J(p_b, H)
- \frac{f Q_m}{\rho_o}
+ f \, \partial_t \eta
- \nabla \wedge \mathcal{U}_t
+ \frac{1}{\rho_o} \nabla \wedge (\boldsymbol{\tau_s - \tau_b})
+ \nabla \wedge \mathcal{A}
+ \nabla \wedge \mathcal{B}
\tag{2}
$$

$$
0
= - \beta V
+ \frac{1}{\rho_o} J(p_b, H)
- \frac{f Q_m}{\rho_o}
+ f \, \partial_t \eta
- \nabla \wedge \mathcal{U}_t
+ \frac{1}{\rho_o} \nabla \wedge \boldsymbol{\tau_s}
- \frac{1}{\rho_o} \nabla \wedge \boldsymbol{\tau_b}
+ \nabla \wedge \mathcal{A}
+ \nabla \wedge \mathcal{B}
\tag{3}
$$



It is seen that, in addition to boundary stress terms (fifth term on the RHS), bottom pressure torque (first term on the RHS), and nonlinear terms (sixth term on the RHS) do contribute significantly to the overall vorticity balance. Here, we isolate the relative contributions of these terms.

To compute bottom pressure torque, we use the following relation where the terms on the RHS are available as diagnostics:

$$
\frac{1}{\rho_o} J(p_b, H)
= \nabla \wedge \left[
- f \, \hat{\mathbf{z}} \wedge \int_{-H}^{\eta} \mathbf{u} \, dz
- \frac{1}{\rho_o} \int_{-H}^{\eta} \nabla p \, dz
\right]
+ \beta V
+ \frac{f Q_m}{\rho_o}
- f \, \partial_t \eta
\tag{4}
$$


Development of the Bottom Pressure Torque (BPT) term:

$$
\frac{1}{\rho_o} J(p_b, H)
= \nabla \wedge \left[
- f \, \hat{\mathbf{z}} \wedge \int_{-H}^{\eta} \mathbf{u} \, dz
- \frac{1}{\rho_o} \int_{-H}^{\eta} \nabla p \, dz
\right]
+ \beta V
+ \frac{f Q_m}{\rho_o}
- f \, \partial_t \eta
= \frac{1}{\rho_o}
\left[
\hat{\mathbf{z}} \cdot
\left( \nabla p_b \wedge \nabla H \right)
\right]
\tag{5}
$$



where$^{\star}$:
- $p_b$ is the pressure at the bottom,
- $H = h + \eta$ is the water column depth, with $h$ being the distance from the resting ocean surface to the bottom topography, and $\eta$ is the sea surface height (SSH) anomaly.


Schoonover et al. (2016) showed that bottom pressure torque controls the Gulf Stream transport along the western boundary, indicating an essentially inviscid balance. See also Gula et al. (2015) and Le Bras et al. (2019).


## CM4X-p25 Simulations



## CM4X-p125 Simulations
