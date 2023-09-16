# Simulation

---

# Finite Element Method

## Julian Roth's Finite Element Method is also better at explaining the rigorous math, but it's too theoretical than I want.

Solve the original problem (~ partial differential equations) by
1. Turning it to weak form
2. Discritization
3. Making it linear algebra


Strong form to weak form
E.g., 
* strong form: differential equation $D(x, t) = 0$.
* weak form: $\int_\Omega D(x, t) \phi(x) dx = 0$ for any $\phi(x)$.

Strain: $\epsilon = \frac{\Delta L}{L_0}$

Stress: $\sigma = E \cdot \epsilon$

## Efficient Engineer's Understanding the Finite Element Method has done a much better job

Turning a problem into linear algebra $\{F\} = [K] \{U\}$ where $\{U\}$ is the input and $\{F\}$ is the output.
The $[K]$ is usually obtained from a concept of equilibrium.
* Direct method: differential equations---strong form
* Variational method: weak form
  * Principle of Minimum Potential Energy: "The displacement configuration that satisfies equilibrium conditions is the one that minimizes the total potential energy." 
* Galerkin method of weighted residuals: weak form
  * Assume an approximation solution $y^\ast(x) = \sum_{i=1}^n c_i N_i(x)$
    * where $c_i$ : coefficient; $N_i(x)$ : trial function, e.g., polynomial
  * Let $R(x) = D(x|y^\ast(x))$
    * where $R(x)$ : residual, $R(x) = 0$ if $y^\ast(x)$ is the exact solution
    * $D(x|y^\ast(x))$ is the differential eq. to be solved.
  * Solve for $c_i$'s from $\int_a^b N_1(x) R(x) dx = 0$, $\int_a^b N_2(x) R(x) dx = 0$, ..., $\int_a^b N_n(x) R(x) dx = 0$.



---

## Edx: Introduction to Simulation

---

# Computational Fluid Dynamics
