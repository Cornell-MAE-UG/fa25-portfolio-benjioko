---
layout: project
title: Torque Wrench Design Project
description: Mechanics of Materials Final Design Project iterating on and analyzing our Torque Wrench Design in Ansys.
technologies: [Ansys, MATLAB, Fusion 360]
image: /assets/images/materials_final/fillet_deflection.png
published: true
project_type: school
---
**The Prompt**
As a final project for my Materials class, we were taksed with designing a torque wrench with the following dimensions under the following criteria:

- Attain at least 1.0 mV/V output at the rated torque of 600 in-lbf. Higher output increases sensitivity and improves signal-to-noise ratio.
- Safety factor Xo = 4 for yield or brittle failure (choose the appropriate criterion depending on whether the selected material behaves in a brittle or ductile manner).
- Safety factor XK = 2 for crack growth from an assumed initial crack depth of 0.04 in (≈1 mm).
- Fatigue stress safety factor XS = 1.5. The wrench must sustain a fully reversed torque of T = ±600 in-lbf for 10^6 cycles.
- Material must be a steel, aluminum, or titanium alloy.

![Torque wrench sketch]({{ "/assets/images/materials_final/sketch.jpeg" | relative_url }})

**Material Choice**
The baseline material for the project was Steel M42 but we were given the choice to use aluminum, steel, or titanium. I agree with using a steel alloy due to aluminium having low strength and titanium being too costly. Steel M42 could satisfy the material choice for the project, but its high Young’s Modulus and Tensile Strength led to low strain output. Doing my research, I found that the material was too robust to use in a torque wrench and not the material used in industry. I chose to use Steel AISI 4140 oil quenched and tempered at 425 deg celsius due to its prevalence in tools similar to a torque wrench within the industry and the yield strength meeting my estimate of the applied load.

{% include image-row.html img1="/assets/images/materials_final/cad1.png" img2="/assets/images/materials_final/matlab_output.png" side_by_side="true" %}

**Loads, Boundary Conditions, and Deflection Results**
When simplifying the analysis, I modeled the system as a beam in a fixed-free condition with it being fixed at the drive and a load applied at its end. The displacements (or deflections) for the FEM and hand calculations are 0.3108 in and 0.2791 in respectively. Comparing the two, the hand calculations differ by 10.2% which is not too far from each other. The main reason for this, I believe, is the difference in the two systems.

The hand calculations assume a different loading configuration that simply assumes a fixed-free configuration where the fixed end is completely fixed. While in the FEM, we only fix one of the drives (the top one) and not the one connected to the handle. The added 0.1 in of the drive would add onto the moment of inertia term used in the deflection calculations.

{% include image-row.html img1="/assets/images/materials_final/fillet_BC.png" img2="/assets/images/materials_final/fillet_deflection.png" side_by_side="true" %}

**Max Normal Stress Results**
![Torque wrench Stress]({{ "/assets/images/materials_final/fillet_normalstress.png" | relative_url }})

Max stress in the y-direction is 45.37 ksi, 12.9% larger than the max stress calculated by hand. This produces the following factors of safety (FOS):

- FOS against yield: 3.6
- FOS against fatigue: 1.5
- FOS for crack growth: 1.8

The discrepancy highlights a key limitation of beam theory in a geometry like this: although it is accurate for predicting global bending stresses, it cannot represent the sharp gradients and peak stresses that occur in the real 3D geometry. The FEM reveals these local effects, which is why the simulated safety factors are lower.

The FOS requirement could be met by changing the geometry, and using a material with a higher fracture toughness (I used the lower bound for the material in analysis). I also think that beam theory can only get you so far in a problem like this as it looks at the average stress and not the local stress in the drives.

**Strain Gauge Results**
The strain gauge results turned out to be exactly the same as what was calculated (1.2 mV/V), which was really good! Below is how the strain gauge was calculated. A half-bridge gauge with a gauge factor of two was used for simplicity. While a physical gauge wasn’t used in this project, I would pick ATO-SG350-3HA as its .38 x .26 in footprint would fit anywhere on my .45 x .45 in wrench.

{% include image-row.html img1="/assets/images/materials_final/strain.png" img2="/assets/images/materials_final/strain_calcs.jpeg" side_by_side="true" %}