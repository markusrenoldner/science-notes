  
[Navier-Stokes equations](Navier-Stokes%20equations.md)


## Derivation of the divergence-free condition
In continuum mechanics, the continuity equation reads
$$\begin{equation}

    \frac{\text{d}}{\text{d}t} \int_{\Omega}^{}\phi + \int_{\partial\Omega}^{}\boldsymbol{F}(\phi) = \int_{\Omega}^{}\boldsymbol{b}.

\end{equation}$$Here, $\boldsymbol{F}$ is a general flux function and $\boldsymbol{b}$ is function representing all sources and sinks of the quantity $\phi$. Applying the divergence theorem, defining $\boldsymbol{F}:=\boldsymbol{u}\phi$ ("mass flux density") and observing that the equation has to hold for any volume $\Omega$, one gets$$

    \frac{\text{d}\phi}{\text{d}t} + \nabla \cdot (\boldsymbol{u}\phi) = \boldsymbol{b}.

$$For the continuity of mass, one choses $\phi=\rho$, i.e. the mass density:
$$

    \frac{\text{d}\rho}{\text{d}t} + \rho\nabla \cdot \boldsymbol{u} + \boldsymbol{u} \cdot \nabla \rho = \boldsymbol{b}.

$$In case of incompressible flows ($\implies\frac{\text{D}\rho}{\text{D}t}: = \frac{\text{d}\rho}{\text{d}t} + \boldsymbol{u}\cdot \nabla \rho =0$) and with no mass in-/outflow, one obtains
$$    \nabla \cdot\boldsymbol{u}=0.$$
Here, $\frac{\text{D}\rho}{\text{D}t}$ is the total/material derivative ([Material derivative](Material%20derivative.md)) of the quantity $\rho$ along its movement trajectory.


## Derivation of the momentum equation

Now one can apply the continuity equation to the momentum, i.e. choosing $\phi=\boldsymbol{u}\rho$ to get $$\frac{\partial}{\partial t}( \boldsymbol{u}\rho) + \nabla\cdot ( \rho\boldsymbol{u} \otimes \boldsymbol{u}) = \boldsymbol{b},$$where one can use basic vector and tensor algebra rules to get
$$ \nabla\cdot ( \rho\boldsymbol{u} \otimes \boldsymbol{u}) = \nabla \rho\cdot\boldsymbol{u}\boldsymbol{u}+ (\nabla \cdot \boldsymbol{u})\rho\boldsymbol{u} +(\nabla  \boldsymbol{u})\rho\boldsymbol{u}  .$$By comparing the dimensions of the above quantities, one realizes, that $\boldsymbol{b}$ is in fact a force per unit volume. Reformulation gives
$$
\mathbf{u}\left(\frac{\partial \rho}{\partial t}+\nabla \cdot(\rho \mathbf{u})\right)+\rho\left(\frac{\partial \mathbf{u}}{\partial t}+\mathbf{u} \cdot \nabla \mathbf{u}\right) = \boldsymbol{b}  .

$$Using the mass continuity equation from before one obtains
$$\begin{equation}
    \rho\left(\frac{\partial \mathbf{u}}{\partial t}+\mathbf{u} \cdot \nabla \mathbf{u}\right) \equiv \rho\frac{\text{D}\boldsymbol{u}}{\text{D}t}=\boldsymbol{b}  .
\end{equation}$$
The term $\mathbf{u} \cdot \nabla \mathbf{u}$ is also called convective term and is part of the material derivative of the velocity field. Now on to the right hand side: as derived in chapter 8.5 of \cite{bartelmann1}, in the right hand side of the momentum equation (also known as "equation of motion") of a continuum there appears the divergence of a tensor quantity called the Cauchy stress tensor. Its matrix representation in cartesian coordinates is$$\boldsymbol{\sigma} = \begin{pmatrix}
\sigma_{xx} & \tau_{xy} & \tau_{xz}\\
\tau_{yx} & \sigma_{yy} & \tau_{yz}\\
\tau_{zx} & \tau_{zy} &\sigma_{zz}
\end{pmatrix}.$$The term $\boldsymbol{b}$ is the sum of the divergence of this tensor and an external force term $\boldsymbol{f}$, i.e.$$\boldsymbol{b}=\nabla\cdot \boldsymbol{\sigma} + \boldsymbol{f}.$$Moreover, from the diagonal part of the stress tensor, one can extract the static pressure $p_{\text{stat}}$ $$ \boldsymbol{\sigma} = -p_{\text{stat}} \boldsymbol{\mathbb{I}}+ \boldsymbol{\tau}.$$The pressure is actually the mean value of the trace of $\boldsymbol{\sigma}$: $p_{\text{stat}}=\frac{1}{d}\sum_i \sigma_{ii}$. This decomposition results in$$\begin{equation}
    \rho\left(\frac{\partial \mathbf{u}}{\partial t}+\mathbf{u} \cdot \nabla \mathbf{u}\right) =-\nabla p_{\text{stat}} + \nabla\cdot \boldsymbol{\tau} + \boldsymbol{f}.
\end{equation}
$$To actually compute solutions for $\boldsymbol{u}$ and the new, explicitly visible unknown $p_{\text{stat}}$, one has to specify more properties of $\boldsymbol{\tau}$ (sometimes called "deviator stress tensor").If $\boldsymbol{\tau}$ is proportional to the deformation rate/velocity difference per unit length of the $\boldsymbol{u}$-field, the flow is called "Newtonian". In 2D and for one component this yields$$\tau_{ij}=\mu\frac{\text{d}u_i}{\text{d}x_j}.$$The proportionality constant $\mu$ is called dynamic viscosity. In 3D one gets$$\boldsymbol{\tau}=\mu \nabla \boldsymbol{u},$$from which in the literature usually only the symmetric part $\left ( \nabla \boldsymbol{u}+(\nabla \boldsymbol{u})^\intercal \right )$ is considered, as the antisymmetric part only describes a rotation of the flow, and not a deformation. This results in the incompressible Navier-Stokes momentum equation for Newtonian fluids: $$\begin{equation}
    \rho\left(\frac{\partial \mathbf{u}}{\partial t}+\mathbf{u} \cdot \nabla \mathbf{u}\right) =-\nabla p_{\text{stat}} + \mu \Delta \boldsymbol{u} + \boldsymbol{f}.
\end{equation}$$
The term $\Delta \boldsymbol{u}$ is also called dissipative or diffusive term, as it results in energy dissipation. It also shows up in the heat equation.

## Nondimensional formulation

A reference length, velocity, time and pressure (in capital letters) is introduced
$$\begin{align*}
    \tilde{\boldsymbol{r}} &= \frac{\boldsymbol{r}}{L}\text{, and }\frac{1}{L}\tilde{\nabla}=\nabla,\\
    \tilde{\boldsymbol{u}} &= \frac{\boldsymbol{u}}{U},\\
    \tilde{t} &= \frac{t}{L/U},\\
    \tilde{p}_{\text{stat}} &= \frac{p_{\text{stat}}}{\rho U^2},
\end{align*}$$
one can substitute everything into the equation above and obtain
$$\begin{equation}
    \frac{\partial \tilde{\boldsymbol{u}}}{\partial\tilde{t}}+\tilde{\boldsymbol{u}} \cdot \tilde{\nabla} \tilde{\boldsymbol{u}} =-\nabla \tilde{p}_{\text{stat}} + \frac{\mu}{\rho UL} \tilde{\nabla}^2 \tilde{\boldsymbol{u}} + \boldsymbol{f}.
\end{equation}$$
The coefficient preceding $\boldsymbol{f}$ has been incorporated into $\boldsymbol{f}$. Furthermore, in the follwing, the tilde symbols will be ignored from now on. That means, the rest of this document will treat the Navier-Stokes equations in its non-dimensional form. 
Now the Reynolds number is defined
$$\begin{equation}
\text{Re}=\frac{\rho UL}{\mu},
\end{equation}$$
which is the single characteristic parameter of this equation. In the literature, Re is often introduced as the the ratio between inertial and viscous forces. A more straight-forward interpretation: it is the ratio of the dynamic pressure and the shear stress:$$ \text{Re} \equiv \frac{\rho UL}{\mu} = \frac{\rho U^2}{\mu \frac{U}{L}} = 2\frac{ p_\text{dyn}}{\tau_{\text{shear}}}.$$This argument should illustrate the meaning of the phrase "ratio of pressure and stress" without going into too much details. 

Remarks for flows with high Reynolds number:
- show turbulent behaviour,
- A high Reynolds number implies that the dissipative term $\Delta u$ is "turned off" and the nonlinear convection term $(u\cdot \nabla)u$ dominates ov er the dissipative term
- For Re $\rightarrow \infty$ (inviscid limit), the equations are also called Euler-equations.
- at Re>2000 starts to develop turbulence
- at Re>4000 the flow is considered "fully turbulent"

Remarks for flows with low Reynolds number:
- this characterises creeping, laminar flows
- Here the dissipative term $\Delta u$ dominates over the convective term
- For Re $=0$ the equations are called "Stokes equations"


The incompressible Navier-Stokes problem for Netwonian fluids then becomes
$$\begin{equation}
\begin{cases}
    \displaystyle\frac{\partial \mathbf{u}}{\partial t}+\mathbf{u} \cdot \nabla \mathbf{u} =-\nabla p_{\text{stat}} + \frac{1}{\text{Re}} \Delta \boldsymbol{u} + \boldsymbol{f} ,\\
    \displaystyle\nabla \cdot \boldsymbol{u} = 0.
\end{cases}
\end{equation}$$


## Rotational formulation


The Laplacian of a vector field is defined as
$$\Delta \boldsymbol{u} = \nabla(\nabla\cdot \boldsymbol{u}) - \nabla \times (\nabla \times \boldsymbol{u})$$
and the velocity is divergence-free. Further, it holds that$$ \boldsymbol{u}\cdot \nabla \boldsymbol{u} =\frac{1}{2}\nabla (\boldsymbol{u}\cdot\boldsymbol{u}) +(\nabla\times \boldsymbol{u}) \times \boldsymbol{u} .$$This results in
$$\begin{equation}
\begin{cases}
    \displaystyle
    \frac{\partial \boldsymbol{u}}{\partial t}+\boldsymbol{\omega} \times \boldsymbol{u}+\frac{1}{2}\nabla (\boldsymbol{u}\cdot\boldsymbol{u})+\frac{1}{\operatorname{Re}} \nabla \times \boldsymbol{\omega}+\nabla p_{\text{stat}}=\boldsymbol{f}, \\
    \boldsymbol{\omega}=\nabla \times \boldsymbol{u}, \\
    \nabla \cdot \boldsymbol{u}=0.
\end{cases}
\end{equation}$$
Here $\boldsymbol{\omega}$ denotes the vorticity of the fluid.


## Bernoulli pressure and forcing term
The term $\frac{1}{2}(\boldsymbol{u}\cdot\boldsymbol{u})$ is (the dimensionless) Bernoulli pressure, also called dynamical pressure. Including physical constants, the Bernoulli pressure would be $\frac{1}{2}\rho (\boldsymbol{u}\cdot\boldsymbol{u})$.

Now, the total pressure of a fluid is the sum of the static and dynamic pressure
$$\begin{equation}

p_{\text{tot}} = p_{\text{stat}} + \frac{1}{2} (\boldsymbol{u}\cdot\boldsymbol{u}).

\end{equation}$$
To simplify the momentum equation one could now treat this total pressure as an unknown of the problem. The momentum equation changes to
$$\frac{\partial \boldsymbol{u}}{\partial t}+\boldsymbol{\omega} \times \boldsymbol{u}+\frac{1}{\operatorname{Re}} \nabla \times \boldsymbol{\omega}+\nabla p_{\text{tot}}=\boldsymbol{f}.$$After computing a solution, one can easily recover the static pressure from $\boldsymbol{u}$ and $p_{\text{tot}}$, using the relation above.

Without loss of generality, $\boldsymbol{f}=0$ can be assumed, if \boldsymbol{f}  is a ”conservative” vector field, with scalar potential $\psi$. This works, as $\psi$ can then be included in the total pressure (the forcing term is being interpreted as an extra pressure term) and later be subtracted again. See the previous subsection about the Bernoulli pressure as a comparison. This can be helpful for numerical simulations.

The resulting system of equations would then be (still in rotational form)
$$\begin{equation}
\begin{cases}
    \displaystyle
    \frac{\partial \boldsymbol{u}}{\partial t}+\boldsymbol{\omega} \times \boldsymbol{u}+\frac{1}{\operatorname{Re}} \nabla \times \boldsymbol{\omega}+\nabla p_{\text{tot}}=\boldsymbol{f} ,\\
    \boldsymbol{\omega}=\nabla \times \boldsymbol{u}, \\
    \nabla \cdot \boldsymbol{u}=0,
\end{cases}
\end{equation}$$
To summarize: it is given an initial value for $\boldsymbol{u}^0$ and $\boldsymbol{\omega}^0$ as well as the forcing function $\boldsymbol{f}$ (also called data). The unknowns are the velocity field $\boldsymbol{u}$, vorticity field $\boldsymbol{\omega}$, and total pressure $p$.

To yield a meaningful problem, boundary conditions have to be prescribed, see [Boundary conditions for Navier-Stokes](Boundary%20conditions%20for%20Navier-Stokes.md). 


## Sources
- Bartelmann - Theoretische Physik 1, Mechanik
- https://en.wikipedia.org/wiki/Derivation_of_the_Navier%E2%80%93Stokes_equations
- https://en.wikipedia.org/wiki/Navier%E2%80%93Stokes_equations
- https://de.wikipedia.org/wiki/Navier-Stokes-Gleichungen

