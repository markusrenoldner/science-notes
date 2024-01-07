# Weak solvability example
Analysing the weak form of the poisson problem for unisolvence. The problem can be solved using the [[Finite Element Method (FEM)]].


## With homogenious boundary conditions
Given problem: $\Omega\subset \mathbb{R}^d$ bounded, Lipschitz domain, $f\in L^2$, find $u \in H^1_0$ such that
$$-\Delta u = f, \qquad u=0\text{ on }\partial\Omega$$
the weak form/[[Variational problem]] can be found by multiplying with testfunctions $v\in  H^1_0$ and integrating by parts:$$A(u,v,):= \int \nabla u \nabla v = \int fv =: l(v) \quad\forall v.$$ This weak problem is unisolvent and its solution depends continuously on the data ("well posed"): $$\Vert u\Vert_{H^1} \leq \Vert f \Vert.$$
Proof.
- $A$ is continuous by Cauchy-Schwarz: $A(u,v) \leq \Vert u\Vert \Vert v \Vert \leq \Vert u\Vert_{H^1} \Vert v \Vert_{H^1}$.
- $A$ is coercive by Poincare-Friedrich: $\Vert u\Vert_{H^1}^2=\Vert u\Vert^2+\Vert \nabla u\Vert^2\leq (C_{PF}^2+1)\Vert\nabla u\Vert^2=(C_{PF}^2+1) A(u,u)$
- $l$ is continuous by Cauchy-Schwarz: $l(v)\leq \Vert v \Vert \Vert f \Vert \leq  \Vert v \Vert_{H^1} \Vert f \Vert$
By the [[Lax-Milgram lemma]], the problem above is unisolvent and well posed.


## With other boundary conditions
Let the boundary be decomposed as $\partial \Omega=\Gamma_D \cup$ $\Gamma_N \cup \Gamma_R$ according to Dirichlet, Neumann and Robin boundary conditions. $\Gamma_D$ has positive measure. We study
$$
\begin{aligned}
-\Delta u & =f & & \text { in } \Omega \\
u & =u_D & & \text { on } \Gamma_D \\
\nabla u \cdot n & =u_N & & \text { on } \Gamma_N \\
\nabla u \cdot n+\alpha u & =u_R & & \text { on } \Gamma_N
\end{aligned}
$$
We assume $u_D \in H^{1 / 2}\left(\Gamma_D\right), u_N \in L^2\left(\Gamma_N\right), u_R \in L^2\left(\Gamma_R\right), f \in L_2(\Omega)$, and $\alpha\in \mathbb{R}^+, v \in H_D^1(\Omega)$ 
The weak form is $$
\begin{aligned}
\int_{\partial \Omega} \nabla u \cdot n \operatorname{tr} v d s & =\int_{\Gamma_D} \nabla u \cdot n \operatorname{tr} v d s+\int_{\Gamma_N} \nabla u \cdot n \operatorname{tr} v d s+\int_{\Gamma_R} \nabla u \cdot n \operatorname{tr} v d s \\
& =0+\int_{\Gamma_N} u_N \operatorname{tr} v d s+\int_{\Gamma_R} u_R \operatorname{tr} v d s-\int_{\Gamma_R} \alpha \operatorname{tr} u \operatorname{tr} v d s .
\end{aligned}
$$ The Dirichlet integral vanishes, as the testfunction have zero trace there. We get
$$\begin{aligned}
A(u, v)&= \int_{\Omega} \nabla u \cdot \nabla v d x+\int_{\Gamma_R} \alpha \operatorname{tr} u \operatorname{tr} v\\
f(v)&=\int_{\Omega} f v d x+\int_{\Gamma_N} u_N \operatorname{tr} v d s+\int_{\Gamma_R} u_R \operatorname{tr} v
\end{aligned}$$
If $u_D=0$ this problem is solvable by [[Lax-Milgram lemma]].

For general $u_D$, the unknown $u$ is now in an [[Affine space]] and not in a vector space and we cant apply the lemma. But we can find a unique function $z$ with zero-Dirichlet boundary condition, for the adjusted problem $A(z,v)=f(v)-A(g,v)\quad \forall v$, with $\text{tr}g = u_D$. We can then recover $u=z+g$.
This is called "offset function trick" and is explained in more detail here: [[Variational problem]]. 


## Sources
Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021