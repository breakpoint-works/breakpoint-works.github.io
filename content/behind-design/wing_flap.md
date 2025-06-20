+++
date = '2025-06-16T08:43:09+02:00'
draft = true
title = 'Foil Flap Section'
showonlyimage = false
image = "/img/behind-design/flap_section/opti_vs_eppler_sections.png"
+++

*Drag Reduction, Cavitation Control, Structural Compliance*

<!--more-->

This case study focuses on the **optimization of a flap-type wing section** for a **foiling yacht**, with design targets inspired by **America’s Cup–style boats**. The goal was to minimize **hydrodynamic drag** under sailing conditions, while ensuring the section complies with **cavitation limits** at high speeds and meets **structural constraints**.

![Optimized Section](/img/behind-design/flap_section/opti_vs_eppler_sections.png)

### Context

The optimization problem is defined by a set of operating points, each specified as a pair of **(speed, CL·chord)** to include the effect of chord variation. Two condition sets were established:

#### Performance Conditions
The following conditions represent the drag reduction objective

| Condition     			 | Speed [kn] | CL·chord |
|----------------------------|------------|----------|
| Take-off      	         | 20         | 0.20     |
| Upwind (Low-Speed)         | 29         | 0.10     |
| Upwind (High-Speed)        | 35         | 0.07     |
| Downwind      			 | 42         | 0.05     |

#### Cavitation Conditions
The following conditions represent the cavitation constraint conditions

| Condition     			 | Speed [kn] | CL·chord |
|----------------------------|------------|----------|
| Take-off      	         | 15         | 0.50     |
| Maneuver1			         | 37         | 0.15     |
| Maneuver2			         | 44         | 0.10     |
| High-Speed      			 | 47         | 0.08     |


#### Initial Section
The baseline section was an **Eppler 211**, scaled to comply with structural thickness.

![Eppler Section](/img/behind-design/flap_section/eppler_section.png)

While it performed well in low-speed conditions, early evaluation showed it **failed the cavitation criteria** above 35 knots, highlighting the need for a tailored solution.

![Eppler Cavitation Plot](/img/behind-design/flap_section/eppler_cavitation.png)

### Methodology

- A **parametric model** was used to generate alternative section shapes with a fixed **40% flap chord**.
- Sections were evaluated in **XFoil** under both performance and cavitation conditions.
- **Flap deflection** and **angle of attack (AoA)** were included as variables in the optimization.
- A **neural network surrogate model** was trained on simulation data to accelerate the multi-condition optimization while enforcing constraints on cavitation and structure.

### Results

![Optimized Section](/img/behind-design/flap_section/opti_vs_eppler_sections.png)

The resulting optimized section:

> * Is **thinner** than the original Eppler profile.
> * Is **slightly longer**, to compensate structurally.
> * Features **aft-loaded camber** and subtle **leading edge carving** to balance performance and cavitation behavior.

It satisfies the **cavitation constraints** and **structural requirements**

![Optimized Section Cavitation](/img/behind-design/flap_section/opti_cavitation.png)


Drag Optimization result:
> * The optimized section shows lower drag above 29.0kn of speed
> * The higher drag at lower speeds is the cost of increasing the top-speed of the section. Thi highlights the relevance of the design criteria seting.

![Drag Comparison](/img/behind-design/flap_section/drag_comparison.png)


### Summary

This case illustrates how a **multi-objective optimization** combining **drag, cavitation, and structure** can inform the design of complex foil sections with flaps. By exploring design trade-offs across a wide performance envelope, the process yields deeper understanding of what performance gains come at what cost — a key principle in advanced foil design.
