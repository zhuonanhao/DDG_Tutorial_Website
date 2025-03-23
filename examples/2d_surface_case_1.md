---
title: "Case 1"
nav_order: 1
parent: Axisymmetric shell
layout: default
---

## [Inflation of an axisymmetric plate](https://github.com/weicheng-huang-mechanics/DDG_Tutorial/tree/main/2d_surface/case_1)
In this case study, we examine the inflation behavior of an axisymmetric plate under applied pressure. The $$R$$ displacement of the central node is constrained based on the symmetry of deformation, and the node at the right end maintains a pin boundary. As the pressure increases, the plate deforms into a characteristic inflated dome shape. This case highlights the ability of the DDG model to accurately capture axisymmetric deformation and provides insights for modeling hyperelastic materials in future studies.

### Simulation Initialization

To initialize the simulation, the following inputs are used:

1. **Geometry and connection:**
   - (i) Nodal positions: the position of the nodes, $$\mathbf{q}(t=0)$$, for a total number of $$N = 40$$ nodes. The axisymmetric plate is initialized in a flat state with a radius $$R = 1.0 \, \text{m}$$.
   - (ii) Stretching elements: connection of every two consecutive nodes, for a total number of $$N_{s} = 39$$ stretching elements.
   - (iii) Bending elements: connection of every two consecutive edges, for a total number of $$N_{b} = 38$$ bending elements.

2. **Physical parameters:**
   - (i) Young's modulus, $$E = 1.0$$ MPa.
   - (ii) Poisson's ratio, $$\nu = 0.5$$.
   - (iii) Material density, $$\rho = 1000 \, \text{kg/m}^3$$.
   - (iv) Plate thickness, $$h = 0.02 \, \text{m}$$.
   - (v) Damping viscosity, $$\mu = 0.1$$.
   - (vi) The overall simulation is static, i.e., $$ \mathrm{ifStatic} = 1$$.

3. **Numerical parameters:**
   - (i) Total simulation time, $$T = 2.0 \, \text{s}$$.
   - (ii) Time step size, $$\mathrm{dt} = 0.01 \, \text{s}$$.
   - (iii) Numerical tolerance, $$\mathrm{tol} = 1 \times 10^{-4}$$.
   - (iv) Maximum iterations, $$N_{\mathrm{iter}} = 10$$.

4. **Boundary conditions:**
   - The $$R$$ displacement of the central node of the plate is constrained based on the symmetry of deformation, and the node at the right end is constrained for a pin boundary condition. Thus, the constrained array is $$\mathcal{FIX} = [1,79,80]^{T}$$.

5. **Initial conditions:**
   - (i) Initial position is input from the nodal positions.
   - (ii) Initial velocity is set to zeros for all nodes.

6. **Loading steps:**
   - (i) The external pressure is increasing with a loading rate, $$\dot{p} = 10.0$$ kPa/s.


### Dynamic Rendering
<br/><img src='../assets/videos/ashell_1.gif' width="600">
