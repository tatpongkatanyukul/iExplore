# Electrodynamic interactions

From the relation $E = p^2/2m$ and the correspondence relations between energy or momentum and time or space derivatives we derived the non-relativistic Schro\"dinger equation for a non-interacting particle ($\frac{\partial \Psi}{\partial t} = \frac{i \bar{h}}{2 m} \frac{\partial^2 \Psi}{\partial x^2} $).
How is this equation modified if the particle moves in an external potential?

In general, what we need is the operator form of the _Hamiltonian_ $H$, which for most cases is equivalent to the total kinetic plus potential energy.
When the potential energy in an external field is a function $V(\mathbf{r})$ of the coordinates only, such as produced by a stationary electric potential, it is simply added to the kinetic energy:

$$i \bar{h} \frac{\partial \Psi}{\partial t} = - \frac{\bar{h}^2}{2 m} \nabla^2 \Psi + V(\mathbf{r}) \Psi$$

In fact, electrons feel the environment through electromagnetic interactions, in general with both an electric and a magnetic component.
If the electric field is not stationary, there is in principle always a magnetic component.
As we shall see, the magnetic component acts through the _vector potential_ that modifies the momentum of the particle.
See Chapter 13 for the basic elements of electromagnetism.

In order to derive the proper form of the electromagnetic interaction of a particle with charge $q$ and mass $m$, we must derive the _generalized momentum_ in the presence of a field.
This is done by the Lagrangian formalism of mechanics, which is reviewed in Chapter 15.
The Lagrangian $L(\mathbf{r}, \mathbf{v})$ is defined as $T - V$, where $T$ is the kinetic energy and $V$ is the potential energy.

In the case of an electromagnetic interaction, the electrical potential energy is modified with a velocity-dependent term $-q \mathbf{A} \cdot \mathbf{v}$, where $\mathbf{A}$ is the _vector potential_ related to the magnetic field $\mathbf{B}$ by

$$\mathbf{B} = \mathrm{curl} \mathbf{A}$$

in a form which is invariant under a Lorentz transformation:

$$V(\mathbf{r}, \mathbf{v}) = q \phi - q \mathbf{A} \cdot \mathbf{v}$$

Thus the Lagrangian becomes

$$L(\mathbf{r}, \mathbf{v}) = \frac{1}{2}m \mathbf{v}^2 - q \phi + q \mathbf{A} \cdot \mathbf{v}$$

The reader should verify that with this Lagrangian the Euler-Lagrange equations of motion for the components of coordinates and velocities

$$\frac{d}{d t} \left( \frac{\partial L}{\partial v_i} \right) = \frac{\partial L}{\partial x_i}$$

lead to the common Lorentz equation for the acceleration of a charge $q$ in an electromagnetic field

$$m \dot{\mathbf{v}}$$
