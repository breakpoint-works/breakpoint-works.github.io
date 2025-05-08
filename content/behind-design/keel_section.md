+++
date = '2025-05-08T20:34:59+02:00'
draft = false
title = 'Keel Section'
showonlyimage = false
image = "img/behind-design/keel_section/section_evaluation.png"
+++


*AI-Driven Design for Performance*

<!--more-->

This case study explores the **optimization of 2D hydrofoil sections** using **machine-learning tools**, with application to **keel design** for high-performance sailing.

### Context

Designing foil sections involves trade-offs between **hydrodynamic efficiency**, **structural requirements**, and **cavitation boundaries**. Standard airfoils often don’t meet all constraints, so optimization is required to find the best solution that meets all the requirements.


### Methodology

*   **Input Parameters**  
    Defined **performance and cavitation conditions**, along with **structural** and **geometrical constraints** (e.g. max chord, thickness).  
    For the particular case study:
    * **Upwind**: 8 kn, CL·chord = 0.16
    * **Downwind**: 12 kn, CL·chord = 0.05
*   **Candidate Generation**  
    A **parametric model** was used to produce thousands of candidate section shapes.  
    Approximately **6,000 candidates** were analyzed for the particular study.
*   **Evaluation & Optimization**  
      Each section is evaluated using **XFoil**, and an **AI-based surrogate model** was trained to speed up the search for an optimal design meeting all constraints.


### Results

During the case study, three baseline profiles were considered: **NACA-0018**, **NACA-6 series**, and **Eppler**.  
The resulting design achieved a **~10% drag reduction** compared to the Eppler section, while still satisfying structural constraints.

![Section Evaluation Plot](/img/behind-design/keel_section/section_evaluation.png)

### Summary

Using a combination of **parametric modeling**, **XFoil**, and **AI-driven optimization**, we developed a foil section with **improved hydrodynamic** performance while **complying with structural criteria** — a workflow applicable to a broad range of hydro/aerodynamic challenges.


