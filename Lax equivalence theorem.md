# Lax equivalence theorem
[[Numerics for differential equations]]
FDM: [[Finite Difference Method (FDM)]]


## Main statement
A linear [[Finite Difference Method (FDM)]] or [[Finite Volume Method (FVM)]] scheme converges if and only if it is consistent and stable.
Proof: see lecture 4, Tornberg


## Convergence
... if the numerical approximation $u_h$ of $u$ vanishes as the step length $h$ goes to $0$:
$$\Vert u_h - u\Vert \xrightarrow{h\rightarrow 0} 0$$


## Consistency (order)
The consistency (order) describes how well a numerical scheme with exact input (!!!) actually solves the given PDE-problem.
I.e. we plug in the exact solution, use the fact that it satisfies the given PDE and yield a residual term that shows the consistency order.
This residual is a "local truncation error" that is produces by the scheme in each computation step.

More details: [[Consistency, order, and local truncation error]]

For consistency for FEM, refer to [[Consistency finite differences vs finite elements]].


## Stability
A method is numerically stable, if "local errors are not amplified too much".

Several different approaches, e.g. 
1. [[CFL condition]] (necessary condition) 
2. [[Von Neumann stability analysis]] (sufficient condition, constant coefficients) 
3. Energy method (sufficient condition, variable coefficients). Handwavy idea: "If the energy/[[Energy norm]] of the unknown is conserved by the scheme $\implies$ stability"

Von Neumann analysis can only handle periodic boundary conditions or no boundaries. The energy method can handle more general boundary conditions.


## My question on stack exchange:
https://math.stackexchange.com/questions/4850071/contradicting-definitions-of-numeric-stability-on-wikipedia


## Source:
- Prof. Tornberg - Numerical solutions of differential equations, KTH lecture notes 2022, lecture 4
- https://en.wikipedia.org/wiki/Numerical_methods_for_ordinary_differential_equations