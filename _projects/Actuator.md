---
layout: project
title: Actuator
description: Statics HW "#"12
technologies: [Notes]
image: /assets/images/Screenshot 2025-12-08 225720.png
---


I defined the problem as a simple design that would lay a steel beam on a pin and an actuator attached to the pin such that the beam would flat. My constraints were the size of the bar (1.5 meters long, .5 meters tall) and how many pins I was able to use. The main task of my device was to design a simple actuator machine that would lift a weight as high as possible. Here is the device.

![Shaded rendering of earlier version]({{ "/assets/images/IMG_0005.jpeg" | relative_url }}){: .inline-image-r style="width: 200px"}

Next I was tasked with finding the deflection of a beam that I would choose. In order to solve this problem I used an appendix in the textbook that would describe the deflection of a beam resting upon two pins. Using this formula, I used the cubic weight of steel and its Young's modulus to put the deflection in terms of the cross sectional area of the beam and its moment of inertia. Since all beams found within the chart on A11 fit the constraints of the problem, I selected the beam with the largest I since I had to minimize A/I when I was 8 orders of magnitude stronger than A.This gave me the beam W310x143 oriented along the X axis. I decided that I could ignore the weight on the end of the beam since the deflection caused by that beam would equal zero as indicated by the equation for deflection (Row 5, b=0). Solving for the deflection of the beam using the values in the table, I got a deflection of 2x10^-7 meters of deflection. This value is reasonable because a steel beam would bend minimally under its own weight when spanning a relatively minor distance. The deflection is obviously much less than 2% of the length (3x10^-2) and thusly meets the requirements. Here is the final drawing of the beam and its deflection.

![Shaded rendering of earlier version]({{ "/assets/images/Screenshot 2025-12-08 225734.png" | relative_url }}){: .inline-image-r style="width: 200px"}

Here is some extra work with me brainstorming different methods of solving.

![Shaded rendering of earlier version]({{ "/assets/images/Screenshot 2025-12-08 225703.png" | relative_url }}){: .inline-image-r style="width: 200px"}