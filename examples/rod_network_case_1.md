---
title: "Case 1"
nav_order: 1
parent: Net and gridshell
layout: default
---

## Flexible net under gravity

Flexible nets are largely used for the capture of objects with irregular shapes, such as tether-net systems that can be considered for space debris capture and removal missions. In this case study, we examine the free oscillation behavior of a flexible net subjected to gravity. The net is modeled with fixed boundary conditions at its vertices, allowing for deformation at the internal nodes. As the gravitational load acts on the net, it undergoes oscillatory motion due to its inherent flexibility. This case highlights the ability of the DDG model to effectively capture the deformation behaviors of the flexible net.

### Simulation Initialization

To initialize the simulation, the following inputs are used:

1. **Geometry and connection:**
   - (i) Nodal positions: the position of the nodes, $$\mathbf{q}(t=0)$$, with a total of $$N = 631$$. The net is initialized as a hexagon with a side length of $$L = 1.0$$ m.
   - (ii) Stretching elements: the connections between the nodes, with a total of $$N_{s} = 720$$.

2. **Physical parameters:**
   - (i) Young's modulus, $$E = 1.0$$ MPa.
   - (ii) Material density, $$\rho = 1000$$ $$\mathrm{kg/m^3}$$.
   - (iii) Cross-sectional radius, $$r_{0} = 0.01$$ m.
   - (iv) Damping viscosity, $$\mu = 0.1$$.
   - (v) Gravity, $$g = [0.0, 0.0, -50]^T$$ $$\mathrm{m/s^2}$$.
   - (vi) The overall simulation is dynamic, i.e., $$\mathrm{ifStatic} = 0$$.

3. **Numerical parameters:**
   - (i) Total simulation time, $$T = 2.0$$ s.
   - (ii) Time step size, $$\mathrm{dt} = 0.01$$ s.
   - (iii) Numerical tolerance, $$\mathrm{tol} = 1 \times 10^{-4}$$.
   - (iv) Maximum iterations, $$N_{\mathrm{iter}} = 10$$.

4. **Boundary conditions:**
   - The six vertices are fixed: $$\{ \mathbf{x}_{2}, \mathbf{x}_{21}, \mathbf{x}_{36}, \mathbf{x}_{51}, \mathbf{x}_{66}, \mathbf{x}_{81} \}$$. Thus, the constrained array, $$\mathcal{FIX}$$, can be constructed accordingly.

5. **Initial conditions:**
   - (i) Initial position is input from the nodal positions.
   - (ii) Initial velocity is set to zeros for all nodes.

6. **Loading steps:**
   - External gravitational force is applied to each node throughout the simulation.


### Dynamic Rendering
<br/><img src='../assets/videos/net_1.gif' width="600">