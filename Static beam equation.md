("Differentialgleichung der Biegelinie")

Assume a cartesian coordinate system where 
- x goes to the right
- y goes out of plane
- z goes down

It is given as
$$\kappa = \frac{1}{r} =  \frac{M_y(x)}{EI_y}$$
where
- $\kappa=\frac{1}{r}$ is the curvature of the beam, $r$ the radius
- $M_y(x)$ is the bending moment around the $y$-axis ("Biegemoment")
- $E$ is youngs module ("Elastizitätsmodul")
- $I_y$ is the second moment of area/area moment of inertia("Flächenträgheitsmoment")

Applying the geometrical definition of curvature:
$$-\kappa \equiv \frac{\omega''}{(1+\omega'^2)^{3/2}} = -\frac{M_y(x)}{EI_y}$$
where $\omega = \omega(x)$ is the onedimensional $z$-directional deflection ("Durchbiegung") of the beam.

For small deflections, one can neglect $\omega'^2$ and yield
$$\omega''(x) \approx - \frac{M_y(x)}{EI_y}$$
Solutions for $\omega(x)$ can be found by integration twice and applying boundary conditions.

## Sources:
- https://de.wikipedia.org/wiki/Biegelinie
- https://en.wikipedia.org/wiki/Euler%E2%80%93Bernoulli_beam_theory#Static_beam_equation