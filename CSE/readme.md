# Computational Science and Engineering

---
# To do

* Simulation
> Simulation has become a "third way" of doing science, not instead of, but in addition to theory and experimentation.
> There is a dander, however, that applied scientists will use "standard" simulation methods, or even worse use "black-box" software, without realizing on what assumption the methods rest and what approximations are implied."
> This book is meant to provide the ncessary scientific background and to promote awareness for the limitations and inaccuracies of simulating the "real world".

---Herman J. C. Berendsen, Simulating the Physical World, Cambridge University Press 2007.


  * Dynamic vs Static
    * Static
      > "Not all questions we endeavor to answer involve dynamic aspects, such as the prediction of static equilibrium properties (e.g., the binding constant of a ligand to a macromolecule or a solid surface). For such static questions the answers may be found by sampling methods, such as Monte Carlo simulations, that generate a representative statistical ensemble of system configurations rather than a trajectory in time." Berendsen(2007)
    * [Dynamic](https://github.com/tatpongkatanyukul/iExplore/tree/main/QuantumSimulation)
       > "The precise details of a particular trajectory of the particles have no relevance for the problem we wish to  solve. What we need is always an average over many trajectories, or at least an average property, such as a the average or variance of a single observable or a correlation function, over one long trajectory." Berendsen(2007)

* Interpolation
> In many occasions we may not even have an analytical form for the potential, but know the potential at a number of discrete points, e.g., from quantum-chemical calculations. In that cse the best way to proceed is to construct the potential function from _cubic spline interpolation_ of the computed points.

## Optimization example
  * Berendsen (2007), pp. 6: Morse function, approximate potential function $V(r) = D (1 - e^{-a (r - b)})^2$.
    * $D$ is the dissociation energy (569.87 kJ/mol); $a$ is a constant related to the steepness of the potential (Example uses $a = 2/b$); $b$ equilibrium bond length (0.09169 nm); $k$ force constant ($5.85 \times 10^5$ kJ mol<sup>-1</sup> nm<sup>-2</sup>). 

---
# Done
