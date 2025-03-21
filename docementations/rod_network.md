---
title: "Net and gridshell: hollow surface"
nav_order: 5
parent: Documentation
layout: default
---

# Net and gridshell: hollow surface


The numerical formulation of net and gridshell structures is straightforward, as the mechanics of the hollow rod network can be captured using rod simulations with appropriately defined input elements. Based on their deformation characteristics, these hollow structures can be categorized into three types:

(i) flexible net -- a network of interconnected 3D rod elements where deformation is limited to stretching while bending and twisting are neglected;

(ii) elastic gridshell -- a network of 3D rod elements that undergo stretching, bending, and twisting. However, the joints between intersecting rods are free to rotate, following a pin-pin boundary condition;

(iii) lattice structure -- similar to the elastic gridshell but with joints capable of transmitting bending and twisting moments, enforcing a clamped-clamped boundary condition.

The primary distinction between (ii) and (iii) in simulation is the inclusion of additional bending and twisting elements at the joints to account for moment and torque transmission.


- [Case 1: Net under gravity](../examples/rod_network_case_1.html)
- [Case 2: Form-finding of gridshell](../examples/rod_network_case_2.html)
- [Case 3: Lattice structure under gravity](../examples/rod_network_case_3.html)
