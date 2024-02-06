# Numeric condition, stability, consistency, and convergence
[[Lax equivalence theorem]]
Condition number, see [[Numerical analysis]]


Let
- $P[\cdot]$ be a differential operator
- $N[\cdot]$ be a numerical scheme that approximates $P$
- $u$ be the exact solution of $P[u]=0$
- $u_h$ be an approximation of $u$ computed from $N[u_h]$

Then
- $P[u_h]-P[u]$, **condition**: how much does the problem vary under perturbation?
- $N[u_h]-N[u]$, **stability**: How much does the scheme vary under perturbation?
- $N[u]-P[u]$, **consistency**: How well does the scheme with exact input solve the problem?
- $N[u_h]-P[u]$ **convergence**: How well does the perturbed algorithm actually solve the problem?

#todo dangerous: $u$ is maybe not the solution actually.... this article is not correct probably


## Sources
- https://de.wikipedia.org/wiki/Stabilit%C3%A4t_(Numerik)