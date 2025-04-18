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
   - (i) Nodal positions: the position of the nodes, $$\mathbf{q}(t=0)$$, with a total of $$N=40$$, with the beam length $$L=1.0\mathrm{~m}$$.
   - (ii) Stretching elements: connection of every two consecutive nodes, with a total of $$N_{s}=39$$.
   - (iii) Bending elements: connection of every two consecutive edges, with a total of $$N_{b}=38$$.

2. **Physical parameters:**
   - (i) Young's modulus, $$E=10\mathrm{~MPa}$$.
   - (ii) Material density, $$\rho=1000\mathrm{~kg/m^3}$$.
   - (iii) Cross-sectional radius, $$r_{0} = 0.01\mathrm{~m}$$.
   - (iv) Damping viscosity, $$\mu = 0.1$$.
   - (v) Gravitational field, $$ \mathbf{g}= [0.0, 0.1]^{T}\mathrm{~m/s^2}$$.
   - (vi) The overall simulation is static, i.e., $$ \mathrm{ifStatic} = 1$$.

3. **Numerical parameters:**
   - (i) Total simulation time, $$T=10.0\mathrm{~s}$$.
   - (ii) Time step size, $$\mathrm{dt} =0.01 \mathrm{~s}$$.
   - (iii) Numerical force tolerance, $$\mathrm{tol} = 1\times10^{-4}$$.
   - (iv) Maximum iterations, $$N_{\mathrm{iter}}=10$$.

4. **Boundary conditions:**
   - The first two nodes, $$\{\mathbf{x}_{1}, \mathbf{x}_{2} \}$$, and the last two nodes, $$\{\mathbf{x}_{39}, \mathbf{x}_{40} \}$$, are fixed to achieve clamped-clamped boundary conditions, thus $$\mathcal{FIX} = [1,2,3,4,77,78,79,80]^{T}$$.

5. **Initial conditions:**
   - (i) Initial position is input from the nodal positions.
   - (ii) Initial velocity is set to zeros.

6. **Loading steps:**
   - (i) Perturbation step: a small perturbation to the initial horizontal configuration is created by applying a small gravitational force (with $$ \mathbf{g}=[0.0,0.1]^{T}\mathrm{~m/s^2}$$) when $$t \le 1.0\mathrm{~s}$$.
   - (ii) Compression step: when $$t>1.0\mathrm{~s}$$, a displacement is applied to the last two nodes along the negative $$X$$-axis with speed $$v_{0} = 0.1\mathrm{~m/s}$$, until the compression distance is larger than the target value, $$\Delta x \ge 0.6\mathrm{~m}$$.

### Dynamic Rendering
<br/><img src='../assets/videos/beam_2.gif' width="600">
