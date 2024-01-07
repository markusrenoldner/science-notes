# Boundary conditions in FEM
[[Finite Element Method (FEM)]]


## Non-zero essential BC
in case of non-zero essential BC, the trial functions are in a space H_g, where g is the value on the boundary, but this space is sometimes still denoted as $H_0$
the testfunctions are in $H_0$ and definitely zero on the boundary! ("do not test, where the solution is known", e.g., on the boundary, says Hiptmair)
This $H_g$ is an [[Affine space]], which is not a vector space.

The problem can be transferred to a problem in a vector space, (how?)
see [[Variational problem]]


## Zero essential BC
this is easy, then the test space and trial space are always vector spaces


## Natural BC
implemented in the variational formulation only.

They are natural, as they show up automatically. E.g. consider
$$\partial_t V + b\cdot \nabla \phi=0$$
$$\partial_t \phi + b\cdot \nabla V=0$$
if you set $V=0$ on the boundary for all $t$, the first equation will naturally enforce $b\cdot \nabla \phi = 0$. In numerical simulations this natural BC should "appear" automatically in the solution, if the mesh is fine enough.


## Source:
- Prof. Hiptmair - Numerical Methods for Partial Differential Equations, ETH lecture notes 2021
