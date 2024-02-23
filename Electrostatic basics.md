# Electrostatic basics


## Coulomb's law

The (Coloumb) force acting between two electrically charged particles is
$$\vec{F}=\frac{1}{4\pi \epsilon_0} \frac{q_1 q_2}{r^3}\vec{r}$$
The Electric field $E(=\frac{1}{\epsilon }D)$ around a testcharge $q$ is defined as
$$\vec{E}:=\frac{\vec{F}}{q}$$
The electric flux is defined as 
$$\Phi_{el}:=\int_{\partial \Omega} \vec{E}\cdot e_n = \int_\Omega \nabla\cdot\vec{E}$$
here $\partial \Omega$ is the boundary area of the domain $\Omega$. If we plug in the electric field, we get
$$\int_{\partial \Omega} \vec{E} = \frac{Q}{4\pi \epsilon_0}\int_{\partial\Omega}\frac{\vec{r}}{r^3}=\frac{Q}{\epsilon_0}\implies \Phi_{el}=\frac{1}{\epsilon_0}\int_{\Omega} \rho$$
(we integrate over surface of sphere $\partial\Omega$)
with $\rho$ being the charge density. $\Omega$ is arbitrary, therefore we follow
$$\nabla\cdot \vec{E} = \frac{\rho}{\epsilon_0}$$
which is **Mx1/Gauss' law**, see [[Maxwell equations]]. 
The work acting on a particle along a curve $C$ in the force field is then
$$W:=\int_C \vec{F}$$
If $\vec{E}$ is conservative, a scalar potential can be defined:
$$-\nabla\phi:=\vec{E}$$
This gives the Poisson equation
$$\Delta \phi = \frac{\rho}{\epsilon_0}$$
Integrating this definition along a curve $C$ gives the voltage $U$:
$$\phi_1 - \phi_2 = \int_C \vec{E} =: U$$
The voltage is therefore the difference in potential.

## Bfield stuff

The magnetic field is denoted $B(=\mu H)$, and the magnetic flux through the surface $S$ is
$$
    \Phi_m = \int_S B\cdot dA
$$
Magnetic flux over a closed surface
$$
    \oint_{\partial \Omega} B\cdot dA = 0 
$$
from this we get the **Mx3/Gauss' law for Magnetism**
$$
    \operatorname{div} (B) =0
$$
**Mx4/Ampere's law** (can be shown experimentally):
$$\begin{aligned}
    \oint_C B\cdot ds &= \mu_0 \cdot I = \mu_0\int j\cdot dA \\
    \implies \operatorname{curl}(B) &= \mu_0 j
\end{aligned}$$

B-field of stationary currents (Biot-Savart law)
$$B(r)=-\frac{\mu_0 I}{4\pi} \int \frac{ds\times e_r}{r^2}$$

**Mx2/Faraday's law of induction** (can be shown experimentally):
$$
\begin{rcases}
    U_{ind} = -\partial_t \Phi_m\\
    \displaystyle
    U = \int_C E\cdot ds
\end{rcases} \implies \operatorname{curl} E = -\partial_t B
$$

In static fields, $\int E\cdot ds=0$ and we get $\operatorname{curl} E=0$.

## Displacement current (extension of Mx4)

In the case of a circuit with capacitor, like shown here:

![[displacement-current-Mx4.png]]

we face a problem with Mx4. The current $j=0$ in the capacitor obviously. But there is still a magnetic field due to the current in the wire. The current after the capacitor is non-zero, so we introduce a "virtual" current, the "displacement current" which discribes this phenomenon,
$$
    j_d \equiv \epsilon_0 \partial_t E,
$$
and we get an extended **Mx4**
$$
    \oint_C B\cdot ds = \mu_0 \int (j + j_d) \implies \operatorname{curl}B=\mu_0 j+\mu_0\epsilon \partial_t E
$$


## Sources:
- Demtröder - Experimentalphysik 2, Elektrizität und Optik
- Lecture 12, Grundlagen Physik 2b, TUWien, 2019

