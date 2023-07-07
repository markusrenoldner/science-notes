
## Two points of view
1. ... is an equivalent formulation of the problem to find the [[Minimum of quadratic functionals]] , as explained here [[Equivalence of minimization of quadr. functional and var. problem]]
2. ... can be used to express a generalization of partial differential equation (see [[Differential equations]] that can be solved using the [[Finite Element Method (FEM)]]


## Linear variational problem (on [[Affine space]])
Find $u\in \hat{V}$ such that 
$$a(u,v)=l(v) \quad \forall v\in V_0$$
$\hat{V}$ ... affine subspace, also called trial space (space with non-zero Dirichlet BC)
$V_0$ ... subspace of the "big" vector space $V$. $V_0$ is also called test space and is a vector space (space with zero Dirichlet BC).


## Offset function trick for variational problem
Let $\hat{V}=g+V_0$ , $g$ ... arbitrary offset function that fulfills the nonzero Dirichlet BC.
Then we can convert the problem into one where trial and test space coincide and are both vector spaces:
$$\begin{align}
u\in \hat{V} : &\quad a(u,v)=l(v) \quad &&\forall v\in V_0\\
\iff z\in V_0: &\quad a(z+g,v) = l(v) \quad &&\forall v \in V_0 \\
\iff z\in V_0: &\quad a(z,v) = l(v)-a(g,v) \quad &&\forall v \in V_0 
\end{align}$$
with a corrected linearform $l(v) - a(g,v)$.
The solution of the old problem can be recovered from the new one by adding the offset function g:
$$u = z+g$$
$g$ is usually not unique. It is arbitrary as long as the above condition is fulfilled.


## Source
- Prof. Hiptmair - Numerical Methods for Partial Differential Equations, ETH lecture notes 2021, [[hiptmair-NUMPDE.pdf]]
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
