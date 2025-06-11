---
title: "Case 3"
nav_order: 3
parent: Engineering Application
layout: default
---

## Space net capture system

Finally, we present a third example to demonstrate the application of the DDG method in aerospace engineering. The numerical model consists of three main components: (i) dynamic simulation of the elastic net, (ii) contact interaction between the net and the rigid ball, and (iii) sliding coupling between rigid rings and the soft cables that form the net boundary. The objective here is to emulate the capture and closing mechanism of a net system designed for space debris removal. A rigid spherical object is initially positioned above the elastic net, while the net boundary is formed by tether rods connected through multiple rigid rings. Both the ball-to-net contact and the ring-to-rod sliding interactions are explicitly modeled within the DDG framework. The overall capture process can be divided into two distinct phases: (i) During **0 s ≤ t < 5 s**, the rigid ball and the elastic net fall under gravity and come into contact. (ii) For **5 s ≤ t < 25 s**, six corner nodes of the net are manually pulled toward the center at a constant speed of **1.0 m/s**, reducing the distance between adjacent corners to less than **5.0 m**. This example showcases the ability of the DDG framework to simulate complex space deployable systems involving large deformations, contact, and sliding interactions, demonstrating its potential for future applications in aerospace engineering.


### Dynamic Rendering
<br/><img src='../assets/videos/application_3.gif' width="600">
