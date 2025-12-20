---
layout: project
title: Thermodynamics System Analysis
description: Turbine Analysis Project
image: /fa25-portfolio-jal564/assets/images/thermo-ec/cornellhydrogen.jpg
---

<div class="info-box" style="border-left-color:#0077cc; background:#f2f7ff;">
  <h3 style="color:black;">Project Outline</h3>
  <p style="color:black;">
    In Thermodynamics class, I was tasked with exploring a specific,
    real-world device that implements the principles we had learned in
    class. I chose the turbine used by Cornell's hydroelectric power
    plant that utilizes the motion of water from Beebe Lake to Fall
    Creek to generate electricity, resulting in 3 to 5 percent of the
    University's consumption each year.
  </p>
</div>

## Overview

![Aerial Image](/fa25-portfolio-jal564/assets/images/thermo-ec/cornell_hydro.jpg)
Source: Cornellians

![Artist's Rendering](/fa25-portfolio-jal564/assets/images/thermo-ec/cornell_hydro_drawing.jpg)
Source: Cornell Facilities

The plant uses two Ossberger cross-flow turbines. We chose to analyze
the second unit listed on the Cornell Facilities page, named the
**Crossflow G1078/20g (2 cell)**.

In these types of systems, water typically flows in from a body of
water and passes through inlet guides. These regulate flow rate and
direct the water across the turbine’s blades twice, hence the
“cross-flow” name, maximizing the amount of energy that can be
harnessed. Water finally exits on the opposite side and continues
through the waterway.

![Ossberger Diagram](/fa25-portfolio-jal564/assets/images/thermo-ec/ossberger_diagram.png)
Source: Ossberger

![Flow Diagram](/fa25-portfolio-jal564/assets/images/thermo-ec/turbine_diagram_flow.jpg)
Source: Pump Fundamentals

A benefit of cross-flow turbines is that they operate adequately at a
variety of flow rates, and their efficiency remains relatively
constant over a wide range of inputs. This is ideal for small river
applications like this one, where flow is far from constant under the
variable weather conditions of Ithaca.

## Analysis

The best analysis for this setup is to model the cross-flow turbine as
a control volume system operating at steady state, as the presence of
running water makes a control mass model unrealistic.

### Entropy Balance (Control Volume)

[ dS_CV / dt  
= Σ(ṁ_in s_in) − Σ(ṁ_out s_out)  
+ Σ(Q̇ / T_b) + σ_gen ]

Under steady state:

[ 0 = ṁ(s_in − s_out) + Σ(Q̇ / T_b) + σ_gen ]

Neglecting heat transfer (adiabatic turbine):

[ 0 = ṁ(s_in − s_out) + σ_gen ]

Due to limitations in current coursework, calculating entropy
generation directly would require modeling turbulent flow, wall
friction, and internal irreversibilities beyond scope. For this
reason, the system is treated as approximately isentropic.

### Mass Balance

Under steady state:

[ Σ ṁ_in = Σ ṁ_out ]

### Energy Balance

[ dE_CV / dt  
= Q̇ − Ẇ  
+ Σ ṁ(h + v²/2 + gz)_in  
− Σ ṁ(h + v²/2 + gz)_out ]

Assuming steady state, negligible heat transfer, and constant
enthalpy and velocity:

[ Ẇ = ṁ g Δz ]

Mass flow rate is calculated from volumetric discharge data provided
by the USGS for Fall Creek.

## Results

USGS provides flow rate measurements in cubic feet per second at
3-hour 15-minute intervals.

Empty data points correspond to periods where measurements were
unavailable due to frozen conditions.

```matlab
close all; % file setup

opts = detectImportOptions("water flow data fall creek.csv");
opts.VariableNamesLine = 0;
opts.VariableNames = ["Water", "Unit"];
water_flow = readtable("water flow data fall creek.csv", opts);

wf = table2array(water_flow(:, "Water"));
wf = flip(wf);

wf = wf * 0.3048^3; % cfs to m^3/s

time = 1:2619;

figure;
plot(time, wf)
title("Fall Creek Discharge Over Time")
xlabel("Index")
ylabel("Volume Flow Rate [m^3/s]")

mf = wf * 1000; % kg/s
power = mf * (9.81 * 35);
power = power / 1e6; % MW

figure;
plot(time, power)
title("Power Produced Over Time")
xlabel("Index")
ylabel("Power [MW]")
