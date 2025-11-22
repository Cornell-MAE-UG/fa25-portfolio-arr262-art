---
layout: project
title: Actuator and Bar
description: Homework problem for ENGRD 2020, Statics and Mechanics of Materials
technologies: 
image: "/assets/images/actuator_final.jpg"
---

Our assignment was to use a bar of any length, 3 pinned supports (two of which were grounded), and a linear actuator from this catalog (https://www.tolomatic.com/wp-content/uploads/2022/05/2700-4000_29_IMA_cat.pdf) to lift the maximum amount of weight the maximum possible height. We were given a 2D design space 150 cm wide and 50 cm tall and told to treat all bars (actuator included) as rigid.

I figured that the best way to accomplish this task was to have the actuator perpendicular to the bar at some point during its upwards motion. This way, all of the compression in the actuator is going towards resisting the moment created by the weight. I decided that the end state of the actuator would be perpendicular to the support bar, creating a constraint on both the initial and final positions of my mechanism. 

![Calculations]({{ "/assets/images/actuator_work.jpg" | relative_url }}){: .inline-image-r }

After drawing free body diagrams and performing the necessary calculations, I ended up with 7 equations governing my system. Using those equations, I set up a spreadsheet and started messing around with my adjustable values, L and d. I also traded off keeping the final height and the final length of the actuator a constant to see which would give me the best values. Interestingly, the main constraint on the maximum weight was not the final position of the actuator but the initial position. 

![Spreadsheet]({{ "/assets/images/image.png" | relative_url }}){: .inline-image-r}

I eventually settled on a design which had d > L and gave a maximum final weight of 51.33 kN and a maximum final height of 0.32m, for a total height change of 0.2m. 

![Final Design]({{ "/assets/images/actuator_final.jpg" | relative_url }})

