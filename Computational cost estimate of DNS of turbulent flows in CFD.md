Direct numerical simulation = DNS
Computational fluid mechanics = CFD, [[Fluid Dynamics]]


## Goal:
The goal here is not to compute an error bound for a specific numerical scheme, but to estimate costs of a general scheme, that can resolve turbulent flow features.


## Nr of DOFs and timesteps
- Necessary DOFs per spatial axis to resolve vortices: $n_x=\frac{1}{\Delta x}=\mathcal{O}(\text{Re}^\frac{3}{4})$
- Same in 3D: $N = n_x^3 = \mathcal{O}(\text{Re}^\frac{9}{4})$
- Necessary nr of timesteps: $N_T=\frac{1}{\Delta t} = \mathcal{O}(\text{Re}^\frac{1}{2})$


## Numerical stability? can we use explicit time stepping?
use [[CFL condition]]:
$$\frac{\Delta t}{\Delta x}u < C = \mathcal{O}(1)$$
this gives
$$\Delta t < \frac{\Delta x}{u}\mathcal{O}(1) = \frac{\mathcal{O}(\text{Re}^\frac{-3}{4})}{\mathcal{O}(\text{Re}^\frac{-1}{4})}\mathcal{O}(1) = \mathcal{O}(\text{Re}^\frac{-1}{2})$$
DNS for turbulent flows allows to use explicit time stepping always, because the step length required for numerical stability is the same as the step length required to resolve turbulence at all scales!


## Total cost of DNS depending in Reynolds number
$$\begin{aligned}
\text{total cost} &= \text{cost per timestep} \times \text{Nr of time steps}\\
&= \mathcal{O}(N)\times \mathcal{O}(N_T)\\
&= \mathcal{O}(\text{Re}^\frac{9}{4})\times \mathcal{O}(\text{Re}^\frac{1}{2})\\
&= \mathcal{O}\left(\text{Re}^\frac{11}{4}\right)\\
&\approx \mathcal{O}(\text{Re}^3)
\end{aligned} $$


## Source
https://www.youtube.com/watch?v=Depe06jFNis&list=WL&index=10&ab_channel=MachineLearning%26Simulation