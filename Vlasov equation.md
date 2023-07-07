we talk about a kinetic description of [[Plasma, Magnetohydrodynamics (MHD)]].
we derive the Vlasov equation from the Boltzmann equation, see [[Kinetic plasma model, Boltzmann equation]].


## Derivation from Boltzmann equation
$$
\frac{\partial f_S}{\partial t}+\vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}+\frac{q_S}{m_S}\left(\vec{E}^{l . r_s}+\vec{v} \times \vec{B}^{l . r .}\right) \cdot \frac{\partial f_S}{\partial \vec{v}}=\left(\frac{\partial f}{\partial t}\right)_c
$$
If collisions can be neglected $\left(n \lambda_D^3 \ggg 1\right) \Rightarrow\left(\frac{\partial f}{\partial t}\right)_c=0$
$$
\frac{\partial f_S}{\partial t}+\vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}+\frac{q_S}{m_S}\left(\vec{E}^{l . r .}+\vec{v} \times \vec{B}^{l . r .}\right) \cdot \frac{\partial f_S}{\partial \vec{v}}=0 \quad \text { Vlasov equation }
$$
For simplicity of notation $\vec{E}^{l . r_{.}} \rightarrow \vec{E}, \vec{B}^{l . r .} \rightarrow \vec{B}$
Vlasov equation is coupled to Maxwell equations
$$
\rho=\sum_S q_S \int \mathrm{d} \vec{v} f_S(\vec{r}, \vec{v}, t) \quad \vec{j}=\sum_S q_S \int \mathrm{d} \vec{v} \vec{v} f_S(\vec{r}, \vec{v}, t)
$$



## Conservation laws

$$
\frac{\partial f_S}{\partial t}+\vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}+\frac{q_S}{m_S}(\vec{E}+\vec{v} \times \vec{B}) \cdot \frac{\partial f_S}{\partial \vec{v}}=0
$$
Conservation of total number of particles
$$
\begin{aligned}
\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \text { Vlasov } & \Rightarrow \underbrace{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \frac{\partial f_S}{\partial t}}_{\frac{\partial}{\partial t} \int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} f_S=\frac{\mathrm{d}}{\mathrm{dt}} N_S}+\underbrace{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}}_{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \frac{\partial}{\partial v} \cdot\left(\vec{v} f_S\right)=0}+\underbrace{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \frac{q_S}{m_S}(\vec{E}+\vec{v} \times \vec{B}) \cdot \frac{\partial f_S}{\partial \vec{v}}}_{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \frac{\partial}{\partial \vec{v}} \cdot\left[\frac{q_S}{m_S}(\vec{E}+\vec{v} \times \vec{B}) f_S\right]=0}=0 \\
& \Rightarrow \frac{\mathrm{d} N_S}{\mathrm{~d} t}=0
\end{aligned}
$$
Conservation of momentum
$\vec{P}_{\text {tot }}=\vec{P}_{\text {particles }}+\vec{P}_{\text {fields }}=\sum_S m_S \int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \vec{v} f_S+\epsilon_0 \int \mathrm{d} \vec{r}(\vec{E} \times \vec{B}) \quad$ is conserved
Conservation of energy
$E_{\text {tot }}=E_{\text {particles }}+E_{\text {fields }}=\sum_S \int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \frac{1}{2} m_S v^2 f_S+\frac{1}{2} \int \mathrm{d} \vec{r}\left(\epsilon_0 E^2+\frac{B^2}{\mu_0}\right) \quad$ is conserved
Entropy is conserved
$S=-\sum_S \int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} f_S \ln f_S$
$\frac{\mathrm{d} S}{\mathrm{~d} t}=-\sum_S \int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v}\left(\frac{\partial f_S}{\partial t} \ln f_S+\frac{\partial f_S}{\partial t}\right)=0 \quad \Rightarrow \begin{aligned} & \text { Vlasov equation describes } \\ & \text { time-reversible processes }\end{aligned}$
(collisions are neglected)



## Interpretation of Vlasov equation

The motion of $f_S$ is incompressible
$$
\nabla_{6 D} \cdot \vec{u}=\frac{\partial}{\partial \vec{r}} \cdot \vec{v}+\frac{\partial}{\partial \vec{v}} \cdot \frac{\vec{F}}{m_S}=0
$$
Variation of $f_S$ along the particle orbits
$$
\begin{aligned}
\left.\frac{\mathrm{d} f_S}{\mathrm{~d} t}\right|_{\text {orbit }} & =\frac{\partial f_S}{\partial t}+\left.\frac{\mathrm{d} \vec{r}}{\mathrm{~d} t}\right|_{\text {orbit }} \cdot \frac{\partial f_S}{\partial \vec{r}}+\left.\frac{\mathrm{d} \vec{v}}{\mathrm{~d} t}\right|_{\text {orbit }} \cdot \frac{\partial f_S}{\partial \vec{v}} \\
& =\frac{\partial f_S}{\partial t}+\vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}+\frac{\vec{F}}{m_S} \cdot \frac{\partial f_S}{\partial \vec{v}}=\frac{\partial f_S}{\partial t}+\vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}+\frac{q_S}{m_S}(\vec{E}+\vec{v} \times \vec{B}) \cdot \frac{\partial f_S}{\partial \vec{v}} \underset{\text { Vlasov }}{=} 0
\end{aligned}
$$
$\Rightarrow f_S$, as measured when moving along a particle trajectory, is constant




## Solutions of Vlasov equation
If $C_j$ are constants of motion, $j=1,2, \ldots, J$, then $f_S\left(C_1, C_2, \ldots, C_J\right)$ is a solution of Vlasov equation. In fact
$$
\frac{\partial f_S}{\partial t}+\vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}+\frac{q_S}{m_S}(\vec{E}+\vec{v} \times \vec{B}) \frac{\partial f_S}{\partial \vec{v}}=\left.\frac{\mathrm{d} f_S}{\mathrm{~d} t}\right|_{\text {orbit }}=\underbrace{\left.\frac{\partial f_S}{\partial C_1} \cdot \frac{\mathrm{d} C_1}{\mathrm{~d} t}\right|_{\text {orbit }}}_{=0}+\underbrace{\left.\frac{\partial f_S}{\partial C_2} \cdot \frac{\mathrm{d} C_2}{\mathrm{~d} t}\right|_{\text {orbit }}}_{=0}+\ldots+\underbrace{\left.\frac{\partial f_S}{\partial C_J} \cdot \frac{\mathrm{d} C_J}{\mathrm{~d} t}\right|_{\text {orbit }}}_{=0}=0
$$
Examples
- $\vec{E}=0=\vec{B} \Rightarrow v_x, v_y, v_z$ are constants of motion $\Rightarrow f_S=f_S\left(v_x, v_y, v_z\right)$ is solution of Vlasov
- $\vec{E}=0, \vec{B}=B_0 \hat{e}_z \quad \Rightarrow \quad v_z, v^2, v_y+\frac{q_S B_0}{m_S} x, v_x-\frac{q_S B_0}{m_S} y$ are constants
$$
\Rightarrow f_S=f_S\left(v_z, v^2, v_y+\frac{q_S B_0}{m_S} x, v_x-\frac{q_S B_0}{m_S} y\right) \text { is solution of Vlasov }
$$
Observations
- Contrast to Boltzmann equation, where Maxwellian is the only stationary solution
- Very difficult to find the constants of motion




## Sources
- EPFL - Introduction to Plasma Physics, lecture 2d)
