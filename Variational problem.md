(= "variational formulation" or "weak formulation" or "weak problem")
Also read: [[Solvability of variational problems]]

## Two points of view:
1. ... generalize partial [[Differential equations]]; nice for using the [[Finite Element Method (FEM)]]
2. [[Minima of functionals solve variational problems]]


## Linear variational problem
Find $u\in \hat{V}$ such that 
$$a(u,v)=l(v) \quad \forall v\in V_0$$
- $\hat{V}$ is an [[Affine space]], also called trial space (space with non-zero Dirichlet BC)
- $V_0\subset V$ is a subspace, called test space (space with zero Dirichlet BC)
- $u$ is the unknown trial function
- $v$ is the test function
- $a(.,.)$ is a bilinear form
- $l(.)$ is a linear form

>"In a weak formulation, equations or conditions have (weak) solutions only with respect to certain 'test functions'.
>In a strong formulation, the solution space is constructed such that these equations or conditions are already fulfilled.
>Somewhat surprisingly, a differential equation may have solutions which are not differentiable and the weak formulation allows one to find such solutions." (Wikipedia)


## Offset function trick for variational problem
Let $\hat{V}=g+V_0$ , $g$ ... arbitrary offset function that fulfills the nonzero Dirichlet BC.
Then we can convert the problem into one where trial and test space coincide and are both vector spaces:
$$\begin{aligned}
u\in \hat{V} : &\quad a(u,v)=l(v) \quad &&\forall v\in V_0\\
\iff z\in V_0: &\quad a(z+g,v) = l(v) \quad &&\forall v \in V_0 \\
\iff z\in V_0: &\quad a(z,v) = l(v)-a(g,v) \quad &&\forall v \in V_0 
\end{aligned}$$
with a corrected linearform $l(v) - a(g,v)$.
The solution of the old problem can be recovered from the new one by adding the offset function g:
$$u = z+g$$
$g$ is usually not unique. It is arbitrary as long as the above condition is fulfilled.


## Source
- Prof. Hiptmair - Numerical Methods for Partial Differential Equations, ETH lecture notes 2021
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
- https://en.wikipedia.org/wiki/Weak_formulation
- https://en.wikipedia.org/wiki/Weak_solution
