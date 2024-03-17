# Berendsen 2007

Herman J. C. Berendsen, Simulating the Physical World, Cambridge University Press 2007

## A modeling hierarchy

* Level 1: Relativistic quantum dynamics
  * System: atomic nuclei (mass, charge, spin), electrons (mass, charge, spin), photons (frequency)
  * Rules: relativistic time-dependent quantum mechanics; Dirac's equation; (quantum) electrodynamics
  * Approximation: Particle velocities small compared to velocity of light
    * No go: electrons close to heavy nuclei; hot plasmas 
* Level 2: Quantum dynamics
  * System: atomic nuclei, electrons, photons
  * Rules: non-relativistic time-dependent Schroedinger equation; time-independent Schrodinger equation; Maxwell equation 
  * Approximation: Born-Oppenheimer approx: electrons move much faster than nuclei
* Level 3: Atomic quantum dynamics
  * System: atoms, ions, molecules, (photons)
  * Rules: atoms move in effective potential due to electrons; atoms may behave according to time-dependent Schrodinger equation
  * Approximation: Atomic motion is classical
* Level 4: Molecular dynamics
  * System: condensed matter: (macro)molecules, fluids, solutions, liquid crystals, fast reactions
  * Rules: classical mechanics (Newton's equations); statistical mechanics; molecular dynamics
  * Approximation: Reduce number of degrees of freedom
* Level 5: Generalized Langevin dynamics on reduced system
  * System: condensed matter: large molecular aggregates, polymers, defects in solids, slow reactions
  * Rules: superatoms, reaction coordinates; averaging over local equilibrium, constraint dynamics, free energies and potentials of mean force.
  * Approximation: Neglect time correlation and/or spatial correlation in fluctuations
* Level 6: Simple Langevin dynamics
  * System: "slow" dynamic (non-equilibrium) processes and reactions
  * Rules: accelerations given by systematic force, friction, and noise; Fokker-Planck equations
  * Approximation: Neglect inertial terms: coarse graining in time
* Level 7: Brownian dynamics
  * System: coarse-grained non-equilibrium processes; colloidal systems; polymer systems
  * Rules: velocities given by force and friction, plus noise; Brownian (diffusive) dynamics; Onsager flux/force relations
  * Approximation: Reduce description to continuous densities of constituent species
* Level 8: Mesoscopic dynamics
  * System: self-organizing systems; reactive non-equilibrium systems
  * Rules: density desciption: mass conservation plus dynamic flux equation, with noise
  * Approximation: Average over "infinite" number of particles
* Level 9: Reactive fluid dynamics
  * System: non-equilibrium macroscopic mixture of different species (as the atmosphere for weather forecasting)
  * Rules: energy, momemtum and mass conservation; reactive fluxes
  * Approximation: Reduced to one species with Newtonian viscosity
* Level 10: Fluid dynamics
  * System: non-equilibrium macroscopic fluids; gases and liquids
  * Rules: energy, momentu and mass conservation; Navier-Stokes eqaution
  * Approximation: Low fluid velocities (low Reynolds number)
    * No go: turbulance
* Level 11: Steady-flow fluid dynamics
  * System: non-equilibrium fluids with laminar flow
  * Rules: simplified Navier-Stokes equation
