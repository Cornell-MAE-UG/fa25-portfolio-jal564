---
layout: default
title: Thermodynamics System Analysis
description: Turbine Analysis Project
image: /assets/images/thermo-ec/cornellhydrogen.jpg
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

<img src="/fa25-portfolio-jal564/assets/images/thermo-ec/cornell_hydro.jpg" 
     alt="Aerial Image" style="width:100%; display:block;">
<p><strong>Source:</strong> Cornellians</p>

<img src="/fa25-portfolio-jal564/assets/images/thermo-ec/cornell_hydro_drawing.jpg" 
     alt="Artist's Rendering" style="width:100%; display:block;">
<p><strong>Source:</strong> Cornell Facilities</p>

The plant uses two Ossberger cross-flow turbines. We chose to analyze the second unit listed on the Cornell Facilities page, named the **Crossflow G1078/20g (2 cell)**.  

In these types of systems, water typically flows in from a body of water and passes through inlet guides. These regulate flow rate and direct the water across the turbine’s blades twice, hence the **“cross-flow”** name, maximizing the amount of energy that can be harnessed. Water finally exits on the opposite side and continues through the waterway.

<img src="/fa25-portfolio-jal564/assets/images/thermo-ec/ossberger_diagram.png" 
     alt="Ossberger Diagram" style="width:100%; display:block;">
<p><strong>Source:</strong> Ossberger</p>

<img src="/fa25-portfolio-jal564/assets/images/thermo-ec/turbine_diagram_flow.jpg" 
     alt="Flow Diagram" style="width:100%; display:block;">
<p><strong>Source:</strong> Pump Fundamentals</p>

A benefit of cross-flow turbines is that they operate adequately at a variety of flow rates, and their efficiency remains relatively constant over a wide range of inputs. This is ideal for small river applications like this one, where flow is far from constant under the variable weather conditions of Ithaca.

## Analysis

The best analysis for this setup is to model the cross-flow turbine as a control volume system operating at steady state, as the presence of running water makes a control mass model unrealistic.

### Entropy Balance (Control Volume)

\[
\frac{dS_{CV}}{dt} = \sum_\text{in} \dot{m}_\text{in} s_\text{in} - \sum_\text{out} \dot{m}_\text{out} s_\text{out} + \sum_k \frac{\dot{Q}}{T_b} + \sigma_\text{gen}
\]

Under steady state:

\[
0 = \dot{m}(s_\text{in} - s_\text{out}) + \sum_k \frac{\dot{Q}}{T_b} + \sigma_\text{gen}
\]

Neglecting heat transfer (adiabatic turbine):

\[
0 = \dot{m}(s_\text{in} - s_\text{out}) + \sigma_\text{gen}
\]

Due to limitations in current coursework, calculating entropy generation directly would require modeling turbulent flow, wall friction, and internal irreversibilities beyond scope. For this reason, the system is treated as approximately **isentropic**.

### Mass Balance

Under steady state:

\[
\sum_\text{in} \dot{m}_\text{in} = \sum_\text{out} \dot{m}_\text{out}
\]

### Energy Balance

\[
\frac{dE_{CV}}{dt} = \dot{Q} - \dot{W} + \sum_\text{in} \dot{m}_\text{in} \left(h + \frac{v^2}{2} + gz\right) - \sum_\text{out} \dot{m}_\text{out} \left(h + \frac{v^2}{2} + gz\right)
\]

Assuming steady state, negligible heat transfer, and constant enthalpy and velocity:

\[
\dot{W} = \dot{m} g \Delta z
\]

Mass flow rate is calculated from volumetric discharge data provided by the USGS for Fall Creek.

## Results

USGS provides flow rate measurements in cubic feet per second at 3-hour 15-minute intervals. Empty data points correspond to periods where measurements were unavailable due to frozen conditions.

```matlab
close all; % file setup

% importing data from spreadsheet
opts = detectImportOptions("water flow data fall creek.csv");
opts.VariableNamesLine = 0;
opts.VariableNames = ["Water", "Unit"]
