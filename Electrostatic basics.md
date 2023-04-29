

## Coulomb's law
The force acting between two electrically charged particles is
$$\vec{F}=\frac{1}{4\pi \epsilon_0} \frac{q_1 q_2}{r^3}\vec{r}$$
The Electric field around a testcharge $q$ is defined as
$$\vec{E}:=\frac{\vec{F}}{q}$$
The electric flux is defined as 
$$\Phi_{el}:=\int_{\partial \Omega} \vec{E} = \int_\Omega \nabla\cdot\vec{E}$$
here $\partial \Omega$ is the boundary area of the domain $\Omega$. If we plug in the electric field, we get
$$\int_{\partial \Omega} \vec{E} = \frac{Q}{4\pi \epsilon_0}\int_{\partial\Omega}\frac{\vec{r}}{r^3}=\frac{Q}{\epsilon_0}\implies \Phi_{el}=\frac{1}{\epsilon_0}\int_{\Omega} \rho$$
#todo explain how the integral is solved

with $\rho$ being the charge density. $\Omega$ is arbitrary, therefore we follow
$$\nabla\cdot \vec{E} = \frac{\rho}{\epsilon_0}$$
which is Gauss' law, and one of the famous [[Maxwell equations]]. 
The work acting on a particle along a curve $C$ in the force field is then
$$W:=\int_C \vec{F}$$
If $\vec{E}$ is conservative, a scalar potential can be defined:
$$\nabla\phi:=\vec{E}$$
This gives the Poisson equation
$$\Delta \phi = \frac{\rho}{\epsilon_0}$$
Integrating this definition along a curve $C$ gives the voltage $U$:
$$\phi_1 - \phi_2 = \int_C \vec{E} =: U$$
The voltage is therefore the difference in potential.

#TODO complete







## Sources:
- Demtröder - Experimentalphysik 2, Elektrizität und Optik


