
[[Finite Element Method (FEM)]]


## Non-zero essential BC
in case of non-zero essential BC, the trial functions are in a space H_g, where g is the value on the boundary, but this space is sometimes still denoted as H_0
the testfunctions are in H_0 and definitely zero on the boundary! ("do not test, where the solution is known", e.g., on the boundary, says hiptmair)
This H_g is an [[Affine space]], which is not a [[Vector space]].

The problem can be transferred to a problem in a vector space, (how?)
see [[Variational formulation, variational problem]]


## Zero essential BC
this is easy, then the test space and trial space are always vector spaces


## Natural BC
implemented in the variational formulation only.



## Source:
- Prof. Hiptmair - Numerics for PDE
