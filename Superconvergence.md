# Superconvergence

see [[Numerical analysis]]

when computing an error like 

$$\epsilon = \Vert u-u_h\Vert_2^2 = \int_\Omega (u-u_h)^2$$

in a simulation using computer code, then one has to be carefule with how the exact solution $u$ is represented. Often, it is given as an analytic expressen, e.g.

$$u(x) = \cos(x)$$

and then interpolated into a discrete function.

Consider that we have chosen $u_h\in P^1(\Omega) \subset H^1(\Omega)$, which is a space of continuous, and element-wise first-order polynomials. The exact sol $u$ will be represented as a number of expansion coefficients for the $P^1(\Omega)$ global basis:

$$u(x) = \sum_i \phi_i(x) u_i$$

here $\phi_i$ is a basis of first order polynomials (e.g. "hat/tent functions") etc. etc...

We have "reduced" the exact solution so much, that the error defined before only takes into account the values at the points associated to the $\phi_i$.

This can somehow lead to round-off errors, resulting in a smaller error and therefore higher convergence rate than we actually have.


## Solution:

interpolate both $u_h$ and $u$ into a higher order function space, so that the round-off errors are avoided.

Some more info:

Jørgen S. Dokken's tutorial: https://jsdokken.com/dolfinx-tutorial/chapter4/convergence.html

