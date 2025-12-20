---
layout: project
title: Thermodynamics System Analysis
description: Turbine Analysis Project
image: /assets/images/cornellhydrogen.jpg
---

<div class="info-box" style="border-left-color: #0077cc; background:#f2f7ff;">
  <h3 style="color: black;">Project Outline</h3>
  <p style="color: black;">In Thermodynamics class, I was tasked with
exploring a specific, real-world device that implements the principles
we had learned in class. I chose the turbine used by Cornell's
hydroelectric power plant that utilizes the motion of water from Beebe
Lake to Fall Creek to generate electricity, resulting in 3 to 5
percent of the University's consumption each year.</p>
</div>

## Overview

![Aerial Image]({{ "/assets/images/cornell_hydro.jpg" |
relative_url }}){: style="width:100%; display:block;" }
Source: [Cornellians](https://nam12.safelinks.protection.outlook.com/?url=https%3A%2F%2Falumni.cornell.edu%2Fcornellians%2Fhydroelectric-plant%2F&data=05%7C02%7Carh258%40cornell.edu%7C4684b8b47d7749fe01fb08de3f7d45a7%7C5d7e43661b9b45cf8e79b14b27df46e1%7C0%7C0%7C639018004459737579%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=EHC2SMie0NRK78FjfSlN%2Bu1X05lcOA0Kb62pz%2B7LGY4%3D&reserved=0)

![Artist's Rendering]({{ "/assets/images/cornell_hydro_drawing.jpg" | relative_url }}){: style="width:100%;
display:block;" }
Source: [Cornell
Facilities](https://nam12.safelinks.protection.outlook.com/?url=https%3A%2F%2Ffcs.cornell.edu%2Fdepartments%2Fenergy-sustainability%2Fdistrict-energy-water%2Fhydroelectric-power&data=05%7C02%7Carh258%40cornell.edu%7C4684b8b47d7749fe01fb08de3f7d45a7%7C5d7e43661b9b45cf8e79b14b27df46e1%7C0%7C0%7C639018004459756750%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=lszH2ae11MWBAlhTsGlsN3QscgriZT6VNguf61zN%2Fgg%3D&reserved=0)

The plant uses two Ossberger cross-flow turbines: we chose to analyze
the second unit listed on the Cornell Facilities page, named the
"Crossflow G1078/20g (2 cell)". In these types of system, water
typically flows in from a body of water and passes through an inlet
guides.
These regulate flow rate and direct the water across the turbine's
blades twice, hence the "cross-flow" name, maximizing the amount of
energy that can be harnessed. Water finally exits on the opposite side
and is free to continue through the waterway.

![Diagram]({{ "/assets/images/ossberger_diagram.png" |
relative_url }}){: style="width:100%; display:block;" }
Source: [Ossberger](https://nam12.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.ossberger.de%2Fen%2Fhydropower-technology%2Fossbergerr-crossflow-turbine&data=05%7C02%7Carh258%40cornell.edu%7C4684b8b47d7749fe01fb08de3f7d45a7%7C5d7e43661b9b45cf8e79b14b27df46e1%7C0%7C0%7C639018004459775894%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=swNnQFF%2BSC5rY12jeSFHEEFkicA67%2FUS5VZ3lEFxMKk%3D&reserved=0)

![Diagram]({{ "/assets/images/turbine_diagram_flow.jpg" |
relative_url }}){: style="width:100%; display:block;" }
Source: [Pump Fundamentals](https://nam12.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.pumpfundamentals.com%2Fimages%2Fossberger.jpg&data=05%7C02%7Carh258%40cornell.edu%7C4684b8b47d7749fe01fb08de3f7d45a7%7C5d7e43661b9b45cf8e79b14b27df46e1%7C0%7C0%7C639018004459793753%7CUnknown%7CTWFpbGZsb3d8eyJFbXB0eU1hcGkiOnRydWUsIlYiOiIwLjAuMDAwMCIsIlAiOiJXaW4zMiIsIkFOIjoiTWFpbCIsIldUIjoyfQ%3D%3D%7C0%7C%7C%7C&sdata=T5Cxp8iq43naQLhG%2BjjKehcnsxxeqNZmhuA5PQ4tAc4%3D&reserved=0)

A benefit of crossflow turbines is that they operate at a variety of
flows adequately and their efficiency remains relatively constant over
a wide range of inputs,
which is ideal for small river applications like this one where flow
is far from constant under the variable weather conditions of Ithaca.

## Analysis
The best analysis for this setup is to model the cross-flow turbine as
a control volume system operating at steady state, as the presence of
running water makes a control model approximation unrealistic.

Entropy balance for a control volume system:

![Diagram]({{ "/assets/images/entropybalance.jpg" |
relative_url }}){: style="width:100%; display:block;" }

For this model, it makes sense to neglect heat transfer, as a turbine
can be reasonably modeled as adiabatic without significantly affecting
its operation, meaning the \(Q\) term can be dropped.

![Diagram]({{ "/assets/images/Screenshot 2025-12-20 153417.jpg" |
relative_url }}){: style="width:100%; display:block;" }

But due to limitations in the coursework I have taken, I am unable to
calculate the relative entropy change of the system, as that would
take considerations of turbulent flow, friction between containing
walls and particles, etc., that I am unable to do. For lack of a
better process, I will stop with this equation here and return after
later semesters for further, more detailed analysis than simply
modeling the system as isentropic with no entropy generation.

Turning to a mass balance for a control volume system:
Under steady state:

![Diagram]({{ "/assets/images/massbalance.jpg" |
relative_url }}){: style="width:100%; display:block;" }



For this model, it again makes sense to neglect heat transfer, as a
turbine can be reasonably modeled as adiabatic without significantly
affecting its operation. Assuming steady state as well, the energy
term on the left can be neglected and mass terms can be combined. Due
to limitations of current coursework, it also makes sense to have the
enthalpy and velocity constant during the process, as it would be
difficult to calculate specific values.

This leaves power equal to the mass flow rate times the difference in
specific potential energy. For a steady state system, mass flow rate
can be found by multiplying volumetric creek flow by water's density.
For this part, I used USGS.gov's automatic measurements of the
discharge of Fall Creek to see how power output changes over the
course of the year with different variable water flow rates.

$$
\dot{W} = \dot{m} \, g \, \Delta z
$$

## Results
USGS provides flow rate in cubic ft per second, for measurements taken
every 3 hours and 15 minutes.

In the code below, I calculate the mass flow rate of the water and
power output of the turbine.
For lack of a better system, I labelled each measurement as an index
of increasing number.
The first data point was taken 12/18/24 at 7:30pm and continue until
12/18 at 3:45pm.
Empty data points (blank spaces in the graph) appear where no data was
unable to be taken--water was frozen.

```matlab
    close all; % file setup

    % importing data from spreadsheet
    opts = detectImportOptions("water flow data fall creek.csv");
    opts.VariableNamesLine = 0;
    opts.VariableNames = ["Water", "Unit"];
    water_flow = readtable("water flow data fall creek.csv", opts);

    % data formatting
    wf = table2array(water_flow(:, "Water"));
    wf = flip(wf); % most recent data points were at top so I flipped

    wf = wf * 0.3048^3; % cfs to cms

    time = 1:2619; %index of times taken, every 3:15 hours:minutes

    % Discharge Plot
    figure;
    plot(time, wf)
    title("Fall Creek Discharge Over Time")
    xlabel("Index")
    ylabel("Volume Flow Rate [cubic meters per second]")

    % Power Calculations
    mf = wf * 1000; % mass flow rate
    dis_speed = 123.5 * 0.3048^3;
    power = mf * (9.81 * 35);
    power = power / 10^6;  % reduce orders of magnitude

    % Power Plot
    figure;
    plot(time, power)
    title("Power Produced Over Time")
    xlabel("Index")
    ylabel("Power [MW]")
```

&nbsp;

<span style="display:block; margin-top:12px;"></span>

Discharge of water over the course of the year:
![Discharge]({{ "/assets/images/graph_one.jpg" |
relative_url }}){: style="width:100%; display:block;" }

Power output:
![Power Output]({{ "/assets/images/graph_two.jpg" |
relative_url }}){: style="width:100%; display:block;" }

&nbsp;

Clearly, power output depends on the volumetric discharge of the river
and has varying power outputs depending on the season and daily
weather.

I worked on this with Andrew Nocily, Audrey Hubbell and Annika Terezakis