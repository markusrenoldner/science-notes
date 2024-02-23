# Taylor-Green vortex (TGV)

Periodic, decaying analytical solution of the [[Navier-Stokes equations]], used to conduct convergence tests of methods from [[Numerics for differential equations]].

![[taylor-green-vortex.png]]


## "Dimensional" case
For 
$$
\begin{aligned}
    \rho\left(\frac{\partial \mathbf{u}}{\partial t}+\mathbf{u} \cdot \nabla \mathbf{u}\right) &=-\nabla p_{\text{stat}} + \mu \Delta u + f\\
	\nabla \cdot u &= 0
\end{aligned}
$$
the TGV solution is given as
$$\begin{aligned}
u&=cos(x)sin(y)F(t)\\
v&= -sin(x)cos(y)F(t) \\
w&=0
\end{aligned}$$
with
$$F(t)=e^{-2\nu t}$$
Here $\nu$ is the kinematic viscosity ($\nu = \frac{\mu}{\rho}$).


## Nondimensional case
In the nondimensional formulation
$$
\begin{aligned}
    \displaystyle\frac{\partial \mathbf{u}}{\partial t}+\mathbf{u} \cdot \nabla \mathbf{u} &=-\nabla p_{\text{stat}} + \frac{1}{\text{Re}} \Delta \boldsymbol{u} + \boldsymbol{f} \\
    \displaystyle\nabla \cdot \boldsymbol{u} &= 0
\end{aligned}
$$
 the function $F$ can be corrected to 
$$\displaystyle F(t)=e^{-2t/Re}$$


## Forcing term and Bernoulli pressure
If one plugs in the TGV into the Navier-Stokes equations, one gets a forcing term with
$$curl(f) = 0$$
This allows to pretend, that $f$ is a pressure term. In numerics, $f$ can then be set to 
$$f:=0$$
and later be subtracted from the pressure if one is interested in the static pressure.




## Source:
- https://en.wikipedia.org/wiki/Taylor%E2%80%93Green_vortex
- https://www1.grc.nasa.gov/wp-content/uploads/C3.3_Ames.pdf