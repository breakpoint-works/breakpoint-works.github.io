+++
date = '2025-06-16T08:43:09+02:00'
draft = true
title = 'Foil Flap Section'
showonlyimage = false
image = "/img/behind-design/flap_section/opti_vs_eppler_sections.png"
+++

*Drag Reduction, Cavitation Control*

<!--more-->

This case study focuses on the **optimization of a flap-type wing section** for a **foiling yacht**, with design targets inspired by **America’s Cup–style boats**. The goal was to minimize **hydrodynamic drag** under sailing conditions, while ensuring the section complies with **cavitation limits** and meets **structural constraints**.

![Optimized Section](/img/behind-design/flap_section/opti_vs_eppler_sections.png)

### Inputs

The optimization problem is defined by a set of operating points, each specified as a pair of **(speed, CL·chord)**. 
Two condition sets were established:

##### Performance Conditions – Optimization Targets  

> * Take-off: 20 kn, CL·chord = 0.20
> * Straight-Line (Low-Speed): 29 kn, CL·chord = 0.10
> * Straight-Line (Mid-Speed): 35 kn, CL·chord = 0.07
> * Straight-Line (High-Speed): 42 kn, CL·chord = 0.05

##### Cavitation Conditions – Constraints  
> * Take-off: 15 kn, CL·chord = 0.50
> * Maneuver 1: 37 kn, CL·chord = 0.15
> * Maneuver 2: 44 kn, CL·chord = 0.10
> * Top-Speed: 47 kn, CL·chord = 0.08


##### Initial Section
The baseline section was an **Eppler 211**, scaled to comply with structural thickness.

![Eppler Section](/img/behind-design/flap_section/eppler_section.png)

While it performed well in low-speed conditions, early evaluation showed it failed to meet cavitation criteria above 35 knots, highlighting the need for a more specialized solution.

![Eppler Cavitation Plot](/img/behind-design/flap_section/eppler_cavitation.png)

### Methodology

- A **parametric model** was used to generate alternative section shapes with a fixed **40% flap chord**.
- Sections were evaluated in **XFoil** under both performance and cavitation conditions.
- **Flap deflection** and **angle of attack (AoA)** were included as variables in the optimization.
- A **neural network surrogate model** was trained on simulation data to accelerate the multi-condition optimization while enforcing constraints on cavitation and structure.

### Results

![Optimized Section](/img/behind-design/flap_section/opti_vs_eppler_sections.png)

The optimized section:

> * Is **thinner** than the original Eppler profile.
> * Is **slightly longer**, to compensate structurally.
> * Features **aft-loaded camber** and subtle **leading edge carving** to balance performance and cavitation behavior.

##### Cavitation

It successfully satisfies all **cavitation** constraints.

![Optimized Section Cavitation](/img/behind-design/flap_section/opti_cavitation.png)


##### Drag Optimization

> * The optimized section shows **lower drag** than the baseline in all conditions **above 29 knots**
> * The **higher drag at lower speeds** is the trade-off for increasing the **maximum cavitation-free speed**

![Drag Comparison](/img/behind-design/flap_section/drag_comparison.png)

This trade-off becomes more evident when plotting **drag in performance conditions** versus **top cavitation-free speed** across the design exploration space.  
It is clear that improving top-speed cavitation resistance comes at the cost of **higher drag in low-speed conditions**, especially when top-speed is increased beyond the 35-knots mark.

![Top Speed Impact](/img/behind-design/flap_section/drag_vs_top_speed.png)

### Summary

This case illustrates how a **multi-objective optimization**—balancing **drag**, **cavitation**, and **structure**—can guide the design of advanced foil sections with flaps.  
By exploring performance trade-offs across a wide range of conditions, the process offers valuable insights into what gains are achievable — and at what cost.
