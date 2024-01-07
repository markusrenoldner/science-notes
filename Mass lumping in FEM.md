# Mass lumping in FEM
[[Finite Element Method (FEM)]]

Is a method to approximate the mass matrix in time-dependent PDEs by a diagonal matrix. This makes sense in case the time-stepping is explicit, so that no linear system has to be solved in each step. The diagonal mass matrix can be inverted trivially.
The approximation can be done in different ways, e.g. by a weighted, row-wise summation of the non-diagonal entries into the corresponding diagonal entry.

It is not clear, whether this method is numerically consistent in the general case.



## Source:
https://scicomp.stackexchange.com/questions/19704/how-to-formulate-lumped-mass-matrix-in-fem