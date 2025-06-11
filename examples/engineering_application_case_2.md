---
title: "Case 2"
nav_order: 2
parent: Engineering Application
layout: default
---

## Soft magnetic cilia robot

Next, we present a second example to further demonstrate the application of the DDG method in soft robotic engineering. Numerical simulations were conducted to study the locomotion of cilia-inspired programmable magnetic carpet robots using the DDG framework. The simulation model consists of four main components: (i) a magnetic rod model representing the cilia (legs), (ii) a plate model representing the body, (iii) coupling between the cilia and the body through discrete connection elements, and (iv) frictional contact with the ground modeled via an incremental potential energy method. In the simulations, the robot’s body was modeled as a thin elastic plate, while the cilia were modeled as slender magneto-elastic rods permanently magnetized along a programmed direction. A time-dependent external magnetic field was applied to actuate the cilia, driving the locomotion of the carpet. Two representative locomotion modes — crawling and rolling — were investigated based on previous experimental studies. In crawling, the cilia bend asymmetrically to generate forward motion, while in rolling, the entire body deforms to form a rolling front. Both crawling and rolling locomotion modes were successfully simulated. A qualitative comparison between simulation results and experimental observations was performed to validate the model, demonstrating good agreement. By tuning parameters such as magnetic field frequency and frictional properties, different locomotion performances were achieved. This example illustrates the capability of the DDG framework to model complex soft robotic systems with strong geometric nonlinearity and multi-physics coupling, highlighting its potential for advancing the design and control strategies of next-generation robotic applications.

### Dynamic Rendering
<br/><img src='../assets/videos/application_2.gif' width="600">
