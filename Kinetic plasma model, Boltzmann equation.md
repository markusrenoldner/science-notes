we discuss [[Plasma, Magnetohydrodynamics (MHD)]].


## Self-consistent plasma description
1. we can find the position and velocities of every particle in a plasma from Newton's 2nd law, i.e. given $F_i \implies r_i, v_i\quad \forall i$ due to $$m_i \partial_t^2 r_i = F_i = q_i \left [ E(r_i, t) + v_i\times B(r_i) \right ]$$ 
2. from this, we get the charge  and current density, i.e. $r_i, v_i \implies q_i, j$ as
$$\begin{align}
    q = \sum_i q_i \delta (r - r_i)\\
    j = \sum_i q_i v_i \delta(r-r_i)
\end{align}$$
3. $q,j\implies B,E$ due to the [[Maxwell equations]] $$\begin{align}
    \nabla\cdot E &= \frac{\rho}{\epsilon_0},  &&\nabla\times E=-\partial_t B, \\
    \nabla\cdot B &= 0, &&\nabla\times B =\mu_0 \left ( j + \epsilon_0 \partial_t E \right ) .
\end{align}$$
4. and $B,E \implies F_i$ as $$F_i = q_i \left [ E(r_i,t) + v_i \times B(r_i,t) \right ]$$ from which one can start at 1. again to obtain the particle positions and velocities.

This model is consistent, but not practical for large numbers of particles.
Better: statistical approach.


## Distribution functions
We use distribution functions (see [2]) in 6D phase space (3 positions, 3 velocities). 
Interesting quantities:
$$\begin{align}
    N_S &= \int dr \int dv f_S(r,v,t) &&\quad \text{ ... number of particles of type "S"}\\
    n_S(r,t) &= \int dv f_S(r,v,t) &&\quad \text{ ... number density in [1/volume]}\\
    u_S &= \frac{1}{n_S}\int dv v f_S(r,v,t)&&\quad \text{ ... average velocity}
\end{align}$$

## Examples of distribution functions
Maxwell-Boltzmann distribution function
$$\begin{align}
    &F_0(\vec{v})=n_0\left(\frac{1}{2 \pi v_{t h}^2}\right)^{\frac{3}{2}} \exp \left(-\frac{v^2}{2 v_{t h}^2}\right)=A \exp(-B v^2) \quad\text{...Gaussian type}\\
    \text{in 1D: }\quad &F_0(v)=n_0\left(\frac{1}{2 \pi v_{t h}^2}\right)^{\frac{1}{2}} \exp \left(-\frac{v^2}{2 v_{t h}^2}\right)
\end{align}$$
Mono-energetic beam in 1D
$$
F_0(v)=n_0 \delta\left(v-v_0\right)
$$
Two counter streaming beams in 1D
$$
F_0(v)=\frac{n_0}{2}\left[\delta\left(v-v_0\right)+\delta\left(v+v_0\right)\right]
$$
We want to find the time evolution of the distribution function:


## Conservation of particle number in phase space
If there are no sources nor sinks of particles particles are conserved in 6D phase space. Therefore we have a [[Conservation law, transport equation]]:
$$\frac{\partial f_S}{\partial t} =-\nabla_{6 D} \cdot\left(\vec{u} f_S\right)$$
Together with the "6D-nabla operator" and the "6D-velocity" (time derivative of state vector):
$$\begin{align}
    \nabla_{6 D} &=\left(\partial x, \partial y, \partial z, \partial v_x, \partial v_y, \partial v_z\right)=\left(\partial \vec{r}, \partial \vec{v}\right) \\
    \vec{u} &=\left(\frac{\mathrm{d} \vec{r}}{\mathrm{~d} t}, \frac{\mathrm{d} \vec{v}}{\mathrm{~d} t}\right)=\left(\vec{v}, \frac{\vec{F}}{m_S}\right)=\left(\vec{v}, \frac{\vec{F}^{l}+\vec{F}^{s}}{m_S}\right) 
\end{align}$$
we get
$$ \frac{\partial f_S}{\partial t}=-\frac{\partial}{\partial \vec{r}} \cdot\left(\vec{v} f_S\right)-\frac{\partial}{\partial \vec{v}} \cdot\left[\left(\frac{\vec{F}^{l}+\vec{F}^{s}}{m_S}\right) f_S\right]
$$
(l ... long range, s ... short range)


## The Boltzmann equation
... basically a reformulation of the conservation law from before.
Observations:
- $\vec{v}$ is independent of $\vec{r}, \frac{\partial}{\partial \vec{r}} \cdot\left(\vec{v} f_S\right)=\vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}$
- $\vec{F}^{l}=q_S\left(\vec{E}^{l}+\vec{v} \times \vec{B}^{l}\right)$, where $E^l$ independent of $\vec{v}$ and $\vec{v} \times \vec{B}^{l} \perp \vec{v}$
$$\implies \frac{\partial}{\partial \vec{v}} \cdot\left(\vec{F}^{l} f_S\right)=\vec{F}^{l} \cdot \frac{\partial f_S}{\partial \vec{v}} $$
Now we plug this into the conservation law
$$ \frac{\partial f_S}{\partial t}+\vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}+\frac{\vec{F}^{l}}{m_S} \cdot \frac{\partial f_S}{\partial \vec{v}}=\underbrace{-\frac{\partial}{\partial \vec{v}} \cdot\left(\frac{\vec{F}^{s}}{m_S} f_S\right)}_{\left(\frac{\partial f}{\partial t}\right)_c}$$The term $(\partial_t f)_c$ describes evolution of distribution function due to collisions and is called collision operator. When we explicitly show $F^l$, we get $$\frac{\partial f_S}{\partial t}+\vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}+\frac{q_S}{m_S}\left(\vec{E}^{l}+\vec{v} \times \vec{B}^{l}\right) \cdot \frac{\partial f_S}{\partial \vec{v}}=\left(\frac{\partial f}{\partial t}\right)_c$$ which is called the "Boltzmann equation".


## Sources
1. EPFL - Introduction to Plasma Physics, lecture 2a)
2. https://en.wikipedia.org/wiki/Distribution_function_(physics)
