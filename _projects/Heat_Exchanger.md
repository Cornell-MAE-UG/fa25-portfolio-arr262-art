---
layout: project
title: Heat Exchanger
description: Homework problem for ENGRD 2210, Thermodynamics
technologies: Heat exchanger
image: "/assets/images/heat_exchanger.jpg"
---

![Our Setup]({{ "/assets/images/heat_exchanger.jpg" | relative_url }})

# Device Overview
The device I set out to analyze (with a group) was a heat exchanger and two pumps. The pumps drove hot and cold water at the same flow rate through the heat exchanger. When the liquids were output into the empty bins, their states (most notably their temperatures) were altered. 

# System Diagram

![System Diagram]({{ "/assets/images/he_diagram.drawio.png" | relative_url }})

# Descriptive Equations
The system as a whole is not really trying to maximize either work or heat transfer, so I will only be considering the mass and energy balance equations as the entropy balance will not reveal anything significant about the system.

## Pumps
The mass balance equation for control volumes is as follows

$$\dot{m_tot} = \sum{\dot{m_in}} - \sum{\dot{m_out}}$$

We can approximate the pumps as operating at steady state because they didn't seem to clog at all or be underfilled for most of the operation, reducing the mass balance to

$$0 = \sum{\dot{m_in}} - \sum{\dot{m_out}}$$

The general energy balance equation is

$$\dot{E} = \dot{Q} - \dot{W} + \sum{\dot{m_in}(h_in + \frac{(v_in)^2}{2} + gz_in)} + \sum{\dot{m_out}(h_out + \frac{(v_out)^2}{2} + gz_out)}$$

As stated above, we can approximate the pumps as operating in steady state. In addition, we can approximate them as adiabatic and ignore changes in potential and kinetic energy. Finally, there is only one inlet and one outlet. As a result, the balance becomes

$$0 = -\dot{W} + \dot{m}(h_in - h_out)$$

Overall, the pumps only serve to push the fluids through the system. Their state isn't altered significantly by this part of the system.

## Heat Exchanger

However, the heat exchanger caused a significant change in the state of the substances. Similarly to the pumps, we can approximate its operation as steady state, giving the mass balance equation

$$0 = \dot{m_in} - \dot{m_out}$$

For the energy balance equation, not only can we approximate the heat exchanger as steady state adiabatic with negligible changes in potential and kinetic energy, but it also does not take any work to operate. Thus we get

$$0 = \sum{\dot{m_in}(h_in)} - \sum{\dot{m_out}(h_out)}$$

An important consideration is that the heat exchanger was not actually operating adiabatically. We observed during the test run that the device was hot to the touch, meaning that it was losing heat to the environment. Thus, if more accuracy is desired, a better equation to use would be

$$0 = \dot{Q} + \sum{\dot{m_in}(h_in)} - \sum{\dot{m_out}(h_out)}$$

# Change in device operation
The change in operation we chose to implement was switching the flow from counterflow to parallel flow. In other words, the two flows switched from being directed against each other within the heat exchanger to being in the same direction. The change we observed was fairly drastic.

For the counterflow run, the hot flow showed a temperature drop of 21 degrees Celcius and the cold flow showed a temperature increase of 20.9 degrees Celcius. This was a noticably drastic change as the initially cold water ended up hotter than the initially hot water. 

However, for the parallel flow run, the hot flow showed a temperature drop of only 15.1 degrees Celcius while the cold flow only increased by 15.4 degrees Celcius. This left both reservoirs at a lukewarm temperature. 

Clearly, running the flows against each other was more effective in changing the enthalpy of each flow than running the flows in parallel. A possible explanation for this is that something about the flows sort of running into each other allows more heat to move between them. Further investigation is required to test this hypothesis.


