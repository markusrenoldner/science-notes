# Potential vs potential energy


Potential vs potential energy in electrostatic/[[Electrodynamics]] and in [[Classical mechanics]]


## Mechanics
Scalar potential $\phi$:
$$\begin{aligned}
    F&=-\nabla \phi(x)\\
    [F] &= \frac{mL}{t^2} \\
    [\phi]&= \frac{mL^2}{t^2}
\end{aligned}$$
Potential energy $V$:
$$\begin{aligned}
    V&= mgh\\
    \text{because: }\quad V&= \int _0^h F_g ds = \int_0^h mg ds = mgh\\
    [V]&= m\frac{L}{t^2} L= \frac{mL^2}{t^2} = [\phi]
\end{aligned}$$
Somehow, in mechanics the scalar potential of the force field is the same as the potential energy.

## Electrostatics:

Define electric field and force:
$$\begin{aligned}
    E &= -\nabla \phi\\
    F &= qE\\
    \implies F &= q\cdot (-\nabla\phi)\\
\end{aligned}$$
Potential
$$V = \int_0^h Fds = \int qEds = \int q(-\nabla\phi)ds = -q \left ( \phi(h) - \phi(0) \right )$$
Choose $\phi(0)=0$ and get
$$
    V(h) =-q\phi(h)
$$
In electrostatics, the potential energy is the charge times the potential.

## Mechanics fixed:

Define potential as 
$$
    F\equiv -m\nabla \phi(x)
$$

this makes mechanical potentials consistent with electrostatic potentials.

