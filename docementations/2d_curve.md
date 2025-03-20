---
title: "Beam"
nav_order: 1
parent: Documentation
layout: default
---

# Beam: planar curve

The beam's nonlinear mechanics, which can be described geometrically as a planar curve, can exhibit large deformation behavior.

Governed by exact geometric curvature rather than linearized approximations, this theory dates back to Euler's elastic theory in the 18th century. Modern applications span compliant robotics, morphing aerospace structures, metamaterials, and bio-inspired systems, with contemporary extensions addressing buckling and snapping behavior.

In this subsection, we start with the simplest planar beam system.

We first introduce the discrete formulation and the associated numerical procedure, followed by three benchmark demonstrations: (i) beam deflection under gravity, (ii) buckling of a compressive beam, and (iii) snap-through of a pre-buckled beam.

![Planar beam model in DDG simulations](Figures/beam_model.pdf)
**Figure:** (a) The beam is discretized into a series of nodes and segments. (b) Each pair of neighboring edges forms a bending element, characterized by a curvature \(\kappa\), which is determined by the turning angle \(\phi\).

### Numerical formulation

As shown in the figure above, the configuration of a planar beam is described by \(N\) nodes, where each node is defined as \(\mathbf{x}_{i} \equiv [x_{i}, y_{i}]^{T} \in \mathcal{R}^{2 \times 1}\). Therefore, the DOF vector can be expressed as:


$$
\mathbf{q} = [ \mathbf{x}_1; \mathbf{x}_2; \ldots; {\mathbf{x}_{N}} ]
$$

\[
\mathbf{q} = \left[ \mathbf{x}_1; \mathbf{x}_2; \ldots; {\mathbf{x}_{N}} \right] \in \mathcal{R}^{2N \times 1}.
\]