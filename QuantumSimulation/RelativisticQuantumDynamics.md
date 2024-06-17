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
