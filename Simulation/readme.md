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


Estimating value of $v(x,y)$ in a mesh with vertices $v_1, v_2, v_3, v_4$ by $v(x,y) = N_1(x,y) v_1 + N_2(x,y) v_2 + N_3(x,y) v_3 + N_4(x,y) v_4$
where shape functions $N_i$'s are often polynomial, e.g.,
* $N_1(x,y) = \frac{1}{4}(1 - r)(1 - s)$
* $N_2(x,y) = \frac{1}{4}(1 + r)(1 - s)$
* $N_3(x,y) = \frac{1}{4}(1 + r)(1 + s)$
* $N_4(x,y) = \frac{1}{4}(1 - r)(1 + s)$
 

---

## Edx: Introduction to Simulation

### 1-D Heat distribution on an isotropic iron bar

* Given $k \frac{d^2 T}{d x^2} + Q = 0$ for $0 \leq x \leq L$, solve for $T(x)$.
* Boundary conditions
  * $T(0) = T_0$
  * $q(L) = q_L = - k \frac{dT}{dx}|_{x=L}$ 
* $T$ : temperature, $q$ heat flow per unit area, "heat flux"

* Direct method: exact solution -> Calculus
* Galerkin: $[K] \{ T \} = \{ Q \}$


#### Derive a weak form
* If $k \frac{d^2 T}{d x^2} + Q = 0$,
  * then $\int_0^L w(x) \cdot \left(k \frac{d^2 T}{d x^2} + Q\right) = 0$ also holds for an arbitrary function $w(x)$.
* Let $w(x)$ be an arbitrary piecewise polynomial function.

With integration by parts,
* $\int_0^L w(x) \cdot \left(k \frac{d^2 T}{d x^2} + Q\right) = 0$
* $w(x) \cdot k \frac{dT}{dx}|_0^L - \int_0^L \frac{dw}{dx} k \frac{dT}{dx} dx + \int_0^L w(x) Q dx  = 0$

#### Discretize $x \in [0, L]$ into $M$ parts, e.g., 4

* $w(x) \cdot k \frac{dT}{dx}|_0^L \approx$
* $\int_0^L \frac{dw}{dx} k \frac{dT}{dx} dx \approx$
* $\int_0^L w(x) Q dx \approx \sum_{i=1}^4 w_i Q \Delta x$

---

# Computational Fluid Dynamics
