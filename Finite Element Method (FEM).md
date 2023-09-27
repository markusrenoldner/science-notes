important numerical technique for partial differential equations/PDE (see [[Differential equations]] in [[Numerics for differential equations]]


## Idea of FEM
The endgoal is to transfer the PDE problem into a linear system of algebraic equations whose solution approximates the PDE.
This is done by deriving a [[Variational formulation, variational problem]]/weak form of the PDE to reduce regularity requirements. The solution of this weak form is interpolated in a finite dimensional function space (e.g. polynomials of a certain degree).


## Theoretical backgound
1. [[Solvability of continuous and discrete variational problems]]
2. properties of sobolev spaces and trace operators and BC, covered in [[Sobolev spaces and Finite Element spaces]]


## Example: Poisson equation with various BC
[[Example of analyzing the weak form of the Poisson equation]]


## Finite Element approximation
1. Local point of view: The note [[Finite Element]] introduces some "local" (i.e. on one element) objects.
2. Global point of view: Moreover, [[Finite Element]] discusses the "global" objects (on the whole domain) as well.
3. FEM assembly: [[Finite Element]] also discusses the assembly of the final linear system of equations.
4. FEM error analysis: [[Finite Element error analysis]]


## Adaptive FEM
[[Adaptive FEM]]


## Mixed Finite Element formulations
A mixed method is a variational formulation involving two function spaces, and a bilinearform of a special saddle point structure ([[Saddle point problem]]). Usually, it is obtained from [[Variational formulation, variational problem]]s with constraints.
- [[Example mixed Finite Element formulations]]
- [[Brezzi Theorem]]
More examples (Stokes flow problem, convection-dominated flow problem with boundary layer and Maxwell problem) can be found in Faustmann.


## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
- Prof. Hiptmair - Numerical Methods for Partial Differential Equations, ETH lecture notes 2021
- Prof. Schöberl - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2020
