# Plasma fluid models and MHD
[[Plasma physics]]


## Fluid equations
We take "moments" of the Boltzmann or Vlasov equation, i.e. we multiply the equation with "1", "$m_S v$", and "$m_S v^2/2$" and integrate. This procedure es explained in [[Taking moments of distribution function]].


We get a
- continuity equation
- momentum equation
- Temperature/Energie equation

this system can then be closed using [[Maxwell equations]]. 
The Bragiinski equations are also a way to close the system.
For multi-fluid models, you pose the above equations for each particle species!
See equations in chapter 4.1 of [2]


## MHD
Assume
- characteristic length scales >> $\lambda_{D}$
- characteristic frequencies << $\omega_{gyro}$ / electrons react infinitely fast to forces on them / $m_e \to 0$
- mean fluid velocity equals ion velocity (comes from $m_e\to 0$)
- two species only: ions and electrons with opposite charge of equal magnitude
- plasma fully ionized
See equations in chapter 4.2 and 4.3 of [2]

## Ideal MHD
Assume
- $\vec{u}<<v_{th,ion}$ 
- high collisionality / short "energy equilibration time"
- $r_{gyro}$ small compared to system size
- Low resistivity, plasma "frozen" in field lines
- Plasma is magnetized
- neglect RHS some terms
$$
\begin{aligned}
\frac{\partial \rho}{\partial t}+\vec{\nabla} \cdot(\rho \vec{u})&=0 \\
\rho \frac{d \vec{u}}{d t}-\vec{J} \times \vec{B}+\vec{\nabla} P&=0 \\
\vec{E}+\vec{u} \times \vec{B}&=0 \\
\frac{d}{d t}\left(\frac{P}{\rho^\gamma}\right)&=0 \\
\vec{\nabla} \cdot \vec{B}&=0 \\
\vec{\nabla} \times \vec{E}&=-\frac{\partial \vec{B}}{\partial t} \\
\vec{\nabla} \times \vec{B}&=\mu_0 \vec{J}
\end{aligned}
$$
where $J$ is the current density, and $P$ is the MHD pressure.


## Sources
1. EPFL - Introduction to Plasma Physics
2. McGreivy -General Plasma Physics, Princeton lecture notes 2017