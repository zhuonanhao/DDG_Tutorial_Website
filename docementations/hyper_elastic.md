---
title: "Flexible structures with material nonlinearity"
nav_order: 7
parent: Documentation
layout: default
---

# Flexible structures with material nonlinearity

When the system is stretching-dominated (e.g., cable or membrane), the physical strain is no longer small; thus, a hyperelastic constitutive law is required. Here, we discuss how the DDG method handles the hyperelastic model.

### Hyperelastic planar cable

We first examine a simple planar cable, where, unlike a bending-dominated beam primarily governed by bending energy, the configuration is mainly determined by stretching energy. Also, for sufficient large external loads, the material response may exceed the linear regime, necessitating the use of a hyperelastic model. Similar to the planar beam system, the DOF vector for a hyperelastic cable system is defined by $$N$$ nodes as

$$
\mathbf{q} = [ \mathbf{x}_1; \mathbf{x}_2; \ldots; {\mathbf{x}_{N}} ] \in \mathcal{R}^{2N \times 1},
$$

where only stretching energy is considered, as the strain induced by bending curvature is negligible compared to that from stretching. The stretching element is comprised of two connected nodes, defined as

$$
\mathcal{S}: \{\mathbf{x}_{1}, \mathbf{x}_{2} \}.
$$

The local DOF vector is defined as 

$$
\mathbf{q}^{s} \equiv [\mathbf{x}_{1}; \mathbf{x}_{2} ] \in \mathcal{R}^{4 \times 1}.
$$

The edge length is the $$\mathcal{L}_2$$ norm of the edge vector, defined as

$$
l   =  || \mathbf{x}_{2}  -\mathbf{x}_{1} ||.
$$

The first principal stretch is the uniaxial elongation of edge as

$$
\lambda_{1} =  \frac {  l } {  \bar{l} }.
$$

Hereafter, we use a bar on top to indicate the evaluation of the undeformed configuration, e.g., $$\bar{l}$$ is the edge length before deformation. Due to the incompressible assumption, the other two principal stretches are

$$
\lambda_{2} =  \frac{1} {\sqrt{\lambda_{1}}}, \; \lambda_{3} =  \frac{1} {\sqrt{\lambda_{1}}}.
$$

The strain energy function for an incompressible Mooney-Rivlin material is

$$
E^s = \left[ C_{1} (I_{1} - 3) + C_{2} (I_{2} - 3) \right] \bar{V},
$$

where $$\bar{V}$$ is the volume of the edge segment, $$C_{1}$$ and $$C_{2}$$ are the two material parameters, and $$I_{1}$$ and $$I_{2}$$ are the first and second principal invariant as

$$
I_{1} = \lambda_{1}^2 +\lambda_{2}^2 + \lambda_{3}^2, \; I_{2} = \lambda_{1}^2 \lambda_{2}^2 + \lambda_{1}^2\lambda_{3}^2 + \lambda_{2}^2 \lambda_{3}^2.
$$

The local stretching force vector, $$\mathbf{F}^{s}_{\mathrm{local}} \in \mathcal{R}^{4 \times 1}$$, as well as the local stretching Hessian matrix, $$\mathbb{K}^{s}_{\mathrm{local}} \in \mathcal{R}^{4 \times 4}$$, can be derived through a variational approach as

$$
\mathbf{F}^{s}_{\mathrm{local}} = -\frac{\partial E^{s}}  {\partial \mathbf{q}^{s}}, \; \mathrm{and} \; \mathbb{K}^{s}_{\mathrm{local}} = \frac {\partial^2 E^{s}}  {\partial \mathbf{q}^{s} \partial \mathbf{q}^{s}}.
$$

The detailed formulation can be found in the MATLAB code. Finally, the global stretching force vector,  $$\mathbf{F}^{s}$$, and the associated Hessian matrix, $$\mathbb{K}^{s}$$, can be assembled by iterating over all stretching elements. 


### Hyperelastic axisymmetric membrane

Next,  we examine an axisymmetric membrane, a commonly used hyperelastic structure for soft actuators, to demonstrate the effectiveness of DDG in handling nonlinear hyperelastic constitutive laws. In contrast to the axisymmetric shell, where bending energy dominates, the axisymmetric membrane solely undergoes stretching, as seen in the inflation of a balloon. Moreover, due to the large physical strain, the linear elastic model fails to accurately describe the membrane's inflation, making a hyperelastic model essential. Similar to aan xisymmetric shell system, the DOF vector for a hyperelastic axisymmetric membrane system can be described by $$N$$ nodes,

$$
\mathbf{q} = [ \mathbf{x}_1; \mathbf{x}_2; \ldots; {\mathbf{x}_{N}} ] \in \mathcal{R}^{2N \times 1},
$$

where only stretching energy is considered, as the strain induced by bending curvature is negligible compared to that from stretching. The stretching element is comprised of two connected nodes, defined as

$$
\mathcal{S}: \{\mathbf{x}_{1}, \mathbf{x}_{2} \}.
$$

The local DOF vector is defined as 

$$
\mathbf{q}^{s} \equiv [\mathbf{x}_{1}; \mathbf{x}_{2} ] \in \mathcal{R}^{4 \times 1}.
$$

The edge length is the $$\mathcal{L}_2$$ norm of the edge vector, defined as

$$
l   =  || \mathbf{x}_{2}  -\mathbf{x}_{1} ||.
$$

The local radius is 

$$
r   =  \frac{1}{2} (r_{1} + r_{2}). 
$$

The first principal stretch is the elongation along the meridional direction as

$$
{\lambda}_{1} = \frac {  l} {  \bar{l} }.
$$

Hereafter, we use a bar on top to indicate the evaluation of the undeformed configuration, e.g., $$\bar{l}$$ is the edge length before deformation. The second principal stretch is along the circumferential and is related to the expansion of the circle as

$$
{\lambda}_{2} = \frac { r } { \bar{r} }.
$$

Due to the incompressible assumption, the last principal stretch is

$$
\lambda_{3} =  \frac{1} { \lambda_{1} \lambda_{2} }.
$$

The strain energy density function for an incompressible Mooney-Rivlin material is

$$
E^s = \left[ C_{1} (I_{1} - 3) + C_{2} (I_{2} - 3) \right] \bar{V}.
$$

where $$\bar{V}$$ is the volume of the local membrane element, $$C_{1}$$ and $$C_{2}$$ are the two material parameters, and $$I_{1}$$ and $$I_{2}$$ are the first and second principal invariant as

$$
I_{1} = \lambda_{1}^2 +\lambda_{2}^2 + \lambda_{3}^2, \; I_{2} = \lambda_{1}^2 \lambda_{2}^2 + \lambda_{1}^2\lambda_{3}^2 + \lambda_{2}^2 \lambda_{3}^2.
$$

The local stretching force vector, $$\mathbf{F}^{s}_{\mathrm{local}} \in \mathcal{R}^{4 \times 1}$$, as well as the local stretching Hessian matrix, $$\mathbb{K}^{s}_{\mathrm{local}} \in \mathcal{R}^{4 \times 4}$$, can be derived through a variational approach as

$$
\mathbf{F}^{s}_{\mathrm{local}} = -\frac{\partial E^{s}}  {\partial \mathbf{q}^{s}}, \; \mathrm{and} \; \mathbb{K}^{s}_{\mathrm{local}} = \frac {\partial^2 E^{s}}  {\partial \mathbf{q}^{s} \partial \mathbf{q}^{s}}.
$$

The detailed formulation can be found in the MATLAB code. Finally, the global stretching force vector,  $$\mathbf{F}^{s}$$, and the associated Hessian matrix, $$\mathbb{K}^{s}$$, can be assembled by iterating over all stretching elements.

## Examples

- [Case 1: Hyperelastic cable under vertical loading](../examples/hyper_elastic_case_1.html)
- [Case 2: Snapping of a hyperelastic torus](../examples/hyper_elastic_case_2.html)
