# Bifurcation Analysis of the 2D Bratu Problem using IGKM

## Overview

This project investigates **nonlinear boundary value problems** and **bifurcation behavior** in the **2D Bratu problem**, solved using the **Iterative Generalized Kantorovich Method (IGKM)**. The results include visualizations of bifurcation diagrams, solution profiles, and comparisons between different Taylor expansion orders.

The Bratu equation:
$$
-\Delta u = \lambda e^u \quad \text{in } \Omega, \quad u = 0 \text{ on } \partial \Omega
$$


is known for exhibiting bifurcation — multiple solution branches for the same parameter λ.



## Explanation of Results

### 1. **Bifurcation Curve: L2 Norm vs. λ**
**Figure:** Plot of ‖v‖ vs. λ for different Taylor orders (k=1, 2, 3)

- This diagram shows how the **L2 norm of the numerical solution** changes with respect to the parameter `λ`.
- Initially, as λ increases, the norm of the solution grows smoothly.
- At a **critical λ**, the curve bends back, showing **multiple solutions for the same λ** → this is the **bifurcation point**.
- **Observation:** Higher Taylor orders (e.g., k=3) provide more accurate and stable branches beyond bifurcation.

 **Conclusion:** IGKM captures both the upper and lower branches of bifurcating solutions when continuation is applied.



###  2. **Solution Profiles for Selected λ**
**Figures:** Plots of `v(x)` vs. grid points for λ = 1.0, 2.0, and 3.0

- These plots show how the **shape of the solution** changes as λ increases.
- For **λ = 1.0**, the solution is smooth and moderate in magnitude.
- For **λ = 2.0**, the curve becomes more peaked, indicating the solution is becoming steeper near the domain center.
- For **λ = 3.0**, the solution shows a **sharp spike**, suggesting strong nonlinearity.

 **Conclusion:** As λ increases, the solution becomes more localized and nonlinear, especially near the bifurcation threshold.



### 3. **Effect of Taylor Expansion Order**
**Figures:** Bifurcation curves for Taylor orders k = 1, 2, 3

- These curves are overlaid to demonstrate how different Taylor expansion orders affect the computed solution.
- **k = 1** (linear approximation) fails to capture the full bifurcation branch.
- **k = 2** shows better approximation but may still deviate post-critical λ.
- **k = 3** provides smooth and accurate tracing even for unstable branches.

**Conclusion:** Higher Taylor orders improve stability and accuracy, especially after bifurcation.



### 4. **Continuation Behavior**
**Observation (no explicit figure):**
- The solver uses a continuation method: the solution for a given λ is used as the **initial guess** for the next.
- This ensures **smooth tracking** of the solution curve, especially on complex bifurcation branches.

**Conclusion:** Continuation is essential to explore nonlinear solution landscapes.






## Summary of Interpretation

| λ Value | Behavior of Solution | Bifurcation Observation |
|--------:|----------------------|--------------------------|
| λ < 1.5 | Single smooth solution | Stable branch |
| λ ≈ 2.5 | Multiple branches appear | Bifurcation point visible |
| λ > 3.0 | Strongly peaked solutions | High instability, multiple solutions |



##  Final Takeaways

- The bifurcation diagrams confirm **non-uniqueness of solutions** in the nonlinear Bratu model.
- IGKM combined with Taylor expansion and continuation can successfully **trace full bifurcation curves**.
- Increasing the Taylor order improves approximation past bifurcation.



## 📌 Recommendation

This approach can be extended to more complex nonlinear PDEs, and the solver can be upgraded to:
- Track unstable branches more robustly
- Compute eigenvalues of Jacobians for dynamical stability
- Generalize to 2D grids for surface plots


