# Diffusion coefficient from statistical mechanics
[[Diffusion equation]]

## Random walk
Assume a particle undergoes $N$ statistically independent steps, with equal probability of going left or right, each with size $\xi=|\xi_i|$. Then it will arrive at position
$$x=\sum_{i=1}^N \xi_i$$
The mean displacement is
$$\bar x = 0$$
But the mean **quadratic** displacement is
$$\overline {x²} = \underbrace{\sum_i \overline{\xi_i^2}}_{=N\xi^2} + \underbrace{\sum_i\sum_{j\neq i} \overline{\xi_i \xi_j}}_{=0} =N\xi^2 $$
We define the inter collision time $\tau$ (inverse of collision frequency $\nu$)
$$N=\frac{t}{\tau}$$
and then define the Diffusion coefficient $D$ by 
$$
\overline{x^2} =N\xi^2=\xi^2\frac{t}{\tau}\equiv D t,
$$
So we have defined $D$ such that
$$D=\text{step size}^2\times\text{collision frequency}$$
Equally, one can introduce the particle speed $v$ and get
$$D={v^2} \tau$$


## Flux and diffusion equation
Equation of motion for particle:
$$m\partial_t v = - \frac{\nabla p}{n} - mv\nu$$
where $n$ is the number density. In the steady-state scenario, we get 
$$v=-\frac{1}{m\nu n}\nabla p$$
We use the ideal gas law, and we use the symbol $T$ for the product of temperature and Boltzmann constant:
$$p = \frac{NT}{V}=nT$$
We assume uniform temperature, $\nabla p = T\nabla n$, and get
$$v=-\underbrace{\frac{T}{m\nu }}_{\equiv D}\frac{\nabla n}{n}=-D\frac{\nabla n}{n}$$
If we identify $T$ with the kinetic energy (actually $E_{kin}\equiv 1/2v^2 m=3/2T$, but we ignore the constant numeric factors), we get
$$D=\frac{T}{m \nu}\approx \frac{mv^2}{m\nu}=\frac{v^2}{\nu}\equiv v^2\tau$$
So this definition is consistent with the one from before. The flux is$$\Gamma\equiv vn = -D\nabla n$$ and we know that $n$ is a conserved quantity - hence satisfies a continuity equation:
$$\partial_t n + \nabla \cdot \Gamma = \partial_t n - \nabla \cdot (D\nabla n) = 0$$
.... the [[Diffusion equation]].



## Source
Prof. Ambrogio Fasoli - Plasma II lecture at EPFL, chapter 5.
