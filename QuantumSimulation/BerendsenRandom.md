# Section 2.5

> ...
> * _fermions_ (half-integral spin, odd parity): electron, proton, neutron, muon, positron, $^3$He nucleus, $^3$He atom, D atome;
> * _bosons_ (integral spin, even parity): deuteron, H-atom, $^4$He nucleus, $^4$He atom, H<sub>2</sub> molecule.
> The consequences for electrons are drastic! If we have two one-electron orbitals (including spin state) $\varphi_a$ and $\varphi_b$, and we put two non-interacting electrons into these orbitals (one in each), the odd parity prescribes that the total two-particle wave function must have the form
> $$\psi(1,2) \propto \varphi_a(1) \varphi_b(2) - \varphi_a(2) \varphi_b(1)$$
> So, if $\varphi_a =\varphi_b$, the wave function cannot exists!
> Hence, two (non-interacting) electrons (or fermions in general) cannot occupy the same spin-orbital.

# Section 3.1

> ...
> The essence of quantum mechanics is that particles are represented by a wave function 
> and have a certain width or uncertainty in space, related to an uncertainty in momentum.
> By a handwaving argument we can already judge whether the quantum character of a particle will play a dominant role or not.
> Consider a (nearly) classical particle with mass $m$ in an equilibrium system at temperature $T$, where it will have a Maxwellian velocity distribution (in each direction) with $\langle p^2 \rangle = m k_B T $.
> This uncertainty in momentum implies that the particle's width $\sigma_x$, i.e. the standard deviation of its wave function distribution, will exceed the value prescribed by Heisenberg's uncertainty principle:
> $$\sigma_x \geq \frac{\bar{h}}{2 \sqrt{m k_B T}}$$
> There will be quantum effects if the forces acting on the particle vary appreciably over the width of the particle.


> In condensed phases, with interparticle distance of a few $\mathring{A}$, this is the case when the width of the particle exceeds, say, $0.1 \mathring{A}$.

Table 3.1 The minimal equantum widdth in $\mathring{A}$ of the electron and some stoms at temperatures between 10 and 1000 K, derived from Heisenberg uncertainty relation. 

| Particle | m(u)     | 10 K | 30 K | 100 K | 300 K | 1000 K |
|---       |---       |---   |---   |---    |---    |---     |
|e         | 0.000545 | 47   | 27   | 15    | 8.6   | 4.7    |
|H         | 1        | 1.1  | 0.64 | 0.35  | 0.20  | 0.11   |
|D         | 2        | 0.78 | 0.45 | 0.25  | 0.14  | 0.078  |
|C         | 12       | 0.32 | 0.18 | 0.10  | 0.058 | 0.032  |
|O         | 16       | 0.28 | 0.16 | 0.087 | 0.050 | 0.028  |
|I         | 127      | 0.098| 0.056| 0.031 | 0.018 | 0.010  |

> ...
> It is clear that electrons are fully quantum-mechanical in all cases (except hot, dilute plasmas with interparticle separations of hundreds of $\mathring{A}$).
> Hydrogen and deuterium atoms are suspect at 300 K but heavier atoms will be largely classical.

# Section 4.2

> The general form of the time-dependent Schro\"dinger equation is
>
>$$i \bar{h} \frac{\partial \Psi}{\partial t} = \hat{H} \Psi$$
>
> ... stationary solutions that represent bound states:
> $\Psi_n(\mathbf{r},t) = \psi_n (\mathbf{r}) \exp \left( - \frac{i}{\bar{h}} E_n t \right)$
> where $\psi_n(\mathbf{r},t)$ and $E_n$ are solutions of the eigenvalue equation.
>
> $\hat{H} \psi(\mathbf{r}) = E \psi(\mathbf{r})$
... called the _time-independent Schro\"dinger equation.


> In chemistry the main concern is the structure and properties of single atoms and molecules; especially large molecules with many electrons pose severe computational problems and elude exact treatment.

# Section 4.3 The few-particle problem

> The Schro\"dinger equation is a _boundary-value_ problem, which acceptable solutions only existing for discrete values of $E$.
> These are called the _eigenvalues_, and the corresponding solutions the _eigenfunctions_.
> The boundary conditions are generally zero values of the wave function at the boundaries, and square-integrability of the function, i.e., $\int \psi^\ast \psi(x) dx$ must exist.
> As any multiple of a solution is also a solution, this property allows to _normalize_ each solution, such that the integral of its square is equal to one.

## Section 4.3.1 Shooting methods

The popular _shooting_ methods integrate the second-order differential equation

$$\frac{d^2 \psi(x)}{d x^2} = \frac{2 m}{\bar{h}^2} \left[ V(x) - E \right] \psi(x) $$

from one end with an estimate of the eigenvalue $E$ and iterate over changes of $E$; only when $E$ is equal to an eigenvalue will the wave function fulfill the proper boundary condition at the other end.

```
# Find the nearest eigenvalue for the single-particle Schrodinger equation

def numerov(m, E, V):
    # m : index for matching point
    # E : trial energy*mass*delx**2 / hbar**2
    # V : array of pot. energy*mass*delx**2 / hbar**2
    # returns [nr of zerocrossings, difference in relat. first derivatives]
    
    E1 = E; E2 = E1*1.05
    F1 = shoot(m, E1, V)
    while (abs(E2 - E1) > 1e-8):
        nF = shoot(m, E2, V); F2 = nF[1]
        Etemp = E2
        E2 = (F1*F2 - F2*E1)/(F1 - F2)
        print("%3d %13.10f"%(nF[0], E2))
    
    return [nF[0], E2]
```

```
def shooting(m, E, V):
    # ...
```

```
def psi(m, E, V):
    # ...
```

My note: Berendsen does not explain very much, does not even provide the example how to run code or how to put in values for the arguments.

Better chance:
* https://liu-group.github.io/interactive-Numerov-PIB/
* https://github.com/tatpongkatanyukul/iExplore/blob/main/QuantumSimulation/computational_physics.pdf
