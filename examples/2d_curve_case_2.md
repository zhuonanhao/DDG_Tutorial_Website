---
title: "Beam buckling"
nav_order: 2
parent: Beam
layout: default
---

## Beam under gravity

In this case study, we examine the free oscillation behavior of a flexible beam under the influence of gravity. The beam is fully constrained at one end, acting as a fixed support, while the other end remains free. Displaced from its initial horizontal position, the beam oscillates due to the restoring elastic forces, with its motion governed by the interplay between elasticity, inertia, and external gravitational force. The case highlights the ability of the DDG model to accurately capture large deformations in beam structures.

### Simulation Initialization

To initialize the simulation, the following inputs are used:

1. **Geometry and connection:**
   - (i) Nodal positions: the position of the nodes, $$\mathbf{q}(t=0)$$, for a total number of $$N=40$$ nodes, with the beam length $$L=1.0\mathrm{~m}$$.
   - (ii) Stretching elements: connection of every two consecutive nodes, for a total number of $$N_{s}=39$$ stretching elements.
   - (iii) Bending elements: connection of every two consecutive edges, for a total number of $$N_{b}=38$$ bending elements.

2. **Physical parameters:**
   - (i) Young's modulus, $$E=100$$ MPa.
   - (ii) Material density, $$\rho=1000\mathrm{~kg/m^3}$$.
   - (iii) Cross-sectional radius, $$r_{0}=0.01\mathrm{~m}$$.
   - (iv) Damping viscosity, $$\mu = 0.1$$.
   - (v) Gravitational field, $$ \mathbf{g}=[0.0, -10.0]^{T}\mathrm{~m/s^2}$$.
   - (vi) The overall simulation is dynamic, i.e., $$ \mathrm{ifStatic} = 0$$.

3. **Numerical parameters:**
   - (i) Total simulation time, $$T=5.0\mathrm{~s}$$.
   - (ii) Time step size, $$\mathrm{d}t=0.01\mathrm{~s}$$.
   - (iii) Numerical force tolerance, $$\mathrm{tol}=1\times 10^{-4}$$.
   - (iv) Maximum iterations, $$N_{\mathrm{iter}}=10$$.

4. **Boundary conditions:**
   - The left tip of the beam is clamped by fixing the first two nodes (starting from the left), thus the constrained DOF-index array is $$\mathcal{FIX} = [1,2,3,4]^T$$.

5. **Initial conditions:**
   - (i) Initial position is input from the nodal positions.
   - (ii) Initial velocity is set to zeros for all nodes.

6. **Loading steps:**
   - External gravitational force is applied to each node throughout the simulation.

### Dynamic Rendering
<br/><img src='../assets/videos/beam_1.gif' width="600">

## Beam buckling 
<br/><img src='../assets/videos/beam_2.gif' width="600">

## Beam snapping 
<br/><img src='../assets/videos/beam_3.gif' width="600">