[[Fluid Dynamics]]

## Vector calculus notation
$$
    \rho\left(\frac{\partial \mathbf{u}}{\partial t}+\mathbf{u} \cdot \nabla \mathbf{u}\right) =-\nabla p_{\text{stat}} + \mu \Delta u + f
$$
$$\nabla \cdot u = 0$$


## Equations for each component:

![[nav-stok-components.png]]


## Nondimensional formulation
introduce reference variables (in capital)
$$\begin{align*}
    \tilde{\boldsymbol{r}} &= \frac{\boldsymbol{r}}{L}\text{, and }\frac{1}{L}\tilde{\nabla}=\nabla,\\
    \tilde{\boldsymbol{u}} &= \frac{\boldsymbol{u}}{U},\\
    \tilde{t} &= \frac{t}{L/U},\\
    \tilde{p}_{\text{stat}} &= \frac{p_{\text{stat}}}{\rho U^2},
\end{align*}$$
plug this into the NS equations.
Then ignore the tilde symbol and get:

$$
\begin{align}
    \displaystyle\frac{\partial \mathbf{u}}{\partial t}+\mathbf{u} \cdot \nabla \mathbf{u} =-\nabla p_{\text{stat}} + \frac{1}{\text{Re}} \Delta \boldsymbol{u} + \boldsymbol{f} \\
    \displaystyle\nabla \cdot \boldsymbol{u} = 0
\end{align}
$$


## Rotational formulation (nondimensional)
apply this to the viscous term
$$\Delta u = \nabla ( \nabla \cdot u) - \nabla \times (\nabla \times u)
$$
and this to the convective term
$$ \boldsymbol{u}\cdot \nabla \boldsymbol{u} =\frac{1}{2}\nabla (\boldsymbol{u}\cdot\boldsymbol{u}) +(\nabla\times \boldsymbol{u}) \times \boldsymbol{u} $$
and get
$$\begin{align}
    \displaystyle
    \frac{\partial \boldsymbol{u}}{\partial t}+\boldsymbol{\omega} \times \boldsymbol{u}+\frac{1}{\operatorname{Re}} \nabla \times \boldsymbol{\omega}+\nabla p=\boldsymbol{f} \\
    \boldsymbol{\omega}=\nabla \times \boldsymbol{u} \\
    \nabla \cdot \boldsymbol{u}=0
\end{align}
$$
ATTENTION:
here the total pressure p is used:
$$p = p_{stat} + \frac{1}{2} (u\cdot u)$$
where the second term is called dynamic pressure or Bernoulli pressure


## Boundary conditions for the NS equ
[[Boundary conditions for Navier-Stokes]]



## Euler equations (inviscid limit)
#TODO 


## Stokes equations
#TODO 