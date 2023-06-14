
## Two points of view
1. ... is an equivalent formulation of the problem to find the [[Minimum of quadratic functionals]] , as explained here [[Equivalence of minimization of quadr. functional and var. problem]]
2. ... can be used to express a generalization of partial differential equation (see [[Differential equations]]


## Linear variational problem (on [[Affine space]])

find $u\in \hat{V}$ such that 
$$a(u,v)=l(v) \quad \forall v\in V_0$$
$\hat{V}$ ... affine subspace, also called trial space
$V_0$ ... subspace of the "big" vector space $V$, $V_0$ is also called test space



## Offset function trick for variational problem

Let $\hat{V}=g+V_0$ 
we can convert the problem into one where $V_0$ and $\hat{V}$ coincide and are both vector spaces!! :
$$\begin{align}
u^*\in \hat{V} : &\quad a(u^*,v)=l(v) \quad &&\forall v\in V_0\\
\iff u\in V_0: &\quad a(u+g,v) = l(v) \quad &&\forall v \in V_0 \\
\iff u\in V_0: &\quad a(u,v) = l(v)-a(g,v) \quad &&\forall v \in V_0 
\end{align}$$
with a corrected linearform $l(v) - a(g,v)$.
The solution of the old problem can be recovered from the new one by adding the offset function g:
$$u^* = g+u$$

## Source
- Prof. Hiptmair - Numerical Methods for Partial Differential Equations, ETH lecture notes 2021, [[hiptmair-NUMPDE.pdf]]
