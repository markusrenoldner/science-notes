necessary introduction into the theoretical background of [[Finite Element Method (FEM)]].



## Bestapproximation property of Hilber spaces:
Let $S$ convex, Hilbert space $V$, $S\subseteq V$. Then, there exists a unique closest point $u_0 \in S$ 
$$
\left\|u-u_0\right\|_V \leq\|u-v\|_V \quad \forall v \in S, u \in V
$$

## Riesz-Representation theorem (inner products)
One can define the functional $l_u(v):= (u,v) \quad \forall v\in V$ for a fixed $u$, as the inner product is linear in $v$. But interestingly, one can also do the reverse:
One can always define an inner product with a unique $u_l$: $(u_l, v) := l(v) \quad \forall v$ with a fixed $l$. 

This gives unisolvence of the abstract problem to find a unique $u$ that satisfies $$(u,v)=f(v) \quad \forall v,$$ if $(.,.)$ is an inner product. 
It shows that the poisson problem $-\Delta u = f$ in weak form has a unique solution. This also works for the discrete approximation of this problem.


## Lax Milgram theorem (coercive, continuous BLFs)
[[Lax-Milgram lemma]]
It shows that variational problems with coercive, continuous bilinearforms are unisolvent. This also works for the discrete approximation of this problem.


## Galerkin method, Galerkin orthog, Cea's lemma
In the Galerkin method, were we look for $u_h$ in a finite-dim subspace $V_h\subseteq V$ that fulfils the discrete problem $$a(u_h,v_h)=f(v_h)\quad \forall v_h.$$For coercive bilinearforms, the unisolvence follows automatically from the continuous setting, as continuity and coercivity are inherited into the discrete setting.

Galerkin orthogonality:
If $u$ solves the weak problem and $u_h$ is its Galerkin approximation, we have
$$A\left(u-u_h, v_h\right)=0$$
as
$$
A\left(u-u_h, v_h\right)=A\left(u, v_h\right)-A\left(u_h, v_h\right)=f\left(v_h\right)-f\left(v_h\right)=0 \quad \forall v_h \in V_h.
$$
This means, that the error $u-u_h$ is orthogonal to our approximation space/to all functions in this space. It allows the formulation of a very important lemma.

Cea's Lemma (gives a best approximation property of the Galerkin method)
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


## Inf-Sup stable bilinearforms
Motivation: there are bilinearforms, that are not coercive and continuous (see [[Lax-Milgram lemma]]) and still yield a unisolvent [[Variational formulation, variational problem]]. Example: $$B(u,v)=u_1 v_1 - u_2 v_2 $$ is not coercive, but there is a unique solution to $$B(u,v)=f(v) \quad \forall v,$$which is: $$u=(f_1, -f_2)^\intercal.$$General (non-coercive) bilinearforms, denoted by $B(.,.)$, are called "inf-sup stable" if$$\inf_u \sup_v \frac{B(u,v)}{\Vert u\Vert_V \Vert v\Vert_W}\geq \beta \quad u\in V,v\in W.$$
Coercivity implies inf-sup stability.

Reformulate this as operator $B:V\rightarrow W^*$ with $\langle B u,v\rangle_{W^*\times W}=B(u,v)$, which yields the inf-sup condition as $$\sup_v \frac{\langle Bu,v\rangle}{\Vert v\Vert}\geq \beta \Vert u\Vert  \quad \forall u$$
We can see that an inf-sup stable $B$ is injective:
- by definition there holds $Bu=0 \implies u=0$
- and therefore, we get the following: $B(a)=B(b)\implies B(a)-B(b)=0\implies B(a-b)=0 \implies a=b$
The second relation is injectivity.

To get an invertible/unisolvent problem, we would like to have $B$ being bijective. We could turn around the inf-sup condition ("sup-inf"), or we ask for the (less restrictive) "non-degeneracy condition"/NDC: $$\sup_u\frac{B(u,v)}{\Vert u\Vert\Vert v\Vert}> 0\quad \forall v$$Coercivity also implies NDC.

The result is: inf-sup stable and NDC fulfilling bilinearforms yield a unisolvent variational problem and we have continuous dependence on the data $$\Vert u\Vert \leq \beta^{-1} \Vert f\Vert$$
## Approximation of inf-sup stable problems
Solvability is not inherited into discrete setting (!!!), so we pose a discrete inf-sup condition:$$\inf_{u_h} \sup_{v_h} \frac{B(u_h,v_u)}{\Vert u_h\Vert\Vert v_h\Vert}\geq \beta_{1h}$$ We dont need a discrete NDC. ("On a finite dimensional space, one to one is equivalent to onto, and therefore the discrete inf-sup condition already implies the non-degeneracy condition.")
The discrete inf-sup cond., like before, implies unisolvence.

We also get a Cea-type (see above) lemma:$$
\left\|u-u_h\right\|_V \leq \left(1+\frac{\beta_2}{\beta_{1h}}\right)\inf_{v_h}\left\|u-v_h\right\|_V
$$


## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
- https://en.wikipedia.org/wiki/Ladyzhenskaya%E2%80%93Babu%C5%A1ka%E2%80%93Brezzi_condition
- https://math.stackexchange.com/questions/2030380/proof-that-a-linear-transformation-is-injective-iff-its-null-space-is-trivial
- https://math.stackexchange.com/questions/3977138/why-is-linear-map-injectivity-defined-solely-using-the-null-space