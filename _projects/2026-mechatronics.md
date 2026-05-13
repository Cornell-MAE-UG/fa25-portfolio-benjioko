---
layout: project
title: Mechatronics Final Robot Project
description: Reflecting on my Heat Transfer Assignment
technologies: [Hand Calculations, Textbook]
image: assets/images/mechatronics cover.jpeg
project_type: coursework
published: true
---
***Group Members***: Dylan Mies and Olivia Tolliver

The goal of the Cube Craze project was to design and build a fully autonomous robot capable of gathering more cubes than an opposing robot within a one-minute match. Our team designed a compact mobile robot using the provided Arduino UNO, modified continuous rotation servos, L9110H H-bridges, QTI sensors, and color sensing components. The robot’s strategy focused on reliability, structural strength, and simple cube collection rather than an overly complex mechanism.

Mechanically, our robot used a lightweight laser-cut body with a cardboard shell designed to create a large perimeter for gathering cubes. Although the shell was made from simple materials, the back structure was especially rigid, which helped the robot resist being pushed by opponents during competition. Electrically, the robot used the required motor drivers and battery setup to power the drive system and sensors. On the software side, the robot was programmed in register-level C to autonomously drive, detect borders, respond to field colors, and move in a pattern intended to collect cubes while staying within the field boundaries.

Throughout the project, our team progressed through the required milestones by first proving basic mobility, then adding sensing and border detection, and finally testing cube collection. The main challenge was tuning the QTI sensors consistently across different fields and lighting conditions. During competition, the robot performed better than expected, winning its first two matches largely because of its sturdy structure. However, later matches revealed weaknesses in sensor consistency and battery-dependent motion control. Overall, the project showed the importance of balancing mechanical robustness, sensor reliability, and repeated testing under realistic competition conditions.

You can view the [project report here]({{ "assets/Mechatronics Robot Competition Final Report.pdf" | relative_url }})!