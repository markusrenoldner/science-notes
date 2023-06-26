important numerical technique for partial differential equations/PDE (see [[Differential equations]] in [[Numerics for differential equations]]


## Idea of FEM
The endgoal is to transfer the PDE problem into a linear system of algebraic equations whose solution approximates the PDE.
This is done by deriving a [[Variational formulation, variational problem]]/weak form of the PDE to reduce regularity requirements. The solution of this weak form is interpolated in a finite dimensional function space (e.g. polynomials of a certain degree).


## Theoretical backgound
- solvability of variational problems
- properties of sobolev spaces
- Trace operators and BC
see [[Finite Element theory]]


## Example: Poisson equation with various BC
[[Example of analyzing the weak form of the Poisson equation]]


## Finite Element approximation



## todolist
#todo insert fausit summary for diplimprüfung, structure:

- FEM (fausti+thesis)
	- Def, local interp, equivalence, mesh [[Finite Element]]
	- gobal basis
	- assembly
	- error analysis
- adaptivity
- mixed forms
- applications (stokes, convection, maxwell)
#todo include this some info on assembly:
- https://mfem.org/bilininteg/#bilinear-form-integrators
- https://mfem.org/lininteg/#:~:text=Linear%20form%20integrators%20are%20the,sometimes%20over%20edges%20or%20faces
#todo split this note into subnotes



## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
- Prof. Hiptmair - Numerical Methods for Partial Differential Equations, ETH lecture notes 2021, [[hiptmair-NUMPDE.pdf]]
- Prof. Schöberl - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2020
