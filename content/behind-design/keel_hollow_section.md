+++
date = '2025-05-14T20:34:59+02:00'
draft = false
title = 'Hollow Keel Section'
showonlyimage = false
image = "/img/behind-design/hollow_keel_section/pareto_section_3.png"
+++

*Weight–Drag Tradeoff with Structural Constraints*

<!--more-->

This case study builds upon the methodology used in a previous [keel section optimization](/behind-design/keel_section/), but introduces a new design variable: **section weight**. The objective is to explore the trade-off between **hydrodynamic drag** and **structural weight**, using a **hollow keel section**.

### Context  
Designing a keel section requires balancing **hydrodynamic efficiency**, **structural performance**, and now, **wall thickness**. A thinner structure reduces weight, but may increase drag or compromise strength. Understanding this trade-off is key to identifying a meaningful optimum.

### Methodology

*   **Input Parameters**  
    Defined **performance and cavitation conditions**, along with **structural** and **geometrical constraints** (e.g. max chord, thickness).  
    For the particular case study:
    * **Upwind**: 8 kn, CL·chord = 0.16
    * **Downwind**: 12 kn, CL·chord = 0.05
*   **Candidate Generation**  
    A **parametric model** produces thousands of hollow section shapes, each with a different internal geometry.
*   **Evaluation & Optimization**  
    *    Each section is evaluated using **XFoil**.  
    *   A **machine-learning surrogate model** is trained on the dataset and used to generate a **Pareto front** of **drag vs. weight**, under the constraint that sections must meet **structural criteria**.


### Results

The resulting **Pareto front** reveals a clear **turning point** around **Section_3**:

*   Attempting to go lighter than that point leads to a **steep increase in drag**.
*   Up to that threshold, **weight can be reduced by ~50%** with only a **moderate drag penalty**.
*   This enables informed design decisions based on project priorities — whether to **favor lighter structure** or **lower hydrodynamic resistance**.

![Drag vs Weight Pareto Front](/img/behind-design/hollow_keel_section/pareto.png)

The images below show the four representative sections along the Pareto front, illustrating the design trade-offs between weight and drag.  

*   **Section 0 – Lowest drag**  
    Solid section thath prioritizes hydrodynamic performance, resulting in higher weight.
    ![Section 0](/img/behind-design/hollow_keel_section/pareto_section_0.png)
*   **Section 1 – Low drag, heavier structure**  
    A compromise between weight and drag; sits well before the sharp increase on the Pareto curve. 
    ![Section 1](/img/behind-design/hollow_keel_section/pareto_section_1.png)
*   **Section 3 – On the Pareto kink**  
    Marks the transition point on the Pareto front — just before drag increases significantly. A particularly interesting design from a trade-off perspective. 
    ![Section 3](/img/behind-design/hollow_keel_section/pareto_section_3.png)
*   **Section 5 – Very light, high drag**
    Achieves very low weight with a large chord and thin walls, but at the cost of significantly higher drag — beyond the efficient trade-off region.  
    ![Section 5](/img/behind-design/hollow_keel_section/pareto_section_5.png)


### Summary

By introducing **section weight** as an optimization variable, this study shows how machine learning can help navigate the complex relationship between **drag and structural mass**.  

The **Pareto front** provides a powerful tool for identifying designs that offer the best balance between weight and drag.


