---
title: "Case 2"
nav_order: 2
parent: Beam
layout: default
---

## [Buckling of a compressive beam](https://github.com/weicheng-huang-mechanics/DDG_Tutorial/tree/main/2d_curve/case_2)

In this case study, we examine the classical Euler buckling phenomenon of a slender beam under axial compression. The beam is fixed at both ends, with a gradually increasing compressive load applied at the right end. As the load increases, the beam transitions from a straight configuration to a buckled state, illustrating the onset of structural instability. The case highlights the ability of the DDG model to accurately capture buckling behavior in slender structures.

### Simulation Initialization

To initialize the simulation, the following inputs are used:

1. **Geometry and connection:**
   - (i) Nodal positions: the position of the nodes, $$\mathbf{q}(t=0)$$, for a total number of $$N=40$$ nodes, with the beam length $$L=1.0\mathrm{~m}$$.
   - (ii) Stretching elements: connection of every two consecutive nodes, for a total number of $$N_{s}=39$$ stretching elements.
   - (iii) Bending elements: connection of every two consecutive edges, for a total number of $$N_{b}=38$$ bending elements.

2. **Physical parameters:**
   - (i) Young's modulus, $$E=10\mathrm{~MPa}$$.
   - (ii) Material density, $$\rho=1000\mathrm{~kg/m^3}$$.
   - (iii) Cross-sectional radius, $$r_{0} = 0.01\mathrm{~m}$$.
   - (iv) Damping viscosity, $$\mu = 0.1$$.
   - (v) Gravitational field, $$ \mathbf{g}= [0.0, 0.0]^{T}\mathrm{~m/s^2}$$.
   - (vi) The overall simulation is static, i.e., $$ \mathrm{ifStatic} = 1$$.

3. **Numerical parameters:**
   - (i) Total simulation time, $$T=10.0$$ s.
   - (ii) Time step size, $$\mathrm{d}t=0.01 \mathrm{~s}$$.
   - (iii) Numerical force tolerance, $$\mathrm{tol} = 1\times10^{-4}$$.
   - (iv) Maximum iterations, $$N_{\mathrm{iter}}=10$$.

4. **Boundary conditions:**
   - The first two nodes and the last two nodes are fixed to achieve clamped-clamped boundary conditions, thus the constrained array, $$\mathcal{FIX} = [1,2,3,4,77,78,79,80]^{T}$$.

5. **Initial conditions:**
   - (i) Initial position is input from the nodal positions.
   - (ii) Initial velocity is set to zeros.

6. **Loading steps:**
   - (i) Perturbation step: A small perturbation to the initial horizontal configuration is created by applying a small gravitational force (with $$ \mathbf{g}=[0.0,0.1]^{T}\mathrm{~m/s^2}$$) when $$t \le 1.0\mathrm{~s}$$.
   - (ii) Compression step: when $$t>1.0$$ s, a displacement is applied to the last two nodes along the negative $$x$$-axis with a speed $$v_{0} = 0.1\mathrm{~m/s}$$, until the compression distance is larger than the target value, $$\Delta x \ge 0.6$$ m.

### Dynamic Rendering
<br/><img src='../assets/videos/beam_2.gif' width="600">