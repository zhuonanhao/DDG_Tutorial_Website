---
title: "Case 1"
nav_order: 1
parent: Hyperelastic structure
layout: default
---

## Hyperelastic planar cable

In this subsection, we examine a simple planar cable, where, unlike a bending-dominated beam primarily governed by bending energy, the configuration is mainly determined by stretching energy. Mathematically, for a 1D structure of length $$L$$, with linear elastic stretching stiffness $$EA$$, bending stiffness $$EI$$, and subjected to an external load $$F$$, a beam model is appropriate when $$EA \gg F \sim EI/L^2$$, whereas a cable model should be used when $$EA \sim F \gg EI/L^2$$. In an intermediate scenario, where $$EA \gg F \gg EI/L^2$$, the configuration of the structure is governed solely by its geometric characteristics and boundary conditions, rendering the problem material-independent — such as an inextensible catenary under its self-weight, which is known as catenary. On the other hand, for sufficiently large external loads, the material response may exceed the linear regime, necessitating the use of a hyperelastic model.

### Simulation Initialization

To initialize the simulation, the following inputs are used:

1. **Geometry and connection:**
   - (i) Nodal positions: the position of the nodes $$\mathbf{q}(t=0)$$, with a total of $$N = 40$$. The length of the cable is set at $$L = 1.0$$ m.
   - (ii) Stretching elements: the connections between the nodes, with a total of $$N_s = 39$$.

2. **Physical parameters:**
   - (i) Young's modulus, $$E = 1.0$$ MPa, $$C_1 = 4E/30$$, and $$C_2 = E/30$$.
   - (ii) Material density, $$\rho = 100.0$$ $$\mathrm{kg/m^3}$$.
   - (iii) Cross-sectional radius, $$r_0 = 0.01$$ m.
   - (iv) Damping viscosity, $$\mu = 1.0$$.
   - (v) Gravity, $$\mathbf{g} = [0.0, 0.0]^T$$ $$\mathrm{m/s^2}$$.
   - (vi) The overall simulation is dynamic, i.e., $$\mathrm{ifStatic} = 0$$.

3. **Numerical parameters:**
   - (i) Total simulation time, $$T = 1.0$$ s.
   - (ii) Time step size, $$\mathrm{dt} = 0.001$$ s.
   - (iii) Numerical tolerance, $$\mathrm{tol} = 1 \times 10^{-4}$$.
   - (iv) Maximum iterations, $$N_{\mathrm{iter}} = 10$$.

4. **Boundary conditions:**
   - The first node and the last node, $$\{ \mathbf{x}_1, \mathbf{x}_{40} \}$$, are fixed to achieve a pin-pin boundary condition, thus the constrained array, $$\mathcal{FIX} = [1, 2, 79, 80]^T$$.

5. **Initial conditions:**
   - (i) Initial position is input from the nodal positions.
   - (ii) Initial velocity is set to zeros.

6. **Loading steps:**
   - The external vertical force is increased at a rate $$\dot{F} = 10$$ N/s.

### Dynamic Rendering
<br/><img src='../assets/videos/hyper_1.gif' width="600">