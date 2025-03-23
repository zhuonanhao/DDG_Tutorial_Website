---
title: "Case 2"
nav_order: 2
parent: Soft robotics
layout: default
---

## [Soft swimming robot](https://github.com/weicheng-huang-mechanics/DDG_Tutorial/tree/main/soft_robot/case_2)

In this subsection, we demonstrate the fluid-structure interaction between a soft swimming robot and the surrounding fluid under external magnetic actuation. Using the DDG simulation framework, we analyze how the robotic swimmer responds to time-varying magnetic fields, generating an undulatory motion that propels it through the fluid. The interplay between magnetic forces, elastic deformation, and hydrodynamic resistance shapes the swimming dynamics, highlighting the model’s ability to capture complex coupled interactions. As magnetically actuated soft robots hold great promise for biomedical and underwater applications, this case underscores the potential of our approach in designing and optimizing efficient, adaptive locomotion strategies.

### Simulation Initialization

To initialize the simulation, the following inputs are used:

1. **Geometry and connection:**
   - (i) Nodal positions: the position of the nodes $$\mathbf{q}(t=0)$$, with a total of $$N = 40$$. The robot body is a magnetized beam with a length of $$L = 0.1$$ m.
   - (ii) Stretching elements: the connections between the nodes, with a total of $$N_s = 39$$.
   - (iii) Bending elements: the connections between the edges, with a total of $$N_b = 38$$.

2. **Physical parameters:**
   - (i) Young's modulus, $$E = 0.1$$ MPa.
   - (ii) Material density, $$\rho = 1000$$ $$\mathrm{kg/m^3}$$.
   - (iii) Cross-sectional radius, $$r_0 = 0.001$$ m.
   - (iv) Gravitational field, $$\mathbf{g} = [0.0, 0.0]^T$$ $$\mathrm{m/s^2}$$.
   - (v) Fluid parameters, including fluid density, $$\rho_{0}=1000 $$, normal drag coefficient $$C_{\perp} = 1.0$$ and shear drag coefficient $$C_{\parallel} = 0.01$$.
   - (vi) The beam magnetization is $$B_r^x = 100 \cos(2 \pi s)$$ $$\mathrm{T/m^3}$$, $$B_r^y = 100 \sin(2 \pi s)$$ $$\mathrm{T/m^3}$$, where $$s \in [0,1]$$ is the arc length parameter of the beam.
   - (vii) The overall simulation is dynamic, i.e., $$\mathrm{ifStatic} = 0$$.

3. **Numerical parameters:**
   - (i) Total simulation time, $$T = 5.0$$ s.
   - (ii) Time step size, $$\mathrm{dt} = 0.01$$ s.
   - (iii) Numerical tolerance, $$\mathrm{tol} = 1 \times 10^{-4}$$.
   - (iv) Maximum iterations, $$N_{\mathrm{iter}} = 10$$.

4. **Boundary conditions:**
   - No nodes are constrained in this case, thus the constrained array is $$\mathcal{FIX} = \emptyset$$.

5. **Initial conditions:**
   - (i) Initial position is input from the nodal positions.
   - (ii) Initial velocity is set to zeros for all nodes.

6. **Loading steps:**
   - A magnetic field with $$B_x = A \cos(\omega t)$$ and $$B_y = A \sin(\omega t)$$ (with $$A = 1.0$$ T and $$\omega = 20.0$$ rad/s) is applied to the entire beam.


### Dynamic Rendering
<br/><img src='../assets/videos/robot_2.gif' width="600">
