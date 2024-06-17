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

$$\psi(\mathbf{r}, t) = c \exp[i (\mathbf{k} \cdot \mathbf{r} - \omega t)]$$

where $c$ is a complex constant, the absolute value of which is the amplitude of the wave, while its argument defines the phase of the wave.

In general, a particle may be described by a superposition of many (a continuum of) waves of different wave vector and frequency:

$$\psi(\mathbf{r}, t) = \int d \mathbf{k} \int d \omega G(\mathbf{k}, \omega) \exp[i (\mathbf{k} \cdot \mathbf{r} - \omega t)]$$

where $G$ is a distribution function of the wave amplitude in $\mathbf{k}, \omega$ space.

Here, we recognize that $\psi(\mathbf{r}, t)$ and $G(\mathbf{k},\omega)$ are each other's Fourier transform, although the sign conventions for the spatial and temporal transforms differ.

## Time-dependent wave function

Of course, the transform can also be limited to the spatial variable only, yielding a time-dependent distribution in $\mathbf{k}$-space (we introduce a factor of $(2 \pi)^{-3/2}$ for symmetry reasons):

$$\psi(\mathbf{r}, t) = (2 \pi)^{-3/2} \int d \mathbf{k}  g (\mathbf{k}, t) \exp [ i (\mathbf{k} \cdot \mathbf{r})] $$

The inverse transform is

$$g(\mathbf{k}, t) = (2 \pi)^{-3/2} \int d \mathbf{r}  \psi (\mathbf{r}, t) \exp [ - i (\mathbf{k} \cdot \mathbf{r})] $$
