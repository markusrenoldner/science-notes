# Mixed variational problem
Also read: [[Solvability of variational problems]]

## Definition
A mixed variational problem is a [[Variational problem]] involving two function spaces, and a bilinearform of a special saddle point structure ([[Saddle point problem]]). Usually, it is obtained from [[Variational problem]]s with constraints.

Consider $$\begin{aligned}
a(u,v):&V\times V\rightarrow \mathbb{R}  \\
b(u,q):&V\times Q\rightarrow \mathbb{R}\\
f(v):&V\rightarrow \mathbb{R}\\
g(q):&Q\rightarrow \mathbb{R}
\end{aligned}$$ with the problem to find $(u,p)\in V\times Q$ s.t. $$\begin{aligned}
&a(u,v) + b(v,p) &=f(v) \quad \forall v\in V \\
&b(u,q)&=g(q)\quad \forall q\in Q
\end{aligned}.$$ 

## Example: energy minimization under side constraint
seek minimum of functional $$J[b]:=\frac{1}{2}a(v,v)-f(v)$$ subject to the constraint $$b(v,q)=g(q)\quad \forall q.$$ $a,b$ are bilinearforms, $f,g$ are linearforms. 

Using the technique of Lagrangian multipliers, one can reformulate this as the problem to find stationary points - which turn out to be saddle points - of $$L(u,\lambda):=J[u]+b(u,\lambda)-g(\lambda)$$which then leads to the following problem: find $(u,p)$ s.t. $$\begin{aligned}
&a(u,v) + b(v,p) &=f(v) \quad \forall v\in V \\
&b(u,q)&=g(q)\quad \forall q\in Q
\end{aligned}$$


## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
- https://en.wikipedia.org/wiki/Mixed_finite_element_method