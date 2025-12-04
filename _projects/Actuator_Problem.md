---
layout: project
title: Actuator and Bar
description: Homework problem for ENGRD 2020, Statics and Mechanics of Materials
technologies: 
image: "/assets/images/actuator_final.jpg"
---

# Part 1

Our assignment was to use a bar of any length, 3 pinned supports (two of which were grounded), and a linear actuator from this catalog (https://www.tolomatic.com/wp-content/uploads/2022/05/2700-4000_29_IMA_cat.pdf) to lift the maximum amount of weight the maximum possible height. We were given a 2D design space 150 cm wide and 50 cm tall and told to treat all bars (actuator included) as rigid.

I figured that the best way to accomplish this task was to have the actuator perpendicular to the bar at some point during its upwards motion. This way, all of the compression in the actuator is going towards resisting the moment created by the weight. I decided that the end state of the actuator would be perpendicular to the support bar, creating a constraint on both the initial and final positions of my mechanism. 

![Calculations]({{ "/assets/images/actuator_work.jpg" | relative_url }}){: .inline-image-r }

After drawing free body diagrams and performing the necessary calculations, I ended up with 7 equations governing my system. Using those equations, I set up a spreadsheet and started messing around with my adjustable values, L and d. I also traded off keeping the final height and the final length of the actuator a constant to see which would give me the best values. Interestingly, the main constraint on the maximum weight was not the final position of the actuator but the initial position. 

![Spreadsheet]({{ "/assets/images/image.png" | relative_url }}){: .inline-image-r}

I eventually settled on a design which had d > L and gave a maximum final weight of 51.33 kN and a maximum final height of 0.32m, for a total height change of 0.2m. 

![Final Design]({{ "/assets/images/actuator_final.jpg" | relative_url }})

# Part 2

Then, later, we were told that our beam was no longer rigid. We now needed to calculate the maximum deflection and design a beam that only deflects 2% of the beam length with minimal weight. 

Through the power of mathematics and the magical formula

$$ M(x) = EIy'' $$

I was able to derive the maximum deflection of the beam. The total force on the end ended up being 7.61 kN. I modelled the beam as simply supported and used the boundary conditions that the deflection at either end was 0. This is because the ground end stays pinned to the ground and we are still assuming that the actuator is a rigid bar. 

![My Calculations]({{ "/assets/images/beam_deflection_calcs.jpg" | relative_url }}){: .inline-image-r}

After the calculations shown, I arrived at a maximum deflection of 

$$ y_{max} = \frac{F}{6EI}(\frac{\sqrt{3}}{3}L)^3 - \frac{FL^2}{6EI}(\frac{\sqrt{3}}{3}L) $$

F is the net force of 7.61 kN, E is the Young's Modulus of the material, I is the second moment of area of the cross section, and L is the beam length of 0.6m. Using this, I derived an expression for EI.

$$ EI = \frac{2\sqrt{3}FL^2}{9*0.02*6} = 8787.27 Nm^2 $$

I then went back to a spreadsheet to determine a good set for E and I. Surprisingly, the beam doesn't need to be super strong to achieve the above strength metric. Thus, I chose a very economical design, selecting the light Western White Pine wood as my material and the S75x8.5 beam standard as my cross section. This gave me an EI well within the necessary limit and a total weight of 0.25 kg. 

![Spreadsheet]({{ "/assets/images/beam_sheet.png" | relative_url }}){: .inline-image-r}

![Final Design]({{ "/assets/images/beam_cross_section.png" | relative_url }})


