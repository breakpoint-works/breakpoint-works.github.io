+++
date = '2025-06-16T08:43:09+02:00'
draft = true
title = 'Foil Flap Section'
+++

*Drag Reduction, Cavitation Control, Structural Compliance*

<!--more-->

This case study focuses on the **optimization of a flap-type wing section** for a **foiling yacht**, with design targets inspired by **America’s Cup–style boats**. The goal was to minimize **hydrodynamic drag** under sailing conditions, while ensuring the section complies with **cavitation limits** at high speeds and meets **structural constraints**.

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
The baseline section was a **modified Eppler 211**, scaled to comply with structural thickness. While it performed well in low-speed conditions, early evaluation showed it **failed the cavitation criteria** above 35 knots, highlighting the need for a tailored solution.

![Eppler Cavitation Plot](/img/behind-design/flap_section/eppler_cavitation.png)

### Methodology

- A **parametric model** was used to generate alternative section shapes with a fixed **40% flap chord**.
- Sections were evaluated in **XFoil** under both performance and cavitation conditions.
- **Flap deflection** and **angle of attack (AoA)** were included as variables in the optimization.
- A **neural network surrogate model** was trained on simulation data to accelerate the multi-condition optimization while enforcing constraints on cavitation and structure.

### Results

The resulting optimized section:

* Is **thinner** than the original Eppler profile.
* Is **slightly longer**, compensating structurally.
* Features **aft-loaded camber** and subtle **leading edge carving** to balance performance and cavitation behavior.

It satisfies all **cavitation constraints** and **structural requirements**, and delivers **lower drag** than the Eppler baseline in all conditions — **except the lowest-speed one**, where the Eppler’s rounder nose geometry performs slightly better.

### Insight

This trade-off reveals an important design tension:  
> **Gaining top-speed capability often requires paying for it in low-speed drag.**

By plotting **drag across sailing conditions** vs. **maximum cavitation-free speed**, a clear trend emerges: pushing cavitation limits higher results in **disproportionate drag penalties** at lower speeds — a valuable insight when prioritizing design objectives.

### Summary

This case illustrates how a **multi-objective optimization** combining **drag, cavitation, and structure** can inform the design of complex foil sections with flaps. By exploring design trade-offs across a wide performance envelope, the process yields deeper understanding of what performance gains come at what cost — a key principle in advanced foil design.
