# Vlasov equation
we talk about a kinetic description of [[Plasma physics]].

Assumptions:
- the phase space volume is macroscopically small: the quantities we compute are representative of the point (x,v) and not of the entire volume
- the phase space volume is microscopically large: there are enough particles in the volumes we consider, so that we can use a statistical ("continuum") treatment
- internal forces (collisions) are neglected


## Distribution functions
The distribution function $f(x,v,t)$, with $x=(x_1,x_2,x_3)$ and $v=(v_1,v_2,v_3)$ is the particle density in 6D phase space. (If $f$ would be normalized, so that $\int fdxdv=1$, $f$ would be the probability to find a particle in a certain phase space volume). Therefore the total number of particles is $N\equiv \int f dx dv$

We use distribution functions $f$ (see [2]) in 6D phase space (3 positions, 3 velocities). 
Interesting quantities:
$$\begin{aligned}
    N_S &= \int dx\int dv f_S(x,v,t) &&\quad \text{ ... number of particles of type "S"}\\
    n_S(x,t) &= \int dv f_S(x,v,t) &&\quad \text{ ... number density in [1/volume]}\\
    u_S &= \frac{1}{n_S}\int dv v f_S(x,v,t)&&\quad \text{ ... average velocity}
\end{aligned}$$
$f_S$ is the density over the velocity range, describes how many particles of a certain velocity $v$ exist at the respective location $r$ and time $t$.
An example is the "Maxwell-Boltzmann"-distribution function:$$f_{S,B}=A \exp{(-Bv^2)}$$ with appropriate constants $A,B$. Its a Gaussian-type distribution (bell curve).


## Derivation
We compute the time-rate of change of $N$ and apply the Leibnitz rule (https://en.wikipedia.org/wiki/Leibniz_integral_rule#Higher_dimensions)
$$

\partial_t N \stackrel{\text{by def}}{=} \partial_t \int f = \int_V \partial_t f + \int_{S(V)} fU

$$
where $U=(\partial_t x,\partial_t v)=(v,F/m)$. The number of particles $N$ in the volume $V$ is conserved, so $\partial_t N = 0$ and we get
$$\begin{aligned}

0&=\int_V \partial_t f + \int_{S(V)} fU\\

&=\int_V \partial_t f+ \int_V \nabla_6 \cdot (fU)\\

\implies 0&=\partial_t f+ \nabla_6 \cdot (fU)

\end{aligned}$$
where $\nabla_6\equiv (\nabla_x,\nabla_y)=(\partial_{x_1}, .. \partial_{y_1},...)$, and where we have used the divergence theorem and the fact that the integral kernel has to vanish for the equation to hold for an arbitrary volume $V$. Now we develop the operator and realize that
$$\begin{aligned}

0&= \partial_f + \nabla_6\cdot(fU) \\

&= \partial_f + \nabla_x\cdot(f v) + \nabla_v\cdot \left ( f \frac{F}{m} \right ) \\

&= \partial_f + v\cdot\nabla_x f + \frac{F}{m}\cdot \nabla_vf

\end{aligned}$$
The reason why the last step is valid, is that
1. the phase space coordinates are independent, i.e. $\partial_{x_i}v_j = 0$; and
2. $\nabla_v\cdot F=q\nabla_v\cdot (E+v\times B)=0$ as $E$ is indep of $v$ and $\nabla_v\cdot (v\times B)=0$, as one can see when writing it out component-wise.

The last line from before is the Vlasov equation:
$$

0 =\partial_f + v\cdot\nabla_x f + \frac{q}{m}(E+v\times B) \cdot \nabla_v f

$$

## Conservation properties
- $\nabla_x \cdot v=0$ ... incompressible velocity
- $f$ is conserved along characteristics (=particle trajectories):
$$\left . \frac{d}{dt}f\right|_{t,x(t),v(t)} \stackrel{\text{chain rule}}{=} \nabla_x f\partial_t x + \nabla_v f\partial_t v \stackrel{Vlasov}{=} 0$$
- IF $C_i$ is a conserved quantity ($\iff dC_i/dt = 0$), then every function $g(C_1,...C_N)$ solves Vlasov as:
$$ \frac{\text{d}g}{\text{d}t} \stackrel{\text{chain rule}}{=} \sum_j\partial_{C_j}g \underbrace{\partial_t C_j}_{=0} = 0$$
An example of this would be $C=v$, as $\partial_t v = 0$ and every $g(v)$ is a solution.
- Vlasov does not model collisions, and is therefore reversible. The entroy $S\equiv\int f\ln{f}dxdv$ is conserved therefore. In Boltzmann equation, we model collisions, and $S$ is not conserved.
- Another conserved quantity is the sum of particle and field energy
$$

E = E_p + E_F = \sum_\alpha \int \frac{m_\alpha v^2}{2}f_\alpha dxdv + \sum_\alpha \int \frac{\epsilon_0 E^2}{2}+ \frac{B^2}{2\mu_0}dx

$$
## Source
Prof. Fasoli - Plasma 2 lecture notes, chapter 7

