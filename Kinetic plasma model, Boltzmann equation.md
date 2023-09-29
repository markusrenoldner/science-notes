we discuss [[Plasma physics]].


## Closed system of equations for single particles:
1. we can find the position and velocities of every particle in a plasma from Newton's 2nd law and the lorentz force. 
2. from this, we get the charge and current densities
3. from these, we get $B,E$ due to the [[Maxwell equations]] 
4. and from these we get the lorentz force acting on particles

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
$f_S$ is the density over the velocity range, describes how many particles of a certain velocity $v$ exist at the respective location $r$ and time $t$.

## Example: Maxwell-Boltzmann distribution function
$$\begin{align}
    &F_0(\vec{v})=n_0\left(\frac{1}{2 \pi v_{t h}^2}\right)^{\frac{3}{2}} \exp \left(-\frac{v^2}{2 v_{t h}^2}\right)=A \exp(-B v^2) \quad\text{...Gaussian type}\\
    \text{in 1D: }\quad &F_0(v)=n_0\left(\frac{1}{2 \pi v_{t h}^2}\right)^{\frac{1}{2}} \exp \left(-\frac{v^2}{2 v_{t h}^2}\right)
\end{align}$$
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
- $\vec{v}$ is independent of $\vec{r}, \frac{\partial}{\partial \vec{r}} \cdot\left(\vec{v} f_S\right)=\vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}$
- $\vec{F}^{l}=q_S\left(\vec{E}^{l}+\vec{v} \times \vec{B}^{l}\right)$, where $E^l$ independent of $\vec{v}$ and $\vec{v} \times \vec{B}^{l} \perp \vec{v}$
$$\implies \frac{\partial}{\partial \vec{v}} \cdot\left(\vec{F}^{l} f_S\right)=\vec{F}^{l} \cdot \frac{\partial f_S}{\partial \vec{v}} $$
Now we plug this into the conservation law$$ \frac{\partial f_S}{\partial t}+\vec{v} \cdot \frac{\partial f_S}{\partial \vec{r}}+\frac{\vec{F}^{l}}{m_S} \cdot \frac{\partial f_S}{\partial \vec{v}}=\underbrace{-\frac{\partial}{\partial \vec{v}} \cdot\left(\frac{\vec{F}^{s}}{m_S} f_S\right)}_{\left(\frac{\partial f}{\partial t}\right)_c}$$The term $(\partial_t f)_c$ is called collision operator.

## Sources
1. EPFL - Introduction to Plasma Physics, lecture 2a)
2. https://en.wikipedia.org/wiki/Distribution_function_(physics)
