[[Finite Element Method (FEM)]].

## Continuous setting
Consider the [[Variational problem]]: find $u\in \hat{V}$ such that 
$$a(u,v)=l(v) \quad \forall v\in V_0$$

A unique solution exists, if
- $a$ is an inner product, see [[Riesz-Representation theorem]]
- $a$ is coercive and continuous, see [[Lax-Milgram lemma]]
- $a$ is inf-sup stable, see [[Inf-sup stability]]


## Discrete/finite-dimensional setting
We approximate the [[Variational problem]] from above using the [[Galerkin method]]: Find $u_h \in V_h\subseteq V$ such that $$a(u_h,v_h)=f(v_h)\quad \forall v_h\in V_h.$$
A unique solution exists, if
- $a(.,.)$ is symmetric or if it is both coercive and continuous. Then one can apply [[Riesz-Representation theorem]] or [[Lax-Milgram lemma]] in the discrete setting. In this case, the unisolvence follows automatically from the continuous setting. We say that continuity and coercivity are inherited into the discrete setting, see section 2.2.3 of [1].
- $a$ is inf-sup stable, then one has to pose an extra inf-sup condition for the discrete problem! inf-sup stability does not get inherited into discrete setting!!! The discrete inf-sup condition is also stated here: [[Inf-sup stability]], see section 6.1 and 6.1.1 of [1]


## Mixed variational problems
Consider the [[Mixed variational problem]]: find $(u,p)\in V\times Q$ such that $$\begin{align}
&a(u,v) + b(v,p) &=f(v) \quad \forall v\in V \\
&b(u,q)&=g(q)\quad \forall q\in Q
\end{align}.$$
A unique solution exists, if
- $a$, $b$ are continuous, $a$ is coercive on $\text{Ker}[b]$, and the LBB-condition holds, see [[Brezzi Theorem]].
- the sum of both equations fulfills [[Inf-sup stability]] (which is a bit ugly as it doesnt take the saddle-point structure of the problem into account)

Solvability of mixed problems in the discrete setting is also discussed in [[Brezzi Theorem]].


## Sources
1. Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021