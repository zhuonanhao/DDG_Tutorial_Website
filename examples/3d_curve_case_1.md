---
title: "Case 1"
nav_order: 1
parent: Rod and ribbon
layout: default
---

## [3D helix under gravity](https://github.com/weicheng-huang-mechanics/DDG_Tutorial/tree/main/3d_curve/case_1)

The deformation of a helix rod is a complex mechanical process that has drawn attention from engineers, mathematicians, and computer scientists over the past decade. In this case study, we examine the free oscillation behavior of a slender rod under the influence of gravity. The rod is clamped at one end while the other end remains free, allowing it to deform under its own weight. As gravity acts on the structure, the helix undergoes complex bending and twisting deformations. This case highlights the ability of the DDG model to capture intricate geometric nonlinearities in slender rod structures.

### Simulation Initialization

To initialize the simulation, the following inputs are used:

1. **Geometry and connection:**  
   - (i) Nodal positions: the position of the nodes, $$\mathbf{q}(t=0)$$, for a total number of $$N=50$$ nodes.  
   - (ii) Helical parameters:  helical radius, $$R_h = 0.125$$ m, and helical pitch, $$P_h = 0.234$$ m.  
   - (iii) Stretching elements: connection of every two consecutive nodes, for a total number of $$N_{s}=49$$ stretching elements.  
   - (iv) Bending elements: connection of every two consecutive edges, for a total number of $$N_{b}=48$$ bending elements.  

2. **Physical parameters:**  
   - (i) Young's modulus, $$E=10.0$$ MPa.  
   - (ii) Poisson’s ratio, $$\nu=0.5$$.  
   - (iii) Material density, $$\rho=1000\mathrm{~kg/m^3}$$.  
   - (iv) Cross-sectional radius, $$r_{0}=0.01\mathrm{~m}$$.  
   - (v) Bending stiffness: $$EI_1 = EI_2 = {E \pi r_0^4}/{4}.$$  
   - (vi) Torsional stiffness: $$GJ = {G \pi r_0^4}/{2}.$$  
   - (vii) Damping viscosity, $$\mu = 1.0$$.  
   - (viii) Gravitational field, $$\mathbf{g} = [0.0, 0.0, -10.0]^{T}$$ m/s\(^2\).  
   - (ix) The overall simulation is dynamic, i.e., $$ \mathrm{ifStatic} = 0$$.  

3. **Numerical parameters:**  
   - (i) Total simulation time, $$T=5.0$$ s.  
   - (ii) Time step size, $$\mathrm{d}t=0.01$$ s.  
   - (iii) Numerical force tolerance, $$\mathrm{tol} = 1 \times 10^{-4}.$$  
   - (iv) Maximum iterations, $$N_{\mathrm{iter}}=10$$.  

4. **Boundary conditions:**  
   - The first two nodes $$\{ \mathbf{x}_{1}, \mathbf{x}_{2} \}$$ and the first twisting angle $$\theta_{1}$$ are fixed to achieve clamped-free boundary conditions: $$\mathcal{FIX} = [1,2,3,4,5,6,151]^{T}.$$  

5. **Initial conditions:**  
   - (i) Initial position is input from the nodal positions.  
   - (ii) Initial velocity is set to zeros for all nodes.  

6. **Loading steps:**  
   - External gravitational force is applied to each node throughout the simulation.  

### Dynamic Rendering
<br/><img src='../assets/videos/rod_1.gif' width="600">
