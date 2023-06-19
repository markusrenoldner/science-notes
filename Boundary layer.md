[[Fluid Dynamics]]

For flows with high Reynolds number Re, where the viscous term $\Delta u$ is small, most of the flow can be considered inviscid, described by [[Euler equations]]. The Euler equations are obtained if Re → ∞ in the [[Navier-Stokes equations]].

However, the highest derivatives are present in the viscous terms, thus a smaller number of boundary conditions ([[Boundary conditions for Navier-Stokes]]) can be satisfied when solving the Euler equations. 

In particular, the no flow condition (no flow across boundary) can be satisfied at a solid wall but not the no slip condition.
In order to satisfy the no slip condition we need to add the viscous term. Thus, there will be a layer close to the solid walls where the viscous terms are important even for very high Reynolds number flow. This layer will be very thin and the flow in that region is called boundary layer flow.

![[Pasted image 20230618233838.png]]


## Equations
$u$ and $v$ are the velocity components in 2D
The continuity equation is:
$$\partial_x (\rho u) + \partial_y (\rho v) = 0$$
And the momentum equation in $x$ direction is
$$\rho u \partial_x u + \rho v \partial_y u= \partial_x p + \partial_y (y \partial_y u)$$


## Source
- Henningson - Fluid Dynamics, lecture notes
- Hanifi - Computational Fluid Dynamics part 1, lecture notes