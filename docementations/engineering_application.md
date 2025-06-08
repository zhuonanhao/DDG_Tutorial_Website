---
title: "Large-scale engineering applications"
nav_order: 9
parent: Documentation
layout: default
---

# Large-scale engineering applications

### Growth of helical tendrils

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

### Soft magnetic cilia robot

Next, we present a second example to further demonstrate the application of the DDG method in soft robotic engineering. Numerical simulations were conducted to study the locomotion of cilia-inspired programmable magnetic carpet robots using the DDG framework. The simulation model consists of four main components:

1. a magnetic rod model representing the cilia (legs),  
2. a plate model representing the body,  
3. coupling between the cilia and the body through discrete connection elements, and  
4. frictional contact with the ground modeled via an incremental potential energy method.

In the simulations, the robot’s body was modeled as a thin elastic plate, while the cilia were modeled as slender magneto-elastic rods permanently magnetized along a programmed direction. A time-dependent external magnetic field was applied to actuate the cilia, driving the locomotion of the carpet. 

Two representative locomotion modes — **crawling** and **rolling** — were investigated based on previous experimental studies. In crawling, the cilia bend asymmetrically to generate forward motion, while in rolling, the entire body deforms to form a rolling front.

Both crawling and rolling locomotion modes were successfully simulated. A qualitative comparison between simulation results and experimental observations was performed to validate the model, demonstrating good agreement. By tuning parameters such as magnetic field frequency and frictional properties, different locomotion performances were achieved. 

This example illustrates the capability of the DDG framework to model complex soft robotic systems with strong geometric nonlinearity and multi-physics coupling, highlighting its potential for advancing the design and control strategies of next-generation robotic applications.

### Space net capture system

Finally, we present a third example to demonstrate the application of the DDG method in aerospace engineering. The numerical model consists of three main components:

1. dynamic simulation of the elastic net,  
2. contact interaction between the net and the rigid ball, and  
3. sliding coupling between rigid rings and the soft cables that form the net boundary.

The objective here is to emulate the capture and closing mechanism of a net system designed for space debris removal. A rigid spherical object is initially positioned above the elastic net, while the net boundary is formed by tether rods connected through multiple rigid rings. Both the ball-to-net contact and the ring-to-rod sliding interactions are explicitly modeled within the DDG framework.

The overall capture process can be divided into three distinct phases:

1. During **0 s ≤ t < 5 s**, the rigid ball and the elastic net fall under gravity and come into contact.  
2. For **5 s ≤ t < 25 s**, six corner nodes of the net are manually pulled toward the center at a constant speed of **1.0 m/s**, reducing the distance between adjacent corners to less than **5.0 m**.  
3. After **t = 25 s**, the tether rods are stretched outward at **1.0 m/s**, causing the net to close partially due to the constraints imposed by the connecting rings.

This example showcases the ability of the DDG framework to simulate complex space deployable systems involving large deformations, contact, and sliding interactions, demonstrating its potential for future applications in aerospace engineering.


## Examples

- [Case 1: Growth of helical tendrils](../examples/engineering_application_case_1.html)
- [Case 2: Soft magnetic cilia robot](../examples/engineering_application_case_2.html)
- [Case 3: Space net capture system](../examples/engineering_application_case_3.html)
