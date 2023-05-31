
[Finite Element Method (FEM)](Finite%20Element%20Method%20(FEM).md)


## Non-zero essential BC
in case of non-zero essential BC, the trial functions are in a space H_g, where g is the value on the boundary, but this space is sometimes still denoted as H_0
the testfunctions are in H_0 and definitely zero on the boundary! ("do not test, where the solution is known", e.g., on the boundary, says hiptmair)
This H_g is an [Affine space](Affine%20space.md), which is not a [Vector space](Vector%20space.md).

The problem can be transferred to a problem in a vector space, (how?)
see [Variational formulation, variational problem](Variational%20formulation,%20variational%20problem.md)


## Zero essential BC
this is easy, then the test space and trial space are always vector spaces


## Natural BC
implemented in the variational formulation only.



## Source:
- Prof. Hiptmair - Numerical Methods for Partial Differential Equations, ETH lecture notes 2021, [hiptmair-NUMPDE.pdf](hiptmair-NUMPDE.pdf)
