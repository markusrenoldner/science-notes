we talk about how to control [[Plasma physics]]

Due to the cyclotron motion (see [[Particle motion in static uniform magnetic fields]], the $B$-field confines charged particles normal to it, but not along/parallel to it.


We have two options:
1. "open" field lines (locally open): A circular current will create the following axially-symmetric $B$-field:
![[magnetic-mirror.png]] 
This principle is used by "magnetic mirrors".
2. Closed field lines: this principle is used in tokamaks and stellerator fusion reactors:
![[tokamak-confinement-principle.png]]


## 1. Open field lines/Magnetic mirror principle
Cross section of magnetic mirror:
![[magnetic-mirror-crosssection.png]]
Useful: polar coordinates $r,\theta,z$
Focus on particles with guiding center on axis (can be generalized to particles that move along the other field lines)

Consider z-component of $v\times B$-force/Lorentz force: $$F_z = q(v\times B) = |q|v_\perp B_r$$where $v_\perp$ is the velocity normal to $B$. Since (B divergence-free) 
$$\begin{align}
    &\nabla\cdot B = \frac{1}{r}\partial_r (rB_r) + fr\partial_z B_z = 0 
\end{align}$$
with $B_z >> B_r$, and $B_r(r=0) = 0$. We can integrate this to get $$B_r = -\frac{r}{2} \partial_z B_z \approx -\frac{r}{2}|\nabla B| \implies F_z = -|q| v_\perp \frac{1}{2}\underbrace{r}_{\approx \rho} |\nabla B| = -\underbrace{\frac{m v_\perp^2}{2B}}_{=\mu}|\nabla B|$$where $\rho$ is the cyclotron radius and $\mu$ is the magnetic moment.

What particles can confined by this idea?
We realized that $\mu=const$ in [[Particle motion in static uniform magnetic fields]]:
$$\begin{align}
    \mu &= const = \frac{1}{2} \frac{m v_{\perp,c}^2}{B_{min}}=\frac{1}{2} \frac{m v_{\perp,e}^2}{B_{min}} \\
    E_{kin} &= const = \frac{1}{2}m (v^2_{\perp,c}+v^2_{\parallel,c}) = \frac{1}{2}m (v^2_{\perp,e}+v^2_{\parallel,e})
\end{align}$$
with $v_{c}$ being the velocity at the center of the mirror (between the electric currents), and with $v_{e}$ the velocity at the end. 
A particle is reflected if $v_\parallel$ vanishes, while moving towards $B_{max}$, which is when $E_{kin} = \frac{1}{2}m v_\perp^2$. This means $$\mu = \frac{1}{2}\frac{m v_{\perp,c}^2}{B_{min}} = \frac{1}{2}\frac{m v^2_{\perp,e}}{B_{max}} \geq \frac{m(v^2_{\perp,e} + v^2_{\parallel,e})}{2 B_{max}} =\frac{E_{kin}}{B_{max}} = \frac{1}{2} \frac{m(v^2_{\perp,c}+v^2_{\parallel,c})}{B_{max}}$$
We can compare the last and first term and conclude that reflection happens if $$\frac{v^2_{\perp,c}}{v^2_{\perp,c}+v^2_{\parallel,c}}\geq \frac{B_{min}}{B_{max}}$$this can be visualized in phase space:
![[magneticmirror-phasespace-losscones.png]]
An example of this confinement mechanism is the earths magnetic field, where particles can be pushed away from the poles along the field lines by an electric field.



## 2. Closed field lines/ Tokamak and stellerator
Closing field lines seems to trap particles completely. But its not so easy.

Amperes law see [[Maxwell equations]] yields the absolute value of the magnetic field:
$$|B| = \frac{\mu_0 N_l}{2 \pi} \frac{I}{r}$$ 
hence, $B$ is not homogeneous and it is curved: drifts are present. 

Which drifts? The curvature drift and the grad-B drift: 
$$\begin{align}
    v_d &=\frac{m v_\parallel^2}{qB^2 R_B^2}(R_B\times B) \\
    v_{\nabla B} &= \frac{m}{2B^3} \frac{v_\perp^2}{q} (B\times \nabla B)
\end{align}$$
see [[Particle motion in electromagnetic fields]]. 
- We want to find the particle dynamics in purely toroidal field (1st image).
- The drifts will add up and induce a charge-dependent motion (2nd image).
- This creates an $E$-field, generating a an "E-cross-B" drift (see [[Particle motion in electromagnetic fields]]) leading to a loss of confinement.
![[plasma-confinement-problem.png]]
A purely toroidal field can not confine particles.

Solution: create a poloidal magnetic field, that short-circuits the charge accumulation. This can be done
- by driving a current inside the plasma (Tokamak)
- by breaking the axial symmetry (Stellerator)


## Sources
- EPFL - Introduction to Plasma Physics, lecture 1f)