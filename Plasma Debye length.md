
plasma is neutral, i.e. same number of electrons and ions per unit volume: $n_e$ and $n_i$ 
potential around test charge $q_T$:
$$\nabla^2 \Phi = -\frac{1}{\epsilon_0}\left(q_T\delta(\vec{r}) + e n_i(\vec{r})+en_e(\vec{r})\right)$$
(This comes from $\nabla \cdot E=\frac{q_{T}}{\epsilon_0}$ , see [[Maxwell equations]]). Ions are "fixed with background", i.e. $n_0:=n_i(\vec{r})$, but electrons move goverend by:
$$\begin{align}m_e \partial_t \vec{u}_e &= -e \vec{E} -1\frac{1}{n_e}\nabla p \\&= -e \vec{E} -1\frac{1}{n_e} \nabla(n_e k_B T_e)\end{align}$$
here $k_B$ is the Boltzmann constant, and it will be symbolically incorporated into the temperature: $T_e:=k_{B}T_e$
assume $m_e\rightarrow 0$, $\vec{E}=-\nabla \Phi$ , and $T_{e}= const.$ :
$$\begin{align*}
0=&e\nabla \Phi - T_{e}  \frac{\nabla n_{e}}{n} = \nabla (e \Phi -T_{e}\text{ log}(n_{e) )}\\\\
\implies & n_e=n_{0} \text{ exp}(\frac{e\Phi}{ T_{e}})
\end{align*}$$
plugging this into the potential:
$$\nabla^2 \Phi = -\frac{1}{\epsilon_0}\left(q_T\delta(\vec{r}) + e n_0(\vec{r})-e n_{0} \text{ exp}(\frac{e\Phi}{ T_{e}} \right)$$
the last term will be Taylor-expanded/linearized for $\Phi$:
$$\begin{align*}
\nabla^2 \Phi &=-\frac{1}{\epsilon_{0}} q_T\delta(\vec{r}) +\frac{1}{\epsilon_{0}} \frac{e^2n_{0}}{\epsilon_{0}T_e}\Phi\\
&=- \frac{1}{\epsilon_{0}} q_T\delta(\vec{r}) + \frac{1}{\lambda_{Dl}^2}\Phi
\end{align*}$$
with the electron Debye length defined as
$$\lambda_{Dl} := \sqrt{\frac{\epsilon_{0}T_{e}}{e^2n_0}}$$
The linearized equation for the electrostatic potential can be solved (in spherical coordinates):
$$\Phi(r) = \frac{1}{4\pi \epsilon_{0}}\frac{q_{T}}{r} \text{ exp}(-r/\lambda_{Dl})$$
in green we see the Coulomb potential (without the exponential term). If $r$ approaches the order of magnitude of the Debye length, the potential deviates from that, see in red.
![[MHD-potential-testcharge.png]]
The plasma therefore "screens" the potential of the charged particle. The potential is also called "Debye screened potential". In this derivation, we have assumed, that the number of particles in a Debye cube $N_D:=n\lambda_{Dl}^{3}$ is "large". If this isnt fulfilled, we would have to calculate single particles.

Conclusions:
- deviation from quasi-neutrality ($n_{e\neq}n_0$) occurs at distances smaler than the Debye length (valid if $N_0$ "large")
- the Taylor-expansion/linearization is only accurate if the argument of the exponential function $\frac{e\Phi}{T_e}$ is "small". As $\Phi$ is large for small $r$, we check $\Phi$ at the minimal distance between particles:  $r_{min} = \sqrt[3]{\frac{1}{n_0}}$  (below that, the equation for $\Phi$ isnt meaningful). Using the Coulomb potential approximation (i.e. ignoring the exponential term), this gives $\Phi_{max}=\frac{1}{4\pi \epsilon_{0}}\frac{e}{r_{min}} = \frac{1}{4\pi \epsilon_{0}} en_0^{\frac{1}{3}}$. We follow that $$\frac{e \Phi_{max}}{ T_{e}}=\frac{1}{4\pi \epsilon_{0}} \frac{e^2n_0^{\frac{1}{3}}}{T_e} = \frac{1}{4\pi N_D^{\frac{2}{3}}},$$ which is "small".
- One-to-one interactions are therefore weak if $N_D$ is "large", as then the potential between two particles is small (see result of previous bullet point).