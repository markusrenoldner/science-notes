we talk about a kinetic description of [[Plasma physics]].
we derive the Vlasov equation from the Boltzmann equation, see [[Kinetic plasma model, Boltzmann equation]].

## Derivation from Boltzmann equation
Take Boltzmann equation and assume large $n$ in debye cube ([[Plasma Debye length]]), which allows to neglect collisions. This gives the Vlasov equation
$$
\frac{\partial f_S}{\partial t}+\vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}+\frac{q_S}{m_S}\left(\vec{E}+\vec{v} \times \vec{B}\right) \cdot \frac{\partial f_S}{\partial \vec{v}}=0 
$$
where we denote the "long range fields" with $E,B$. Vlasov equation is coupled to Maxwell equations with the following relations (charge and current density):
$$
\rho=\sum_S q_S \int \mathrm{d} \vec{v} f_S(\vec{r}, \vec{v}, t) \quad \vec{j}=\sum_S q_S \int \mathrm{d} \vec{v} \vec{v} f_S(\vec{r}, \vec{v}, t)
$$


## Conservation laws
Conservation of total number of particles: integrate Vlasov eq. over phase space (space and velocities)
$$
\begin{align}
&\underbrace{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \frac{\partial f_S}{\partial t}}_{\frac{\partial}{\partial t} \int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} f_S=\frac{\mathrm{d}}{\mathrm{dt}} N_S}+\underbrace{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}}_{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \frac{\partial}{\partial v} \cdot\left(\vec{v} f_S\right)=0}+\underbrace{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \frac{q_S}{m_S}(\vec{E}+\vec{v} \times \vec{B}) \cdot \frac{\partial f_S}{\partial \vec{v}}}_{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \frac{\partial}{\partial \vec{v}} \cdot\left[\frac{q_S}{m_S}(\vec{E}+\vec{v} \times \vec{B}) f_S\right]=0}=0 \\
& \implies \frac{\mathrm{d} N_S}{\mathrm{~d} t}=0
\end{align}
$$
Conservation of momentum:$$\vec{P}_{\text {tot }}=\vec{P}_{\text {particles }}+\vec{P}_{\text {fields }}=\sum_S m_S \int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \vec{v} f_S+\epsilon_0 \int \mathrm{d} \vec{r}(\vec{E} \times \vec{B}) \quad$$ Conservation of energy$$E_{\text {tot }}=E_{\text {particles }}+E_{\text {fields }}=\sum_S \int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \frac{1}{2} m_S v^2 f_S+\frac{1}{2} \int \mathrm{d} \vec{r}\left(\epsilon_0 E^2+\frac{B^2}{\mu_0}\right) \quad$$
Entropy is conserved
$$\begin{align}
S&=-\sum_S \int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} f_S \ln f_S \\
\frac{\mathrm{d} S}{\mathrm{~d} t}&=-\sum_S \int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v}\left(\frac{\partial f_S}{\partial t} \ln f_S+\frac{\partial f_S}{\partial t}\right)=0 
\end{align}$$
which means that Vlasov equation describes time-reversible processes 
(remember: collisions are neglected by Vlasov eq.)

"Also, I always find the discussion of particle conservation in fusion ironic. The whole goal of fusion is for the number of particles **not** to be conserved. However, it makes sense to ensure conservation of particles because, even in a successful fusion device, the number of particles that fuse is negligibly small from a plasma behavior perspective (but the energy it produces is not)." - someone in the course discussion forum


## Interpretation of Vlasov equation
The motion of $f_S$ is incompressible in 6D phase space
$$
\nabla_{6 D} \cdot \vec{u}=\frac{\partial}{\partial \vec{r}} \cdot \vec{v}+\frac{\partial}{\partial \vec{v}} \cdot \frac{\vec{F}}{m_S}=0
$$
Variation of $f_S$ along the particle orbits
$$\begin{align}
\frac{\mathrm{d} f_S}{\mathrm{~d} t} \text{\huge$|$}_{\text {orbit }} & =\frac{\partial f_S}{\partial t}+\frac{\mathrm{d} \vec{r}}{\mathrm{~d} t}\text{\huge$|$}_{\text {orbit }} \cdot \frac{\partial f_S}{\partial \vec{r}}+\frac{\mathrm{d} \vec{v}}{\mathrm{~d} t}\text{\huge$|$}_{\text {orbit }} \cdot \frac{\partial f_S}{\partial \vec{v}} \\
& =\frac{\partial f_S}{\partial t}+\vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}+\frac{\vec{F}}{m_S} \cdot \frac{\partial f_S}{\partial \vec{v}}\\
&=\frac{\partial f_S}{\partial t}+\vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}+\frac{q_S}{m_S}(\vec{E}+\vec{v} \times \vec{B}) \cdot \frac{\partial f_S}{\partial \vec{v}} \overset{\text { Vlasov}}{=} 0
\end{align}
$$

$f_S$, as measured when moving along a particle trajectory, is constant.


How to find solutions to the equation is discussed in [1].


## Sources
1. EPFL - Introduction to Plasma Physics, lecture 2d)
2. https://en.wikipedia.org/wiki/Constant_of_motion
