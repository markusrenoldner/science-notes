
important numerical technique for partial differential equations/PDE (see [Differential equations](Differential%20equations.md)) in [Numerics for differential equations](Numerics%20for%20differential%20equations.md)


## Idea
The endgoal is to transfer the PDE problem into a linear system of equations whose solution approximates the PDE.
This is done by interpolating the unknown function.


## Variational Formulation
see also [Variational formulation, variational problem](Variational%20formulation,%20variational%20problem.md)



Usually, the PDE problem is being transferred into a variational formulation by multiplying by a testfunction and then partially integrating over the domain. This reduces regularity requirements on the unknowns, and forcing terms.
For example, consider the poisson problem:
$$\Delta u = f$$


## Finite dimensional function spaces/FEM spaces


## Assembly



#todo idea of FEM, inclusive global assembly, interpolation operators, local-global mapping, reference transformation

some info on assembly:
https://mfem.org/bilininteg/#bilinear-form-integrators

https://mfem.org/lininteg/#:~:text=Linear%20form%20integrators%20are%20the,sometimes%20over%20edges%20or%20faces



## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
- Prof. Hiptmair - Numerical Methods for Partial Differential Equations, ETH lecture notes 2021, [hiptmair-NUMPDE.pdf](hiptmair-NUMPDE.pdf)
- Prof. Schöberl - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2020