---
title: "Case 2"
nav_order: 2
parent: Plate and shell
layout: default
---

## [Plate wrinkling under gravity](https://github.com/weicheng-huang-mechanics/DDG_Tutorial/tree/main/3d_surface/case_2)


Unlike the simple deflection case, this example introduces the phenomenon of wrinkling, a manifestation of instability in thin structures under compression. In this case study, we examine the wrinkling behavior of a plate subjected to gravity. The plate is modeled with two fixed boundary corners. As the plate deforms under the gravitational load, wrinkles develop due to instability in the structure. This case highlights the ability of the DDG model to accurately capture the complex deformation pattern of wrinkling.

### Simulation Initialization

To initialize the simulation, the following inputs are used:

1. **Geometry and connection:**
   - (i) Nodal positions: the position of the nodes, $$\mathbf{q}(t=0)$$, with a total number of $$N=644$$. The plate length is $$L=1.0\mathrm{~m}$$ and width $$W=0.5$$.
   - (ii) Stretching elements: connection of every two consecutive nodes, for a total number of $$N_{s}=1821$$ stretching elements.
   - (iii) Triangular mesh, total number $$N_{t}=1178$$.
   - (iv) Bending elements: connection of every two triangular meshes, for a total number of $$N_{b}=1713$$ bending elements.

2. **Physical parameters:**
   - (i) Young's modulus, $$E=0.1$$ MPa.
   - (ii) Material density, $$\rho=1000\mathrm{~kg/m^3}$$.
   - (iii) Plate thickness, $$h = 0.001$$ m.
   - (iv) Gravitational field, $$ \mathbf{g}=[1.0, 1.0, -30.0]^T \mathrm{~m/s^2}$$.
   - (v) Damping viscosity, $$\mu = 0.01$$.
   - (vi) The overall simulation is dynamic, i.e., $$ \mathrm{ifStatic} = 0$$.

3. **Numerical parameters:**
   - (i) Total simulation time, $$T=5.0$$ s.
   - (ii) Time step size, $$\mathrm{d}t=0.01$$ s.
   - (iii) Numerical tolerance, $$\mathrm{tol} = 1 \times 10^{-4}$$.
   - (iv) Maximum iterations, $$N_{\mathrm{iter}} = 10$$.

4. **Boundary conditions:**
   - The two corner nodes, $$\{\mathbf x_{17}, \mathbf x_{644}\}$$, are fixed; thus, the constrained array, $$\mathcal{FIX}$$, can be constructed accordingly.

5. **Initial conditions:**
   - (i) Initial position is input from the nodal positions.
   - (ii) Initial velocity is set to zeros for all nodes.

6. **Loading steps:**
   - External gravitational force is applied to each node throughout the simulation.


### Dynamic Rendering
<br/><img src='../assets/videos/plate_2.gif' width="600">