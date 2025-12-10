---
layout: project
title: North Star Attitude Control
description: This project explores the fundamentals of satellite attitude dynamics by modeling a 3-axis spacecraft in geostationary orbit and developing a closed-loop pointing controller.
technologies: [MATLAB]
image: assets/images/systems_final/definition.png
published: true
---

**North Star — Satellite Attitude Dynamics & Pointing Control**
***Group Members***: Aloyse Maille, Olivia Lee, Ethan Kim

Working with my team, I helped build the system definition, derive the nonlinear equations of motion, create the state-space model, and implement a full MATLAB simulation environment to study stability, performance requirements, and disturbance rejection of a space satellite.

Our goal was to design a controller capable of keeping the satellite pointed at a fixed location on Earth. This involved understanding how inertia properties, rotational dynamics, and solar-pressure disturbances influence attitude behavior, and how active control laws can correct for them.

![Block Diagram]({{ "/assets/images/systems_final/model.png" | relative_url }})
Block Diagram for Satellite angular velocity control with disturbances and with angular position output created by Olivia Lee

**My Contributions**

***State-Space Modeling***
I helped derived and linearized the rotational equations of motion, assembled the state-space representation, and helped structure the block-diagram architecture used for simulation.

***Performance Requirements & Control Strategy***
I researched pointing accuracy standards for GEO satellites and helped define requirements for steady-state error, settling time, maximum overshoot, and allowable angular rate. These specifications guided our proportional-derivative control design.

***MATLAB Simulation & Analysis***
I contributed to the implementation of the full simulation environment, including:
	•	angular rate and pointing angle response
	•	disturbance modeling from solar radiation pressure
	•	step-response and gain-sensitivity studies
	•	Bode-plot analysis of open-loop and closed-loop dynamics

This simulation allowed us to validate controller performance across multiple axes and visualize the satellite’s pointing behavior over its orbit.

**Report & Code**
Feel free to view our project report [here!]({{ "/assets/images/systems_final/North_Star_Attitude_Control.pdf" | relative_url }})

![Orbit Animation]({{ "/assets/images/materials_final/sketch.jpeg" | relative_url }})