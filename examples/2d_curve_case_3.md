---
title: "Case 3"
nav_order: 3
parent: Beam
layout: default
---

## [Snapping of a pre-buckled beam](https://github.com/weicheng-huang-mechanics/DDG_Tutorial/tree/main/2d_curve/case_3)

In this case study, we examine the snap-through behavior of a pre-buckled beam under rotational displacement. The beam is clamped at both ends, with one end gradually rotated to induce instability. As the rotation increases, the beam undergoes a sudden transition, driven by the interplay between bending stiffness and applied rotational forces. The case highlights the ability of the DDG model to effectively capture nonlinear snapping behavior in slender structures.

### Simulation Initialization

To initialize the simulation, the following inputs are used:

1. **Geometry and connection:**
   - (i) Nodal positions: the position of the nodes, $$\mathbf{q}(t=0)$$, with a total of $$N=40$$, with the beam length $$L=1.0\mathrm{~m}$$.
   - (ii) Stretching elements: connection of every two consecutive nodes, with a total number of $$N_{s}=39$$.
   - (iii) Bending elements: connection of every two consecutive edges, with a total number of $$N_{b}=38$$.

2. **Physical parameters:**
   - (i) Young's modulus, $$E=10\mathrm{~MPa}$$.
   - (ii) Material density, $$\rho=1000\mathrm{~kg/m^3}$$.
   - (iii) Cross-sectional radius, $$r_{0} = 0.01\mathrm{~m}$$.
   - (iv) Damping viscosity $$\mu = 0.1$$.
   - (v) The overall simulation is dynamic, i.e., $$ \mathrm{ifStatic} = 0$$.

3. **Numerical parameters:**
   - (i) Total simulation time, $$T=20.0\mathrm{~s}$$.
   - (ii) Time step size, $$\mathrm{dt} =0.01 \mathrm{~s}$$.
   - (iii) Numerical force tolerance, $$\mathrm{tol} = 1\times10^{-4}$$.
   - (iv) Maximum iterations, $$N_{\mathrm{iter}}=10$$.

4. **Boundary conditions:**
   - The first two nodes, $$\{\mathbf{x}_{1}, \mathbf{x}_{2} \}$$, and the last two nodes, $$\{\mathbf{x}_{39}, \mathbf{x}_{40} \}$$, are fixed to achieve clamped-clamped boundary conditions, thus $$\mathcal{FIX} = [1,2,3,4,77,78,79,80]^{T}$$.

5. **Initial conditions:**
   - (i) Initial position is input from the nodal positions.
   - (ii) Initial velocity is set to zeros.

6. **Loading steps:**
   - (i) Compression step: when $$t \le 3.0\mathrm{~s}$$, a displacement is applied to both the first two nodes and the last two nodes along the $$X$$-axis with speed $$v_{0} = 0.1\mathrm{~m/s}$$ until the compressive distance reaches the target, $$\Delta x \ge 0.3\mathrm{~m}$$. Note that here we use $$ \mathbf{g}=[0.0,10.0]^T\mathrm{~m/s^2}$$ to induce the bifurcation direction.
   - (ii) Delete Perturbation: when $$3.0 \; \mathrm{s} \le t \le 5.0 \; \mathrm{s}$$, the gravity force is removed to delete the influence of the perturbation, $$ \mathbf{g}=[0.0,0.0]^T\mathrm{~m/s^2}$$.
   - (iii) Rotate left end: the left clamped edge is rotated to induce the snap-through of the bistable beam, the rotational speed is $$\omega = 1.0\mathrm{~rad/s}$$.

### Dynamic Rendering
<br/><img src='../assets/videos/beam_3.gif' width="600">
