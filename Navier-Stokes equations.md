# Navier-Stokes equations
[[Fluid Dynamics]]

The following equations descibre incompressible, Newtonian fluids.
[[Derivation of Navier-Stokes equations]]

## Vector calculus notation

$$
\begin{aligned}
    \rho\left(\frac{\partial \mathbf{u}}{\partial t}+\mathbf{u} \cdot \nabla \mathbf{u}\right) &=-\nabla p_{\text{stat}} + \mu \Delta u + f\\
	\nabla \cdot u &= 0
\end{aligned}
$$


## Equations for each component in cartesian coordinates
We denote $\boldsymbol{u}:=(u,v,w)$

Continuity: $$\quad \frac{\partial u}{\partial x}+\frac{\partial v}{\partial y}+\frac{\partial w}{\partial z}=0$$Momentum $x$-component:
$$
\rho\left(\frac{\partial u}{\partial t}+u \frac{\partial u}{\partial x}+v \frac{\partial u}{\partial y}+w \frac{\partial u}{\partial z}\right)=-\frac{\partial p}{\partial x}+\mu\left(\frac{\partial^2 u}{\partial x^2}+\frac{\partial^2 u}{\partial y^2}+\frac{\partial^2 u}{\partial z^2}\right)+\rho g_x
$$
Momentum $y$ - component:
$$
\rho\left(\frac{\partial v}{\partial t}+u \frac{\partial v}{\partial x}+v \frac{\partial v}{\partial y}+w \frac{\partial v}{\partial z}\right)=-\frac{\partial p}{\partial y}+\mu\left(\frac{\partial^2 v}{\partial x^2}+\frac{\partial^2 v}{\partial y^2}+\frac{\partial^2 v}{\partial z^2}\right)+\rho g_y
$$
Momentum $z$ - component:$$\rho\left(\frac{\partial w}{\partial t}+u \frac{\partial w}{\partial x}+v \frac{\partial w}{\partial y}+w \frac{\partial w}{\partial z}\right)=-\frac{\partial p}{\partial z}+\mu\left(\frac{\partial^2 w}{\partial x^2}+\frac{\partial^2 w}{\partial y^2}+\frac{\partial^2 w}{\partial z^2}\right)+\rho g_z$$

## Nondimensional formulation
introduce reference variables (in capital)
$$\begin{aligned}
    \tilde{\boldsymbol{r}} &= \frac{\boldsymbol{r}}{L}\text{, and }\frac{1}{L}\tilde{\nabla}=\nabla,\\
    \tilde{\boldsymbol{u}} &= \frac{\boldsymbol{u}}{U},\\
    \tilde{t} &= \frac{t}{L/U},\\
    \tilde{p}_{\text{stat}} &= \frac{p_{\text{stat}}}{\rho U^2},
\end{aligned}$$
plug this into the NS equations.
Then ignore the tilde symbol and get:

$$
\begin{aligned}
    \displaystyle\frac{\partial \mathbf{u}}{\partial t}+\mathbf{u} \cdot \nabla \mathbf{u} =-\nabla p_{\text{stat}} + \frac{1}{\text{Re}} \Delta \boldsymbol{u} + \boldsymbol{f} \\
    \displaystyle\nabla \cdot \boldsymbol{u} = 0
\end{aligned}
$$


## Rotational formulation (nondimensional)
apply this to the viscous term
$$\Delta u = \nabla ( \nabla \cdot u) - \nabla \times (\nabla \times u)
$$
and this to the convective term
$$ \boldsymbol{u}\cdot \nabla \boldsymbol{u} =\frac{1}{2}\nabla (\boldsymbol{u}\cdot\boldsymbol{u}) +(\nabla\times \boldsymbol{u}) \times \boldsymbol{u} $$
and get
$$\begin{aligned}
    \displaystyle
    \frac{\partial \boldsymbol{u}}{\partial t}+\boldsymbol{\omega} \times \boldsymbol{u}+\frac{1}{\operatorname{Re}} \nabla \times \boldsymbol{\omega}+\nabla p=\boldsymbol{f} \\
    \boldsymbol{\omega}=\nabla \times \boldsymbol{u} \\
    \nabla \cdot \boldsymbol{u}=0
\end{aligned}
$$
ATTENTION:
here the total pressure p is used:
$$p = p_{stat} + \frac{1}{2} (u\cdot u)$$
where the second term is called dynamic pressure or Bernoulli pressure


## Boundary conditions for the NS equ
[[Boundary conditions for Navier-Stokes]]



## Euler equations (inviscid limit)
Taking infinite Reynolds number, one gets the [[Euler equations]].




## Sources
- Bartelmann - Theoretische Physik 1, Mechanik
- https://en.wikipedia.org/wiki/Derivation_of_the_Navier%E2%80%93Stokes_equations
- https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_equations
- https://de.wikipedia.org/wiki/Navier-Stokes-Gleichungen