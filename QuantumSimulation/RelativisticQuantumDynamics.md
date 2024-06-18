# Relativistic Quantum Dynamics

---

* [Level 1: Relativistic quantum dynamics](https://github.com/tatpongkatanyukul/iExplore/blob/main/QuantumSimulation/RelativisticQuantumDynamics.md)
  * System: atomic nuclei (mass, charge, spin), electrons (mass, charge, spin), photons (frequency)
  * Rules: relativistic time-dependent quantum mechanics; Dirac's equation; (quantum) electrodynamics
  * Approximation: Particle velocities small compared to velocity of light
    * No go: electrons close to heavy nuclei; hot plasmas 

---

# The wave character of particles

* Particles (such as electrons in beams) show diffraction behavior as if they are waves.  [[Me: double-slit experiment?]](https://en.wikipedia.org/wiki/Double-slit_experiment) The wavelength $\lambda$ appears to be related to the momentum $p = m v$ of the particle by $\lambda = h/p$, where $h$ is Planck's constant.

  If we define $\mathbf{k}$ as the _wave vector_ in the direction of the velocity of the particle and with absolute value $k = 2 \pi / \lambda$, then

  $$\mathbf{p} = \bar{h} \mathbf{k}$$

  (with $\bar{h} = h/2 \pi$) is a fundamental relation between the momentum of a particle and its wave vector.

* Electromagnetic waves (such as monochromatic light) appear to consist of packages of energy of magnitude $h \nu$, where $\nu$ is the frequency of the (monochromatic) wave, or $\bar{h} \omega$, where $\omega = 2 \pi \nu$ is the angular frequency of the wave.

  Assuming that particles have a wave character, we may generalize this to identify the frequency of the wave with energy of the particle:

  $$E = \bar{h} \omega$$

Let us further define a _wave function_ $\psi(\mathbf{r}, t)$ that describes the wave, A homogeneous plane wave, propagating in the direction of $\mathbf{k}$ with a phase velocity $\omega/k$ is described by

$$\Psi(\mathbf{r}, t) = c \exp[i (\mathbf{k} \cdot \mathbf{r} - \omega t)]$$

where $c$ is a complex constant, the absolute value of which is the amplitude of the wave, while its argument defines the phase of the wave.

In general, a particle may be described by a superposition of many (a continuum of) waves of different wave vector and frequency:

$$\Psi(\mathbf{r}, t) = \int d \mathbf{k} \int d \omega G(\mathbf{k}, \omega) \exp[i (\mathbf{k} \cdot \mathbf{r} - \omega t)]$$

where $G$ is a distribution function of the wave amplitude in $\mathbf{k}, \omega$ space.

Here, we recognize that $\Psi(\mathbf{r}, t)$ and $G(\mathbf{k},\omega)$ are each other's Fourier transform, although the sign conventions for the spatial and temporal transforms differ.

## Time-dependent wave function

Of course, the transform can also be limited to the spatial variable only, yielding a time-dependent distribution in $\mathbf{k}$-space (we introduce a factor of $(2 \pi)^{-3/2}$ for symmetry reasons):

$$\Psi(\mathbf{r}, t) = (2 \pi)^{-3/2} \int d \mathbf{k}  g (\mathbf{k}, t) \exp [ i (\mathbf{k} \cdot \mathbf{r})] $$

The inverse transform is

$$g(\mathbf{k}, t) = (2 \pi)^{-3/2} \int d \mathbf{r}  \Psi (\mathbf{r}, t) \exp [ - i (\mathbf{k} \cdot \mathbf{r})] $$

[Me: Recall $\mathbf{r} \cdot \mathbf{k} = 0$ for any $\mathbf{k}$ orthogonal to $\mathbf{r}$.]

The next crucial step is one of interpretation: we interpret $\Psi^\ast \Psi(\mathbf{r}, t)$ as the _probability density_ that the particle is at $\mathbf{r}$ at time $t$. Therefore we require for a particle with continuous existence the probability density to be normalized at all times:

$$\int d \mathbf{r} \Psi^\ast \Psi(\mathbf{r}, t) = 1$$

where the integration is over all space. Likewise $g^\ast g$ is the probability density in $\mathbf{k}$-space; the normalization of $g^\ast g$ is automatically satisfied:

$$\int d \mathbf{k} g^\ast g(\mathbf{k}, t) = 1$$

The _expectation value_, indicated by triangular brackets, of an observale $f(\mathbf{r})$, which is a function of space only, then is

$$\langle f(\mathbf{r}) \rangle (t) = \int d \mathbf{r} \Psi^\ast \Psi (\mathbf{r}, t) f(\mathbf{r})$$

If we apply these equations to define the expectation values of the _variances_ of one coordinate $x$ and its conjugate $k = k_x$:

$$\sigma_x^2 = \langle (x - \langle x \rangle)^2 \rangle$$

$$\sigma_k^2 = \langle (k - \langle k \rangle)^2 \rangle$$

we can show (see Chapter 12) that

$$\sigma_x \sigma_k \geq \frac{1}{2}$$ 

which shows that two conjugated variables as $x$ and $k$ ([Me: position and direction]) cannot be simultaneously sharp. 
This is Heisenberg's _uncertainty relation_, which also applies to $t$ and $\omega$.

As shown in Chapter 12, averages over $\mathbf{k}$ [Me: _wave vector_ in the direction of the velocity of the particle] and powers of $k$ can be rewritten in terms of the spatial wave function $\Psi$:

$$\langle \mathbf{k} \rangle (t) = \int d \mathbf{r} \Psi ^ \ast (- i \nabla) \Psi (\mathbf{r}, t)$$

$$\langle k^2 \rangle (t) = \int d \mathbf{r} \Psi ^ \ast (- \nabla ^ 2) \Psi (\mathbf{r}, t)$$

Thus, the expectation of some observable $A$, being either a function of $\mathbf{r}$ only, or being proportional to $\mathbf{k}$ or to $k^2$, can be obtained from

$$\langle A \rangle (t) = \int d \mathbf{r} \Psi^\ast (\mathbf{r}, t) \hat{A} \Psi (\mathbf{r}, t)$$

where $\hat{A}$ is an _operator_ acting on $\Psi$ , and

$$ \hat{\mathbf{k}} = -i \nabla $$

$$ \hat{k}^2 = - \nabla^2$$

Similarly, the expectation value of the angular frequency $\omega$ is found from equation by using the operator

$$\hat{\omega} = i \frac{\partial}{\partial t}$$

The identifications $\mathbf{p} = \bar{h} \mathbf{k}$ and $E = \bar{h} \omega$ allow the following operator definitions:

$$\hat{\mathbf{p}} = -i \bar{h} \nabla$$

$$\hat{p}^2 = - \bar{h}^2 \nabla ^ 2 $$

$$\hat{E} = i \bar{h} \frac{\partial}{\partial t}$$

From these relations and expression of the energy as a function of momenta and positions, the equations of motion for the wave function follow.

> Me:
> * $\langle \mathbf{p} \rangle = \int d \mathbf{r} \Psi^\ast (\mathbf{r}, t) (- i \bar{h} \nabla) \Psi (\mathbf{r}, t)$
> * $\langle p^2 \rangle = \int d \mathbf{r} \Psi^\ast (\mathbf{r}, t) (- \bar{h}^2 \nabla^2) \Psi (\mathbf{r}, t)$
> * $\langle E \rangle = \int d \mathbf{r} \Psi^\ast (\mathbf{r}, t) (i \bar{h} \frac{\partial}{\partial t}) \Psi (\mathbf{r}, t)$

---

# Non-relativistic single free particle

In principle, we need the relativistic relations between energy, momentum, and external fields, but for clarity we shall first look at the simple non-relativistic case of a single particle in one dimension without external interactions.
This will allow us to look at some basic propagation properties of wave functions.

Using the relation

$$E = \frac{p^2}{2 m}$$

then $\hat{p}^2 = - \bar{h}^2 \nabla ^ 2$
and $\hat{E} = i \bar{h} \frac{\partial}{\partial t}$
give the following equations of motion for the wave function:

$$i \bar{h} \frac{\partial \Psi(x,t)}{\partial t} = - \frac{\bar{h}^2}{2 m} \frac{\partial^2 \Psi}{\partial x^2}$$

or

$$\frac{\partial \Psi}{\partial t} = \frac{i \bar{h}}{2 m} \frac{\partial^2 \Psi}{\partial x^2}$$

This is in fact the time-dependent Schro\:dinger equation.
This equation looks much like Fick's diffusion equation, with the difference that the diffusion constant is now imaginary (or, equivalently, that the diffusion takes place in imaginary time).

If we choose an initial wave function $\Psi(x,0)$, with Fourier transform $g(k,0)$, then the solution of $\frac{\partial \Psi}{\partial t} = \frac{i \bar{h}}{2 m} \frac{\partial^2 \Psi}{\partial x^2}$ is simply

$$\Psi (x,t) = \frac{1}{\sqrt{2 \pi}} \int_{-\infty}^\infty dk g(k,0) \exp [i k x - i \omega (k) t]$$

$$\omega(k) = \frac{\bar{h} k^2}{2 m}$$

The angular frequency corresponds to the energy:

$$E = \bar{h} \omega = \frac{(\bar{h} k)^2}{2 m} = \frac{p^2}{2 m}$$

If $\omega$ had been just proportional to $k$ (and not to $k^2$) then 
$\Psi (x,t) = \frac{1}{\sqrt{2 \pi}} \int_{-\infty}^\infty dk g(k,0) \exp [i k x - i \omega (k) t]$ would represent a wave packet traveling at constant velocity without any change in the form of the packet.
But because the $k^2$-dependence the wave packet slowly broaden as it proceeds in time.

## Narrow distribution

Let us assume that $g(k,0)$ is a narrow distribution around a constant $k_0$, and write

$$k^2 = k_0^2 + 2 k_0 \Delta k + (\Delta k)^2$$

[Me: from $k = k_0 + \Delta k$ and $(k_0 + \Delta k)^2$.]

$$\bar{h} k_0 = m v$$

[Me: from $p = m v$ and $p = \bar{h} k$.]

In these terms the wave function can be written as 

$$\Psi (x,t) = \frac{1}{\sqrt{2 \pi}} \exp [ i k_0 (x - \frac{1}{2} v t)] + \int_{-\infty}^\infty d \Delta k g(\Delta k, t) \exp [i \Delta k (x - v t)]$$

[Me: from $\omega = \frac{\bar{h} k^2}{2 m} = \frac{p k}{2 m} = \frac{1}{2} v k$.]

$$g(k,t) = g(k,0) \exp [-i \frac{\bar{h} (\Delta k)^2 t}{2 m}]$$

The factor in front of the integral is a time-dependent phase factor thtat is irrelevant for the shape of the density distribution since it cancels in $\Psi^\ast \Psi$.
The packet shape (in space) depends on $x' = x = v t$ and thus the packet travels with the _group velocity_ $v  = d \omega / d k$.
However, the packet changes shape with time. In fact, the package will always broaden unless it represents a stationary state (as a standing wave), but the latter requires an external confining potential.

Let us take a Gaussian packet with initial variance of $\sigma_0^2$ and with velocity $v$ (i.e., $\langle k \rangle = k_0$) as an example.
Its initial description (disregarding normalizing factors) is

$$\Psi(x, 0) \propto \exp \left[ - \frac{x^2}{4 \sigma_0^2} + i k_0 x \right]$$

$$g(k,0) \propto \exp [ - \sigma_0^2 (\Delta k)^2]$$

The wave function $\Psi(x' = x - v t, t)$ is, apart from the phase factor, equal to the inverse Fourier transform in $\Delta k$ of $g(k,t)$ of $g(k,t) = g(k,0) \exp [-i \frac{\bar{h} (\Delta k)^2 t}{2 m}]$:

$$g(k, t) \propto \exp \left[ - \left( \sigma_0^2 + i \frac{\bar{h} t}{2 m} \right) (\Delta k)^2 \right]$$

which works out to

$$\Psi(x, t) \propto \exp \left[ - \frac{x'^2}{4 (\sigma_0^2 + i \bar{h} t /2m)} \right]$$

The narrower the initial package, the faster it will spread.

By evaluating $\Psi^\ast \Psi$, we see that a Gaussian density is obtained with a variance $\sigma(t)$ that changes in time according to

$$\sigma^2(t) = \sigma_0^2 \left( 1 + \frac{\bar{h}^2 t^2}{4 m^2 \sigma_0^4} \right)$$

---

# Relativistic energy relations for a free particle

The relation between energy and momentum (for a free particle) that we used in the previous section is incorrect for velocities that approach the speed of light.
In non-relativsitic physics we assume that the laws of physics are invariant for a translation of the spatial and time origins of our coordinate system and also for a rotation of the coordinate system; this leads to fundamental conservation laws for momentum, energy, and angular momentum, respectively.

In the theory of special relativity the additional basic assumption is that the laws of physics, including the velocity of light, are also invariant if we transform our coordinate system to one moving at a constant speed with respect to the original one.
Where for normal rotations in 3D-space we require that the square of length elements $(d\mathbf{r})^2$ is invariant, the requirement of the constant speed of light implies that for transformations to a moving frame $(c d \tau)^2 = (c d t)^2 - (d \mathbf{r})^2$ is invariant. For $1+1$ dimensions where we transform from $(x,t)$ to $x'$, $t'$ in a frame moving with velocity $v$, this leads to the _Lorentz transformation_

$$\begin{bmatrix}x' ;\\ c t' \end{bmatrix} = \begin{bmatrix} \gamma & - \gamma v/c ;\\ -\gamma v /c & \gamma \end{bmatrix} \begin{bmatrix} x ;\\ c t\end{bmatrix}$$

where

$$\gamma = \frac{1}{\sqrt{1 - v^2/c^2}}$$

In _Minkovsky space_ of $1+3$ dimensions $(ct, x, y, z) = (c t, \mathbf{r})$ vectors are _four-vector_ $v_\mu = (v_0, \mathbf{v}) (\mu = 0, 1, 2, 3)$ and we define the scalar or inner product of two four-vectors as

$$v_\mu w_\mu \equiv v_0 w_0 - v_1 w_1 - v_2 w_2 - v_3 w_3 = v_0 w_0 - \mathbf{v} \cdot \mathbf{w}$$

The notation $v_\mu w_\mu$ uses the Einstein summation convetion ($\sum_{\mu=0}^3$ over repeating indices is assumed, taking the signs into account as in v_\mu w_\mu \equiv v_0 w_0 - v_1 w_1 - v_2 w_2 - v_3 w_3$).
The square magnitude or length of a four-vector is the scalar productwith itself; not that such a square length may be positive or negative.
Lorentz transformations are all transformations in Minkowski space that leave $d x_\mu  d x_\mu = (c d \tau)^2$ invariant; they of course include all space-like rotations for which $d \tau = 0$.
Vectors that represent physical quantities are invariant for Lorentz transformations, and hence their scalar products and square magnitudes are constants.

Without any derivation, we list a number of relevant physical four-vectors, as they are defined in relativistic mechanics:

* coordinates: $x_\mu = (c t, \mathbf{r})$;
* wave vector: $k_\mu = (\omega/c, \mathbf{k})$;
* velocity: $u_\mu = (\gamma c, \gamma \mathbf{v})$;
* momentum: $p_\mu = m u_\mu = (\gamma m c, \gamma m \mathbf{v})$.

Here $m$ is the (rest) mass of the particle. The first component of the momentum four-vector is identified with the energy $E/c$, so that $E = \gamma m c^2$.
Note the following constant square lengths:

$$u_\mu u_\mu = c^2$$

$$p_\mu p_\mu = \frac{E^2}{c^2} - \mathbf{p}^2 = m^2 c^2$$

or

$$E^2 = m^2 c^4 + \mathbf{p}^2 c^2 $$

This is the relation between energy and momentum that we are looking for.
From the quadratic form it is immediately clear that $E$ will have equivalent positive and negative solutions,
one set around $+ m c^2$ and the other set around $- m c^2$.
Only the first set corresponds to the solutions of the non-relativistic equation.

Now identifying $E$ with $i \bar{h} \partial / \partial t$ and $\mathbf{p}$ with $-i \bar{h} \nabla$ , we obtain the _Klein-Gordon equation_

$$\left[ \left( - \frac{\partial^2 }{c^2 \partial t^2} + \nabla^2 \right) + \left( \frac{m c}{h} \right)^2 \right] \Psi = 0$$

This equation has the right relativistic symmetry (which the Schro\:dinger equation does not have), 
but unfortunately no solutions with real scalar densities $\Psi^ \ast \Psi$ exist.

Dirac devised an ingeneous way to linearize $E^2 = m^2 c^4 + \mathbf{p}^2 c^2 $.
Let us first consider the case of one spatial dimension, where motion is allowed only in the $x$-direction, and angular momentum cannon exist.
Instead of taking a square root of $E^2 = m^2 c^4 + \mathbf{p}^2 c^2 $, which would involve the square root of the operator $\hat{p}$, one can devise a two-dimensional _matrix equation_ which in fact equals a set of equations with multiple solutions:

$$i \bar{h} \frac{\partial \mathbf{\Psi}}{\partial t} = c (\mathbf{\alpha} \hat{p} + \mathbf{\beta} m c) \mathbf{\Psi} = \hat{\mathbf{H}} \mathbf{\Psi} $$

where $\mathbf{\Psi}$ is a two-component vector, and $\mathbf{\alpha}$ and $\mathbf{\beta}$ are dimensionless Hermitian $2 \times 2$ matrices, chosen such that $E^2 = m^2 c^4 + \mathbf{p}^2 c^2 $ is satisfied for all solutions of $i \bar{h} \frac{\partial \mathbf{\Psi}}{\partial t} = c (\mathbf{\alpha} \hat{p} + \mathbf{\beta} m c) \mathbf{\Psi} = \hat{\mathbf{H}} \mathbf{\Psi} $:

$$(\mathbf{\alpha} \hat{p} + \mathbf{\beta} m c)^2 = (\hat{p}^2 + m^2 c^2) \mathbf{1}$$

This implies that

$$\mathbf{\alpha}^2 \hat{p}^2 + (\mathbf{\alpha} \mathbf{\beta} + \mathbf{\beta} \mathbf{\alpha}) m c \hat{p} + \mathbf{\beta}^2 m^2 c^2 = (\hat{p}^2 + m^2 c^2 ) \mathbf{1}$$

or

$$\mathbf{\alpha}^2 = \mathbf{1}$$
