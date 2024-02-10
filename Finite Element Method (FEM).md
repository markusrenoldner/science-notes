# Finite Element Method (FEM)
important numerical technique for partial  [[Differential equations]]
see also [[Numerics for differential equations]]


## Idea of FEM
Transfer a PDE into a system of linear, algebraic equations whose solution approximates the PDE.
For that, derive a [[Variational problem]] (or [[Mixed variational problem]]) of the PDE(s). 
Its solution is interpolated in a finite dim. function space (e.g. polynomials of degree $n$).
The unknown interpolation coefficients are the approximate solution.


## Solvability and function spaces
- [[Solvability of variational problems]]
- [[Weak solvability of poisson problem]]
- [[Weak solvability example of mixed problems]]
- [[Galerkin method]]
- For FEM, use Sobolev spaces as defined here: [[Function spaces]]
- [[Sobolev space properties]]
- [[Trace operator]]


## Finite Element approximation
- [[Local Finite Element interpolation]]
- [[Global Finite Element interpolation]]
- [[Finite Element assembly]]
- [[Finite Element error analysis]]


## Adaptive FEM
[[Adaptive FEM]]


## Application examples
More examples of Finite Elements for the Stokes flow problem, for convection-dominated flows with boundary layer and for the Maxwell problem can be found in section 7 in [1].


## Sources
1. Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021 ^68316d
- Prof. Hiptmair - Numerical Methods for Partial Differential Equations, ETH lecture notes 2021
- Prof. Schöberl - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2020
