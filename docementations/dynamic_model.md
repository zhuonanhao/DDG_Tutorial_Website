---
title: "General structure dynamics"
nav_order: 1
parent: Documentation
layout: default
---

# General structure dynamics

We use a generalized degree of freedom (DOF) vector, $$\mathbf{q} \in \mathcal{R}^{N \times 1}$$, to formulate the structural dynamic equations based on Newton's second law,

$$
\mathbb{M} \ddot{\mathbf{q}}(t) + \mathbb{C} \dot{\mathbf{q}}(t) + \mathbb{K} \mathbf{q}(t) = \mathbf{F}^{\mathrm{ext}}(t),
$$

where $$\mathbb{M} \in \mathcal{R}^{N \times N} $$ the mass matrix, $$\mathbb{C} \in \mathcal{R}^{N \times N} $$ the damping matrix, $$\mathbb{K} \in \mathcal{R}^{N \times N} $$ the tangential stiffness matrix, and $$\mathbf{F}^{\mathrm{ext}} \in \mathcal{R}^{N \times 1}$$ the external force vector. We will use $$\dot{()}$$ to represent the derivative with respect to time, i.e., $$\dot{\mathbf{q}}$$ is the generalized velocity vector, and $$\ddot{\mathbf{q}}$$ is the generalized acceleration vector. The above dynamic equations of motion can be solved with given initial conditions, $$\mathbf{q}(t=0)$$ and $$\dot{\mathbf{q}}(t=0)$$, as well as the boundary conditions. Also, it should be noted that the mass matrix, damping matrix, stiffness matrix, and external force vector, may not be a constant and could vary as a function of DOF vector, $$\mathbf{q}(t)$$, which is known as the nonlinearity. For example, the mass matrix would change for rocket launch, the damping matrix would change for viscoelastic material, and the tangential stiffness matrix would change for large deformations, which is one of the key challenges for the understanding of flexible structure mechanics, e.g., rods and shells. In that case, we usually introduce the total elastic energy, $$\mathcal{V}$$, and find the local force vector and tangential stiffness matrix through a variational approach,

$$
\mathbf{F}^{\text{int}} = - \frac {\partial \mathcal{V} } {\partial \mathbf{q}}, \; \mathrm{and} \;
\mathbb{K} = \frac {\partial^2 \mathcal{V}} {\partial \mathbf{q}^2},
$$

where $$\mathcal{V}$$ is the total elastic energy of the system and $$\mathbf{F}^{\text{int}}$$ the internal elastic force. The key challenge for flexible structural dynamics is to formulate its total potential energy and find its first and second variations used in equations of motion, for which we will give detailed formulae for different types of structure.

Next, to solve the nonlinear dynamic equations of motion, the most straightforward way is the implicit Euler method, for its computational efficiency and numerical robustness. Specifically, the DOF vector $$\mathbf q$$, as well as its velocity $$\dot{\mathbf q}$$, can be updated from the current time step $$ t_{k} $$ to the next time step $$ t_{k+1}$$ by using the following rules,

$$
\mathbf{q}(t_{k+1}) =  \mathbf{q}(t_{k}) +  \dot{\mathbf{q}}(t_{k+1}) \mathrm{dt},
$$

$$
\dot{\mathbf{q}}(t_{k+1}) = \dot{\mathbf{q}}(t_{k}) + \ddot{\mathbf{q}}(t_{k+1}) \mathrm{dt}, 
$$

where $$\mathrm{dt}$$ is the time step size. Thus, the $$N$$-sized continuous equation of motions in Eq.~(\ref{eq:dynamicEquation}) can be discretized and numerically solved step by step

$$
\mathcal{E} \equiv \mathbb{M} \ddot{\mathbf{q}}(t_{k+1}) + \mathbb{C} \dot{\mathbf{q}}(t_{k+1}) - \mathbf{F}^{\text{int}}(t_{k+1}) - \mathbf{F}^{\text{ext}}(t_{k+1}) = \mathbf{0}.
$$

The Jacobian can be expressed as

$$
\mathbb{J} = \frac {\mathbb{M}} {\mathrm{dt}^2} +  \frac {\mathbb{C}} {\mathrm{dt}} + \mathbb{K} - \frac{\partial \mathbf{F}^{\text{ext}}} {\partial \mathbf{q}}.
$$

To solve the nonlinear discrete equations of motion, the iterative Newton-Raphson method is employed. At the time step $$t_{k+1}$$, a new solution is first guessed on the basis of the previous state, i.e.,

$$
\mathbf{q}_{n}(t_{k+1}) = \mathbf{q}(t_{k}) + \mathrm{dt} \; \dot{\mathbf{q}}(t_{k}).
$$

Then, it is optimized utilizing the gradient descent principle, such that the new solution at the $$(n+1)$$-th step is

$$
\mathbf{q}_{n+1}(t_{k+1}) = \mathbf{q}_{n}(t_{k+1}) - \mathbb{J}_{n} \backslash \mathcal{E}_{n}.
$$

We will update the time step and move forward until the numerical error is smaller than the tolerance, 

$$
|| \mathcal{E}_{n}|| < \mathrm{tol}.
$$

It is worth noting that this framework is for dynamic simulation, and the static solution can be easily derived through the dynamic relaxation method \cite{barnes1999form, han2003study}; also, if the inertia and damping terms are ignored, the simulation can provide a static result by increasing the loading step by step, i.e., 

$$
\mathbb{K} \mathbf{q}(t_{k+1}) = \mathbf{F}^{\text{ext}}(t_{k+1})
$$
which is known as numerical continuation.
