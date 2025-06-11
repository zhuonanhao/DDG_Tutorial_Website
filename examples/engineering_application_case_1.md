---
title: "Case 1"
nav_order: 1
parent: Engineering Application
layout: default
---

## Growth of helical tendrils

First, we use an example of growing a 1D tendril to show the application of the DDG method in biological engineering, which can be viewed as a simplified case of 3D growing biological tissue in low dimension.

We shows an example of a helical tendril found in nature, which we aim to reproduce using the DDG method. In the context of biological engineering, simulating the growth and coiling behavior of such tendrils can inspire the design of programmable morphing structures and intelligent systems.

To simulate the growth process, we adopt the theory of growing elastic rods in which the geometry of the rod evolves over time through changes in its reference length **l̄** and intrinsic curvature **κ̄₁**, **κ̄₂**, and intrinsic torsion **τ̄**. In particular, the increase in intrinsic curvature is interpreted as an equivalent form of strain mismatch in a bilayer structure, which drives the out-of-plane deformation and coiling behavior of the rod.

We model the time evolution of growth with the following functions:

- **l̄ = l̄(t)**
- **κ̄₁ = κ̄₁(t)**
- **κ̄₂ = κ̄₂(t)**
- **τ̄ = τ̄(t)**

where **l̄(t)** denotes the reference length of the growing tendril, while **κ̄₁(t)** and **κ̄₂(t)** represent the intrinsic curvatures along the **m¹** and **m²** directions, and **τ̄(t)** represents the intrinsic torsion along the **m³** direction; all are functions of time **t**.

The reference length, intrinsic curvatures, and intrinsic torsion are computed from the tendril’s growth trajectory, where the nodal positions are given by:

```
x(t) = 0.1 * t * cos(3t / 4) - π  
y(t) = 0.1 * t * sin(3t / 4)  
z(t) = t - 10π
```

Physically, this model describes a rod that gradually elongates over time due to increasing **l̄**, while the intrinsic curvature **κ̄₁**, **κ̄₂** and intrinsic torsion **τ̄** simultaneously grow and saturate, leading to a sequence of deformations from straight to bent and eventually to coiled configurations.

The simulation results validate the effectiveness of this growth model. By tuning the parameters controlling the growth rate and curvature evolution, a variety of helical tendril shapes can be achieved. This demonstrates the potential of the DDG framework in designing self-morphing structures inspired by natural growth mechanisms.

### Dynamic Rendering
<br/><img src='../assets/videos/application_1.gif' width="600">
