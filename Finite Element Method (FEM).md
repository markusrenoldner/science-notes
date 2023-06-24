important numerical technique for partial differential equations/PDE (see [[Differential equations]] in [[Numerics for differential equations]]



## Idea of FEM
The endgoal is to transfer the PDE problem into a linear system of equations whose solution approximates the PDE.
This is done by interpolating the unknown function in a finite dimensional function space (polynomials of a certain degree).



#todo insert fausit summary for diplimprüfung, structure:
- idea of FEM
	-  [[Variational formulation, variational problem]]
- abstract FEM theory
	- basics bestapprox, linforms
	- inprod, RR theorem
	- coercive, Lax milg, approx of coercive (galerkin ortho, Cea), [[Lax-Milgram lemma]]
	- sob spaces
		- gen derivatives
		- theorems: meyer serrin, rellich, poincare inequ, bramble hilb
		- traces, poincare frid ineq
- exapmle: weak form of poisson
	- dirichlet
	- various BC
- FEM (fausti+thesis)
	- Def, local interp, equivalence, mesh
	- gobal basis
	- assembly
	- error analysis
- adaptivity
- mixed forms
- applications (stokes, convection, maxwell)
#todo include this some info on assembly:
- https://mfem.org/bilininteg/#bilinear-form-integrators
- https://mfem.org/lininteg/#:~:text=Linear%20form%20integrators%20are%20the,sometimes%20over%20edges%20or%20faces



## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
- Prof. Hiptmair - Numerical Methods for Partial Differential Equations, ETH lecture notes 2021, [[hiptmair-NUMPDE.pdf]]
- Prof. Schöberl - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2020
