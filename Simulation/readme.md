# Simulation

---

# Finite Element Method

## Julian Roth's Finite Element Method

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

## Efficient Engineer's Understanding the Finite Element Method

Turning a problem into linear algebra $\{F\} = [K] \{U\}$ where $\{U\}$ is the input and $\{F\}$ is the output.
The $[K]$ is usually obtained from a concept of equilibrium.
* Direct method: differential equations---strong form
* Variational method: weak form
  * Principle of Minimum Potential Energy: "The displacement configuration that satisfies equilibrium conditions is the one that minimizes the total potential energy." 
* Galerkin method of weighted residuals: weak form
  * Assume an approximation solution $y^\ast(x) = \sum_i c_i N_i(x)$
    * where $c_i$ : coefficient; $N_i(x)$ : trial function, e.g., polynomial
  * Let $R(x) = D(x|y^\ast(x))$
    * where $R(x)$ : residual, $R(x) = 0$ if $y^\ast(x)$ is the exact solution
    * $D(x|y^\ast(x))$ is the differential eq. to be solved.
  * Solve for $c_i$'s from $\int_a^b N_1(x) R(x) dx = 0$, $\int_a^b N_2(x) R(x) dx = 0$, ..., $\int_a^b N_n(x) R(x) dx = 0$.




Estimating value of $v(x,y)$ in a mesh face with vertices $v_1, v_2, v_3, v_4$ by $v(x,y) = N_1(x,y) v_1 + N_2(x,y) v_2 + N_3(x,y) v_3 + N_4(x,y) v_4$
where shape functions $N_i$'s are often polynomial, e.g.,
* $N_1(x,y) = \frac{1}{4}(1 - r)(1 - s)$
* $N_2(x,y) = \frac{1}{4}(1 + r)(1 - s)$
* $N_3(x,y) = \frac{1}{4}(1 + r)(1 + s)$
* $N_4(x,y) = \frac{1}{4}(1 - r)(1 + s)$

 My note: I don't know why we need this interpolation given that we have solved $y^\ast(x)$.

---

## Edx: Introduction to Simulation

### 1-D Heat distribution on an isotropic iron bar

* Given $k \frac{d^2 T}{d x^2} + Q = 0$ for $0 \leq x \leq L$, solve for $T(x)$.
* Boundary conditions
  * $T(0) = T_0$
  * $q(L) = q_L = - k \frac{dT}{dx}|_{x=L}$ 
* $T$ : temperature, $q$ heat flow per unit area, "heat flux"

My note: $q = - k \frac{dT}{dx}$ means: 
  * along $x$, negative heat flux $q < 0$ takes heat in and temperature rises.
  * along $x$, positive heat flux $q > 0$ takes heat out and temperature gets lower.


To solve the problem,
* Direct method: exact solution -> Calculus
* Galerkin: $[K] \{ T \} = \{ Q \}$


#### Derive a weak form
* If $k \frac{d^2 T}{d x^2} + Q = 0$,
  * then $\int_0^L w(x) \cdot \left(k \frac{d^2 T}{d x^2} + Q\right) = 0$ also holds for an arbitrary function $w(x)$.
* Let $w(x)$ be an arbitrary piecewise polynomial function.

With integration by parts,
* $\int_0^L w(x) \cdot \left(k \frac{d^2 T}{d x^2} + Q\right) = 0$
* $w(x) \cdot k \frac{dT}{dx}|_0^L - \int_0^L \frac{dw}{dx} k \frac{dT}{dx} dx + \int_0^L w(x) Q dx  = 0$

#### Discretize $x \in [0, L]$ into $M$ parts, e.g., 3 parts (4 nodes: 1, 2, 3, 4)

* $w(x) \cdot k \frac{dT}{dx}|_0^L$
  * $w(x) \cdot k \frac{dT}{dx}|_0^L = w(x) \cdot k \frac{dT}{dx}|^{x=L} - w(x) \cdot k \frac{dT}{dx}|^{x=0})$
  * $w(x) \cdot k \frac{dT}{dx}|_0^L \approx w_4 \cdot k \frac{dT}{dx}|^{x=L} - w_1 \cdot k \frac{dT}{dx}|^{x=0}$
* $\int_0^L \frac{dw}{dx} k \frac{dT}{dx} dx$
  * Recall $\frac{dw}{dx} = \frac{w_{i+1} - w_i}{\Delta x}$ and $\frac{dT}{dx} = \frac{T_{i+1} - T_i}{\Delta x}$
  * Hence, $\int_0^L \frac{dw}{dx} k \frac{dT}{dx} dx \approx \frac{k}{\Delta x} \left( (w_2 - w_1)(T_2 - T_1) + (w_3 - w_2)(T_3 - T_2) + (w_4 - w_3)(T_4 - T_3) \right)$
* $\int_0^L w(x) Q dx = Q \int_0^L w(x) dx$
  * $\int_0^L w(x) dx$ : area under curve and since we choose $w(x)$ to be piecewise linear, the area is a sum of trazoidal areas: $Q \int_0^L w(x) dx \approx Q \left( \Delta x (w_1 + w_2)/2 + \Delta x (w_2 + w_3)/2  + \Delta x (w_3 + w_4)/2 \right)$
  * Hence, $Q \int_0^L w(x) dx \approx Q \Delta x \left(  w_1/2  + w_2 + w_3 + w_4/2 \right)$

Approximate 
$$w_4 \cdot k \frac{dT}{dx}|^{x=L} - w_1 \cdot k \frac{dT}{dx}|^{x=0} - \frac{k}{\Delta x} \left( (w_2 - w_1)(T_2 - T_1) + (w_3 - w_2)(T_3 - T_2) + (w_4 - w_3)(T_4 - T_3) \right) + Q \Delta x \left(  w_1/2  + w_2 + w_3 + w_4/2 \right) = 0$$

and rearrange to
$$w_1 \cdot (\frac{Q \Delta x}{2} - k \frac{dT}{dx}|^{x=0})$$
$$+ w_2 \cdot (Q \Delta x)$$
$$+ w_3 \cdot (Q \Delta x)$$
$$+ w_4 \cdot (\frac{Q \Delta x}{2} + k \frac{dT}{dx}|^{x=L}) = 0$$

---

# Computational Fluid Dynamics
