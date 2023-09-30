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


## Conservation properties
The vlasov conserves the total number of particles $N_S$, momentum, energy and entropy.

E.g.: integrate Vlasov eq. over phase space (space and velocities)
$$
\begin{align}
&\underbrace{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \frac{\partial f_S}{\partial t}}_{\frac{\partial}{\partial t} \int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} f_S=\frac{\mathrm{d}}{\mathrm{dt}} N_S}+\underbrace{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}}_{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \frac{\partial}{\partial v} \cdot\left(\vec{v} f_S\right)=0}+\underbrace{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \frac{q_S}{m_S}(\vec{E}+\vec{v} \times \vec{B}) \cdot \frac{\partial f_S}{\partial \vec{v}}}_{\int \mathrm{d} \vec{r} \int \mathrm{d} \vec{v} \frac{\partial}{\partial \vec{v}} \cdot\left[\frac{q_S}{m_S}(\vec{E}+\vec{v} \times \vec{B}) f_S\right]=0}=0 \\
& \implies \frac{\mathrm{d} N_S}{\mathrm{~d} t}=0
\end{align}
$$
which means that Vlasov equation describes time-reversible processes. 
(remember: collisions are neglected by Vlasov eq.)

"Also, I always find the discussion of particle conservation in fusion ironic. The whole goal of fusion is for the number of particles **not** to be conserved. However, it makes sense to ensure conservation of particles because, even in a successful fusion device, the number of particles that fuse is negligibly small from a plasma behavior perspective (but the energy it produces is not)." - someone in the course discussion forum from [1].

How to find solutions to the equation is discussed in [1].


## Sources
1. EPFL - Introduction to Plasma Physics, lecture 2d)
2. https://en.wikipedia.org/wiki/Constant_of_motion
