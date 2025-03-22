---
title: "Flexible structures interacting with external environment"
nav_order: 7
parent: Documentation
layout: default
---

# Flexible structures interacting with the external environment


### Magnetic actuation

We first illustrate the dynamic response of a magnetized beam subjected to external magnetic actuation. Using the DDG simulation framework, we analyze how the beam deforms and oscillates in response to time-varying magnetic fields. As magnetically actuated structures are widely explored in soft robotics, biomedical devices, and adaptive materials, this case highlights the potential of our approach in designing and optimizing magneto-mechanical systems for precise and controllable actuation.

Similar to the stretching element, the discrete magnetic force (or torque) is applied based on each magnetized rod segment, defined as

$$
\mathcal{S}: \{\mathbf{x}_{1}, \mathbf{x}_{2} \}.
$$

The local DOF vector is defined as 

$$
\mathbf{q}^{s} \equiv [\mathbf{x}_{1}; \mathbf{x}_{2} ] \in \mathcal{R}^{4 \times 1}.
$$

The local edge length is the $$\mathcal{L}_2$$ norm of the edge vector, defined as

$$
l = || \mathbf{x}_{2} - \mathbf{x}_{1} ||.
$$

We use $$\mathbf{t}$$ and $$\mathbf{n}$$ to denote the local material frame for each rod segment, defined as

$$
    \mathbf{t} = (\mathbf{x}_{2} - \mathbf{x}_{1}) / || \mathbf{x}_{2} - \mathbf{x}_{1} ||, \; \mathrm{and} \; \mathbf{n} \cdot \mathbf{t} = 0.
$$

The discrete format of the magnetic functional for this rod segment is 

$$
E^{\mathrm{mag}} = - \bar{l} \cdot ( {\mathcal{M}} \cdot \mathbf{B} ),
$$

where $$\mathbf{B} \in \mathcal{R}^{2\times1}$$ is the external magnetic field and $${\mathcal{M}} \in \mathcal{R}^{2\times1}$$ is the remanent magnetization density per length, i.e.,

$$
 {\mathcal{M}} = A \left[ \left( \mathbf{t}\otimes \bar{\mathbf{t}} + \mathbf{n} \otimes \bar{\mathbf{n}} \right) \cdot \bar{\mathbf{B}}_{r} \right ].
$$

Here, $$A$$ is the local cross-sectional area, and $$\bar{\mathbf{B}}_{r}$$ is the remanent magnetization density per unit volume of the segment in the reference configuration. Hereafter, we use a bar on top to indicate the evaluation of the undeformed configuration, e.g., $$\bar{l}$$ is the edge length before deformation. The magnetic force vector,  $$\mathbf{F}^{\mathrm{mag}}_{\mathrm{local}}$$, can be derived by finding the gradient of the magnetic potential as

$$
\mathbf{F}^{\mathrm{mag}}_{\mathrm{local}} = -\frac{\partial E^{\mathrm{mag}}}  {\partial \mathbf{q}^{s}}.
$$

The detailed formulation can be found in the MATLAB code. Finally, the global magnetic force vector,  $$\mathbf{F}^{\mathrm{mag}}$$, can be assembled by iterating over all stretching elements.  


### Fluid-structure interaction

Next, we demonstrate the fluid-structure interaction between a soft swimming robot and the surrounding fluid under external magnetic actuation. Using the DDG simulation framework, we analyze how the robotic swimmer responds to time-varying magnetic fields, generating an undulatory motion that propels it through the fluid. The interplay between magnetic forces, elastic deformation, and hydrodynamic resistance shapes the swimming dynamics, highlighting the model’s ability to capture complex coupled interactions. As magnetically actuated soft robots hold great promise for biomedical and underwater applications, this case underscores the potential of our approach in designing and optimizing efficient, adaptive locomotion strategies.

Similar to the stretching element, the discrete drag force is applied based on each rod segment, defined as

$$
\mathcal{S}: \{\mathbf{x}_{1}, \mathbf{x}_{2} \}.
$$

We use $$\mathbf{t}$$ and $$\mathbf{n}$$ to denote the local tangential direction and the local normal direction, defined as

$$
    \mathbf{t} = (\mathbf{x}_{2} - \mathbf{x}_{1}) / || \mathbf{x}_{2} - \mathbf{x}_{1} ||, \; \mathrm{and} \; \mathbf{n} \cdot \mathbf{t} = 0
$$ 

The segment velocity components along the tangential and normal directions are given by

$$
\mathbf{v}_{\parallel} = \left ( \mathbf{v} \cdot \mathbf{t} \right) \cdot \mathbf{t}, \; \mathbf{v}_{\perp} = \left ( \mathbf{v} \cdot \mathbf{n} \right) \cdot \mathbf{n},
$$

where $$\mathbf{v} =  {(\mathbf{v}_{1} + \mathbf{v}_{2})} /{2}$$ is the segment velocity. For most underwater locomotion, the Reynolds number is Intermediate, i.e., $$ 1.0 < Re < 1000.0$$, the local fluid drag force is typically quadratic with the velocity,
$$
(\mathbf{F}_{\mathrm{local}}^{\text{drag}})_{\parallel} = - \frac{1} {2} \rho_{0} C_{\parallel} || \mathbf{v}_{\parallel} ||  \mathbf{v}_{\parallel} , 
$$

$$
(\mathbf{F}_{\mathrm{local}}^{\text{drag}})_{\perp} = - \frac{1} {2} \rho_{0} C_{\perp} || \mathbf{v}_{\perp} ||  \mathbf{v}_{\perp},
$$

where $$\rho_{0}$$ is the density of the water, $$C_{\parallel}$$ and $$C_{\perp}$$ are the drag coefficients. Finally, the global fluid force vector, $$\mathbf{F}^{\text{drag}}$$, is the sum of the local force by iterating over all stretching segments.

### Frictional contact

Finally, we present the frictional contact interaction of a soft crawling robot with multiple legs as it moves across a surface under external magnetic actuation. Using the DDG simulation framework, we analyze how the legs interact with the ground, generating propulsion through controlled frictional forces. The interplay between magnetic excitation, elastic deformation, and contact dynamics determines the robot’s locomotion efficiency and stability. By capturing the complex coupling between actuation and ground interaction, this model provides valuable insights into the design of magnetically controlled soft robots for applications in biomedical engineering, inspection, and search-and-rescue operations.

We use the incremental potential method to model frictional contact between flexible structures and a rigid surface.  Here, the local nodal position is defined as $$\mathbf{x} \equiv [x, y]^T$$, and its velocity as $$\dot{\mathbf{x}} \equiv [\dot{x}, \dot{y}]^T$$. The ground is assumed to have a surface normal $$\mathbf{n}$$. The contact force is applied through each node as

$$
(\mathbf{F}^{\mathrm{con}}_{\mathrm{local}})_{n} =
\begin{cases}
K_{c} \left[ - 2 (d - \hat{d}) \log(  {d} / {\hat{d}}) -  {(d - \hat{d})^2} /{d} \right] \mathbf{n} \; &\mathrm{when} \; 0 < d < \hat{d}, \\
\mathbf{0} \; & \mathrm{when} \; d \geq \hat{d},
\end{cases}
$$

where $$d$$ is the approaching distance between the node and the ground. When the ground is flat with zero height, $$d = y$$. The parameter $$\hat{d}$$ is the barrier parameter, and $$K_{c}$$ denotes the contact stiffness. The tangential frictional force is formulated based on the maximum dissipation principle as

$$
(\mathbf{F}^{\mathrm{con}}_{\mathrm{local}})_{t} =
\begin{cases}
- \mu || (\mathbf{F}^{\mathrm{con}}_{\mathrm{local}})_{n}  || \frac {\mathbf{v}_{t}} {||\mathbf{v}_{t}||} \left(- \frac {||\mathbf{v}_{t}||^2} {\epsilon_{v}^2} +  \frac {||\mathbf{v}_{t}||} {\epsilon_{v}} \right) \; &\mathrm{when} \; 0 < ||\mathbf{v}_{t}|| < \epsilon_{v}, \\
- \mu || (\mathbf{F}^{\mathrm{con}}_{\mathrm{local}})_{n}  || \frac {\mathbf{v}_{t}}  {||\mathbf{v}_{t}||} \; & \mathrm{when} \;  ||\mathbf{v}_{t}|| \geq \epsilon_{v},
\end{cases}
$$

where 

$$
\mathbf{v}_{t} = \mathbf{v} - \mathbf{v} \cdot \mathbf{n}
$$

is the relative velocity along the surface tangential direction, and $$\epsilon_{v}$$ is the velocity parameter. The continuous contact defection must iterate over all nodes for a discrete beam system to build the global contact force vector, $$\mathbf{F}^{\text{con}}$$.


## Examples

- [Case 1: Beam under magnetic actuation](../examples/soft_robot_case_1.html)
- [Case 2: Soft swimming robot](../examples/soft_robot_case_2.html)
- [Case 3: Soft crawling robot](../examples/soft_robot_case_3.html)
