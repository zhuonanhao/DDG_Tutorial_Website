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

### Numerical formulation

This is an equation:

$$
\mathbf{q} = [ \mathbf{x}_1; \mathbf{x}_2; \ldots; {\mathbf{x}_{N}} ]
$$
