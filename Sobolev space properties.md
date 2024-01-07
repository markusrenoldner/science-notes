# Sobolev space properties
some properties of Sobolev spaces in the framework of the [[Finite Element Method (FEM)]].
The function spaces itself are defined in [[Function spaces]].


## Meyers-Serrin theorem
This statement shows that smooth functions are dense in Sobolev spaces (i.e., for every function in the Sobolev space there exists a sequence of smooth functions that converges to this function). I.e.:
$C^\infty$ is dense in $H^k$ for all $k$. This is equivalent to saying$$C^\infty \subseteq H^k $$ and  $$\forall u \in H^k \quad \exists \text{ squence } f_i\in C^\infty  \text{ converging to  }u .$$
## Rellich compactness theorem
The follwing is a very strong theorem that states compactness of the inclusion of Sobolev spaces of higher orders. It says
$$H^l\subset H^k \quad \forall l>k \implies \iota:H^l\rightarrow H^k:u\mapsto u \text{ is compact}$$
Here $\iota$ is the "inclusion map". Interpretation: let $u_h\in H^l$ be bounded, then $\iota(u_h)$ has a convergent subsequence.

## Sobolev embedding theorem
Provided the order of differentiation is large enough Sobolev functions are actually continuous. If $k>\frac{n}{2}$, with $n$ being the space dimension, we have
$$H^k \subset C.$$ Example: in 2D ($n=2$), $H^1$ function are not necessarily continuous!

## Poincare inequality
Let $u\in H^1$ then
$$\Vert u \Vert \preceq \Vert \nabla u \Vert +  \left \vert \int u\right \vert$$
(we use $\preceq$ for $\leq$ up to constants, and we use the $L^2$-norm if not specified otherwise).
Proof: see Faustmann.

## Bramble-Hilbert lemma
Taking the Poincare inequality and replacing $u$ by $w:=u-\frac{1}{|\Omega|} \int_{\Omega} u$, with $w\in H^1(\Omega)$ then $\implies \int w =0$.
Then we get
$$
\left\|u-\frac{1}{|\Omega|} \int_{\Omega} u\right\| \preceq \|\nabla u\|
$$
The Bramble-Hilbert lemma generalizes this to higher dimensions
Let $\mathcal{P}_k$ be the space of polynomials of maximal degree $k$. Let $u \in H^k(\Omega)$. Then,
$$
\inf _{p \in \mathcal{P}_{k-1}}\|u-p\|_{H^k(\Omega)} \preceq \Vert\nabla u\Vert
$$
Interpretation: choose a clever constant/polynomial to subtract from $u$ and you can bound $u$ by its derivatives!


## Poincare-Friedrichs inequality
A stronger variant of the Poincare inequality for functions with zero trace (see [[Trace operator]]).
Let $\Gamma_D\subset \partial\Omega$, then $$\Vert v \Vert \preceq \Vert \nabla v \Vert \quad \forall v\in H^1_D$$ where $H^1_D:=\{u \in H^1(\Omega): \operatorname{tr} u=0 \text{ on }\Gamma_D\}.$

This is much better than the Poincare inequality!



## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021