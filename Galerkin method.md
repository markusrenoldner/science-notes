[[Finite Element Method (FEM)]]

In the Galerkin method, we look for $u_h$ in a finite-dim subspace $V_h\subseteq V$ that fulfills the discrete problem $$a(u_h,v_h)=f(v_h)\quad \forall v_h.$$ As an example, $V_h$ could be the function space of polynomials up to a certain degree, which is finite dimensional. How to come up with these function spaces is explained in [[Local Finite Element interpolation]]


## Galerkin orthogonality:
If $u$ solves the weak problem and $u_h$ is its Galerkin approximation, we have
$$A\left(u-u_h, v_h\right)=0$$
as
$$
A\left(u-u_h, v_h\right)=A\left(u, v_h\right)-A\left(u_h, v_h\right)=f\left(v_h\right)-f\left(v_h\right)=0 \quad \forall v_h \in V_h.
$$
This means, that the error $u-u_h$ is orthogonal to our approximation space $V_h$/to all functions $v_h$ in this space. It allows the formulation of a very important lemma.


## Cea's Lemma for coercive blfs
coercive and continuous blf: see [[Lax-Milgram lemma]]
gives a best approximation property of the Galerkin method

Let the assumptions of the Galerkin orthogonality hold and $A(\cdot, \cdot)$ be continuous and coercive. Then,
$$
\left\|u-u_h\right\|_V \leq \alpha_2 / \alpha_1 \inf_{v_h}\left\|u-v_h\right\|_V
$$
i.e., the approximation error of the Galerkin method is quasi optimal.

Proof.
Let $v_h \in V_h$ be arbitrary. Using Galerkin orthogonality, we compute
$$
\begin{aligned}
\left\|u-u_h\right\|^2 & \leq \alpha_1^{-1} A\left(u-u_h, u-u_h\right) \\
& =\alpha_1^{-1} A\left(u-u_h, u-v_h\right)+\alpha_1^{-1} A(u-u_h, \underbrace{v_h-u_h}_{\in V_h}) \\
& =\alpha_1^{-1} A\left(u-u_h, u-v_h\right) \\
& \leq \alpha_2 / \alpha_1\left\|u-u_h\right\|\left\|u-v_h\right\| .
\end{aligned}
$$
Divide one factor $\left\|u-u_h\right\|_V$. Since $v_h \in V_h$ was arbitrary, the estimation holds true also for the infimum in $V_h$.


## Cea's Lemma for inf-sup stable blfs
inf-sup condition, see [[Inf-sup stability]]
We also get best-approximation lemma of the Galerkin approximation for inf-sup stable blfs, meaning we have quasi optimality:$$
\left\|u-u_h\right\|_V \leq \left(1+\frac{\beta_2}{\beta_{1h}}\right)\inf_{v_h}\left\|u-v_h\right\|_V
$$
(No proof in Faustmann)



## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
- https://en.wikipedia.org/wiki/Galerkin_method