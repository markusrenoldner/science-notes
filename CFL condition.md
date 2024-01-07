# CFL condition
A necessary condition for numerical stability (CFL$\impliedby$stability, but not CFL $\implies$ stability).
See also [[Lax equivalence theorem]] of an approximation using the [[Finite Difference Method (FDM)]].


## In words:
A consistent method can only be stable if the continuous domain of dependence is a subset of the numerical domain of dependence.


## Example
CFL condition for FD schemes for the [[Advection equation]]:
$$\frac{\Delta t}{\Delta x} a \leq 1$$

## Implicit time-stepping schemes
>Firstly, implicit linear convection is unconditionally stable, and also lacks a CFL condition. This happens because implicit schemes use the entire domain to calculate each timestep. However, implicitly calculating (i.e., solving an implicit linear system) each timestep can be very costly. In addition, time accuracy decreases as the timestep increases. Therefore, it is logical is to use an explicit scheme with a lower timestep.

>For more complicated and representative problems, including nonlinear flow, the CFL condition serves as a reference for setting the timestep. Furthermore, when dealing with nonlinear phenomena, even the implicit form can have stability problems if a large Courant number is chosen. Consequently, it might be necessary to apply local stability analysis on a linearized formulation in those cases. Still, the CFL condition is necessary for nonlinear problems.


## Source:
- Prof. Tornberg - Numerical solutions of differential equations, KTH lecture notes 2022, lecture 4
- https://www.simscale.com/blog/cfl-condition/
