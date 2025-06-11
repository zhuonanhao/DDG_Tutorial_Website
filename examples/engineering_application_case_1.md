---
title: "Case 1"
nav_order: 1
parent: Engineering Application
layout: default
---

## Growth of helical tendrils

First, we use an example of growing a 1D tendril to show the application of the DDG method in biological engineering, which can be viewed as a simplified case of 3D growing biological tissue in a low dimension. We show an example of a helical tendril found in nature, which we aim to reproduce using the DDG method. In the context of biological engineering, simulating the growth and coiling behavior of such tendrils can inspire the design of programmable morphing structures and intelligent systems. To simulate the growth process, we adopt the theory of growing elastic rods in which the geometry of the rod evolves over time through changes in its reference length **\bar{l}** and intrinsic curvature **\bar{\kappa}_{1}**, **\bar{\kappa}_{2}**, and intrinsic torsion **\bar{\tau}**. In particular, the increase in intrinsic curvature is interpreted as an equivalent form of strain mismatch in a bilayer structure, which drives the out-of-plane deformation and coiling behavior of the rod. **\bar{l}=\bar{l}(t)**, **\bar{\kappa}_1 = \bar{\kappa}_1(t)**, **\bar{\kappa}_2 = \bar{\kappa}_2(t)**, **\bar{\tau} = \bar{\tau}(t)**,
where **\bar{l}(t)** denotes the reference length of the growing tendril, while **\bar{\kappa}_1(t)** and **\bar{\kappa}_2(t)** represent the intrinsic curvatures along the **\mathbf{m}^1** and **\mathbf{m}^2** directions, and **\bar{\tau}(t)** represents the intrinsic torsion along the **\mathbf{m}^3** direction; all are functions of time **t**. The reference length, intrinsic curvatures, and intrinsic torsion are computed from the tendril’s growth trajectory, where the nodal positions are given by **\{x(t), y(t), z(t)\} = \{ 0.1{t}\cos\left({3}t/4\right) - \pi, 0.1{t}\sin\left({3}t/4\right), {t} - 10\pi \}**. Physically, this model describes a rod that gradually elongates over time due to increasing **\bar{l}**, while the intrinsic curvature **\kappa_{1}**, **\kappa_{2}** and intrinsic torsion **\tau** simultaneously grow and saturate, leading to a sequence of deformations from straight to bent and eventually to coiled configurations. The simulation results validate the effectiveness of this growth model. By tuning the parameters controlling the growth rate and curvature evolution, a variety of helical tendril shapes can be achieved. This demonstrates the potential of the DDG framework in designing self-morphing structures inspired by natural growth mechanisms.

### Dynamic Rendering
<br/><img src='../assets/videos/application_1.gif' width="600">
