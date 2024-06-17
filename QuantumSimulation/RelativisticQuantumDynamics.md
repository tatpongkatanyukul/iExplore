# Relativistic Quantum Dynamics

---

* [Level 1: Relativistic quantum dynamics](https://github.com/tatpongkatanyukul/iExplore/blob/main/QuantumSimulation/RelativisticQuantumDynamics.md)
  * System: atomic nuclei (mass, charge, spin), electrons (mass, charge, spin), photons (frequency)
  * Rules: relativistic time-dependent quantum mechanics; Dirac's equation; (quantum) electrodynamics
  * Approximation: Particle velocities small compared to velocity of light
    * No go: electrons close to heavy nuclei; hot plasmas 

---

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
> * $ \langle \mathbf{p} \rangle = \int d \mathbf{r} \Psi^\ast (\mathbf{r}, t) (- i \bar{h} \nabla) \Psi (\mathbf{r}, t)$
> * $ \langle p^2 \rangle = \int d \mathbf{r} \Psi^\ast (\mathbf{r}, t) (- \bar{h}^2 \nabla^2) \Psi (\mathbf{r}, t)$
> * $ \langle E \rangle = \int d \mathbf{r} \Psi^\ast (\mathbf{r}, t) (i \bar{h} \frac{\partial}{\partial t}) \Psi (\mathbf{r}, t)$
