important numerical technique for partial differential equations/PDE (see [[Differential equations]] in [[Numerics for differential equations]]


## Idea of FEM
The endgoal is to transfer the PDE problem into a linear system of algebraic equations whose solution approximates the PDE.
This is done by deriving a [[Variational formulation, variational problem]]/weak form of the PDE to reduce regularity requirements. The solution of this weak form is interpolated in a finite dimensional function space (e.g. polynomials of a certain degree).


## Abstract FEM theory
### Bestapproximation property of Hilber spaces:
Let $S$ convex, Hilbert space $V$, $S\subseteq V$. Then, there exists a unique closest point $u_0 \in S$ 
$$
\left\|u-u_0\right\|_V \leq\|u-v\|_V \quad \forall v \in S, u \in V
$$
### Riesz-Representation theorem (inner products)
One can define the functional $l_u(v):= (u,v) \quad \forall v\in V$ for a fixed $u$, as the inner product is linear in $v$. But interestingly, one can also do the reverse:
One can always define an inner product with a unique $u_l$: $(u_l, v) := l(v) \quad \forall v$ with a fixed $l$. 

This gives unisolvence of the abstract problem to find a unique $u$ that satisfies $$(u,v)=f(v) \quad \forall v,$$ if $(.,.)$ is an inner product. 
It shows that the poisson problem $-\Delta u = f$ in weak form has a unique solution. This also works for the discrete approximation of this problem.

### Lax Milgram theorem (coercive, continuous BLFs)
[[Lax-Milgram lemma]]
It shows that variational problems with coercive, continuous bilinearforms are unisolvent.

### Galerkin method
In the Galerkin method, were we look for $u_h$ in a finite-dim subspace $V_h\subseteq V$ that fulfils the discrete problem $$a(u_h,v_h)=f(v_h)\quad \forall v_h.$$For coercive bilinearforms, the unisolvence follows automatically from the continuous setting, as continuity and coercivity are inherited into the discrete setting.

### Galerkin orthogonality
If $u$ solves the weak problem and $u_h$ is its Galerkin approximation, we have
$$A\left(u-u_h, v_h\right)=0$$
as
$$
A\left(u-u_h, v_h\right)=A\left(u, v_h\right)-A\left(u_h, v_h\right)=f\left(v_h\right)-f\left(v_h\right)=0 \quad \forall v_h \in V_h.
$$
This means, that the error $u-u_h$ is orthogonal to our approximation space/to all functions in this space. It allows the formulation of a very important lemma.

### Cea's Lemma (best approximation of the Galerkin method)
Let the assumptions of the previous lemma hold and $A(\cdot, \cdot)$ be continuous and coercive. Then,
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


## Sobolev space properties
The spaces are defined in [[Function spaces]].

### Meyers-Serrin theorem
This statement shows that smooth functions are dense in Sobolev spaces (i.e., for every function in the Sobolev space there exists a sequence of smooth functions that converges to this function). I.e.:
$C^\infty$ is dense in $H^k$ for all $k$. This is equivalent to saying$$C^\infty \subseteq H^k $$ and  $$\forall u \in H^k \quad \exists \text{ squence } f_i\in C^\infty  \text{ converging to  }u .$$
### Rellich compactness theorem
The follwing is a very strong theorem that states compactness of the inclusion of Sobolev spaces of higher orders. It says
$$H^l\subset H^k \quad \forall l>k \implies \iota:H^l\rightarrow H^k:u\mapsto u \text{ is compact}$$
Here $\iota$ is the "inclusion mapping". Interpretation: let $u_h\in H^l$ be bounded, then $\iota(u_h)$ has a convergent subsequence.

### Sobolev embedding theorem
Provided the order of differentiation is large enough Sobolev functions are actually continuous. If $k>\frac{n}{2}$, with $n$ being the space dimension, we have
$$H^k \subset C.$$ Example: in 2D ($n=2$), $H^1$ function are not necessarily continuous!

### Poincare inequality
Let $u\in H^1$ then
$$\Vert u \Vert \preceq \Vert \nabla u \Vert +  \left \vert \int u\right \vert$$
(we use $\preceq$ for $\leq$ up to constants, and we use the $L^2$-norm if not specified otherwise).
Proof: see Faustmann.

### Bramble-Hilbert lemma
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

## Trace operators and trace spaces
As described in [[Function spaces]], $L^2$-functions that differ on sets with measure $0$ are "the same". This means, that boundary values are meaningless for these functions.
For functions in $H^1$ one can define boundary values, by the means of the trace operator:

### Existence of continuous trace operator
There exists a well defined and continuous trace operator
$$
\operatorname{tr}: H^1(0, h) \rightarrow \mathbb{R}
$$
whose restriction to $C^1([0, h])$ coincides with
$$
u \rightarrow u(0).
$$
Proof.
Let $u \in C^1([0, h])$ with some $h>0$. Then, we can bound
$$
\begin{aligned}
u(0) & =\left.\left(1-\frac{x}{h}\right) u(x)\right|_{x=0} = -\int_0^h\left[\left(1-\frac{x}{h}\right) u(x)\right]^{\prime}   =-\int_0^h \frac{-1}{h} u(x)+\left(1-\frac{x}{h}\right) u^{\prime}(x) \\
& \leq\left\|\frac{1}{h}\right\|\|u\|+\left\|1-\frac{x}{h}\right\|\left\|u^{\prime}\right\| \\
& \simeq h^{-1 / 2}\|u\|+h^{1 / 2}\left\|u^{\prime}\right\|\\
& \simeq \Vert u \Vert _{H^1}.
\end{aligned}
$$
The value on to boundary for a continuous function is bounded by the $H^1$-norm.
Now we use the Meyers-Serrin theorem: $C^1$ is dense in $H^1$
Let $u\in H^1$, $u_j\in C^1$ and $u_j \rightarrow u$. Then
- $\vert u_m(0)-u_n(0) \vert \leq \Vert u_m- u_n\Vert_{H^1} \rightarrow 0$
- $u_j(0)$ has exactly 1 limit in $\mathbb{R}$ which is independent of the choice of the sequence (as $\mathbb{R}$ is complete and $u_j(0)$ is a Cauchy sequence). This limit is called trace of $u$, denoted by $\text{tr}(u)$.

### Existence of multidimensional trace operator
There exists a well defined and continuous trace operator
$$
\operatorname{tr}: H^1(\Omega) \rightarrow L^2(\partial \Omega)
$$
which coincides with $\left.u\right|_{\partial \Omega}$ for $u \in C^1$ and is continuous:
$$
	\|\operatorname{tr} u\| \preceq\|u\|_{H^1}
$$
Proof. 
(Details in Faustmann, Theorem 3.13)
For a special case of $\Omega \subset \mathbb{R}^2$ being a convex polygon and $v\in C^\infty$, we can show that $$\|v\|^2 \preceq\|v\|_{H^1}^2$$ which shows continuity of the trace operator mapping from $C^{\infty}({\Omega})$ to $L^2(\partial \Omega)$. By density of $C^{\infty}$ in $H^1$ this result can be extended to $H^1(\Omega)$.

### "Trace space"
By construction, every function in $H^1(\Omega)$ has a trace in $L^2(\partial\Omega)$, but not every function in $L^2(\partial\Omega)$ is the trace of some function in $H^1(\Omega)$ - i.e. the trace operator is not bijective on these spaces.
The following space "fixes" this:
$$H^\frac{1}{2}:=\{\text{tr}(u): u\in H^1(\Omega)\}$$ with the norm
$$\Vert \text{tr}u\Vert_{H^\frac{1}{2}}:= \inf_{\text{tr}u=\text{tr}v} \Vert v\Vert_{H^1}.$$
The trace operator allows the definition of spaces with boundary values, e.g.:
$$
H_0^1=\left\{u \in H^1(\Omega): \operatorname{tr} u=0\right\}.
$$

### Traces on subdomain interfaces
This theorem allows to construct globally $H^1$-"conforming" discrete subspaces.

Let $u \in L^2(\Omega)$ and $\Omega=\Omega_1 \cup \Omega_2 \cup F_{12}$ s.t.
- $u_i:=\left.u\right|_{\Omega_i} \in H^1\left(\Omega_i\right)$, and $g_i:=\nabla u_i$ is its weak gradient,
- traces on common interfaces of subdomains coincide: $\operatorname{tr}^{F_{12}} u_1=\operatorname{tr}^{F_{12}} u_2$.
Then, $u$ belongs to $H^1(\Omega)$, i.e. globally for the whole domain $\Omega$.

Proof. 
(Details in Faustmann, Theorem 3.16)
It suffices to show, that the weak gradient of $u$ is in $L^2$. The idea is to use the definition of the weak derivative/gradient. Apply Green's first integral formula on the subdomains $\Omega_i$ and use the fact that the outer normal vectors on common faces are oriented opposite to each other.

### Poincare-Friedrichs inequality
A stronger variant of the Poincare inequality for functions with zero trace.
Let $\Gamma_D\subset \partial\Omega$, then $$\Vert v \Vert \preceq \Vert \nabla v \Vert \quad \forall v\in H^1_D$$ where $H^1_D:=\{u \in H^1(\Omega): \operatorname{tr} u=0 \text{ on }\Gamma_D\}.$

This is much better than the Poincare inequality!


## Example: analyzing the weak form of the Poisson equation
### With homogenious boundary conditions
Given problem: $\Omega\subset \mathbb{R}^d$ bounded, Lipschitz domain, $f\in L^2$, find $u \in H^1_0$ such that
$$-\nabla u = f, \qquad u=0\text{ on }\partial\Omega$$
the weak form can be found by multiplying with testfunctions $v\in  H^1_0$ and integrating by parts:$$A(u,v,):= \int \nabla u \nabla v = \int fv =: l(v) \quad\forall v.$$ This weak problem is unisolvent and its solution depends continuously on the data ("well posed"): $$\Vert u\Vert_{H^1} \leq \Vert f \Vert.$$
Proof.
- A is continuous by Cauchy-Schwarz: $A(u,v) \leq \Vert u\Vert \Vert v \Vert \leq \Vert u\Vert_{H^1} \Vert v \Vert_{H^1}$.
- A is coercive by Poincare-Friedrich: $\Vert u\Vert_{H^1}^2=\Vert u\Vert^2+\Vert \nabla u\Vert^2\leq (C_{PF}^2+1)\Vert\nabla u\Vert^2=(C_{PF}^2+1) A(u,u)$ 
- l is continuous by Cauchy-Schwarz: $l(v)\leq \Vert v \Vert \Vert f \Vert \leq  \Vert v \Vert_{H^1} \Vert f \Vert$
By the Lax-Milgram lemma, the problem above is unisolvent and well posed.

### With other boundary conditions
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
$$\begin{align}
A(u, v)&= \int_{\Omega} \nabla u \cdot \nabla v d x+\int_{\Gamma_R} \alpha \operatorname{tr} u \operatorname{tr} v\\
f(v)&=\int_{\Omega} f v d x+\int_{\Gamma_N} u_N \operatorname{tr} v d s+\int_{\Gamma_R} u_R \operatorname{tr} v
\end{align}$$
If $u_D=0$ this problem is solvable by [[Lax-Milgram lemma]].

For general $u_D$, the unknown $u$ is now in an [[Affine space]] and not in a vector space and we cant apply the lemma. We can try to solve for a function $z$ with zero-Dirichlet boundary condition, for the adjusted problem $A(z,v)=f(v)-A(\tilde u,v)\text{ }\forall v$, with $\text{tr}\tilde u = u_D$, we get a unique solution. We can then recover $u=z+\tilde u$.
This is called "offset function trick" and is exaplained in more detail here: [[Variational formulation, variational problem]].


## todolist
#todo insert fausit summary for diplimprüfung, structure:

- FEM (fausti+thesis)
	- Def, local interp, equivalence, mesh [[Finite Element]]
	- gobal basis
	- assembly
	- error analysis
- adaptivity
- mixed forms
- applications (stokes, convection, maxwell)
#todo include this some info on assembly:
- https://mfem.org/bilininteg/#bilinear-form-integrators
- https://mfem.org/lininteg/#:~:text=Linear%20form%20integrators%20are%20the,sometimes%20over%20edges%20or%20faces
#todo split this note into subnotes



## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
- Prof. Hiptmair - Numerical Methods for Partial Differential Equations, ETH lecture notes 2021, [[hiptmair-NUMPDE.pdf]]
- Prof. Schöberl - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2020
