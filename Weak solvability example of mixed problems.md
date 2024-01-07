# Weak solvability example of mixed problems
See [[Mixed variational problem]].


## Example 1: Neumann problem of the Poisson equation
Find $u\in V$ s.t. $$-\Delta u = f, \quad \frac{\partial u}{\partial n} = 0$$ or in weak form: $$\int \nabla u\nabla v = \int fv \quad \forall v\in W.$$ This problem is not unisolvent without further constraints (as one can add constants to the solution $u$ and get another solution). There are two options:
1. One can change the trialspace $V$ and only allow functions with $\int u=0$
2. One can change the problem, by adding an equation (this is usually easier): find $(u,p)\in H^1\times \mathbb{R}$, s.t. $$\begin{aligned}
&\int \nabla u\nabla v + p\int v && =\int fv  &&\forall v\in H^1 \\
&q\int u && =0  &&\forall q\in \mathbb{R}
\end{aligned}$$
If $(u,0)$ solves the 2nd problem, then $u$ also solves the 1st problem with the constraint. The adapted problem picks this solution automatically.

We can now apply [[Brezzi Theorem]] to show unisolvence. We have to check three conditions:
1. $a,b$ are continuous by Cauchy-Schwartz
2. $a$ is coercive on the Kernel of $b$. We have $\text{Ker}(b)=\{u\in H^1 : \int u=0\}$ and we can use the Poincare-Friedrichs inequality (see [[Trace operator]]) to show that $a$ is coercive, i.e. $a(u,u)\geq \alpha \Vert u\Vert^2\quad \forall u\in \text{Ker}(b)$.
3. LBB condition. Pick $u:=q$ and get $\Vert u \Vert_{H^1}= |q| |\Omega|^\frac{1}{2}$ and $$\Vert q\Vert_Q = |q|=\frac{q\cdot q}{|q|} = \frac{1}{|\Omega|^\frac{1}{2}} \frac{b(u,q)}{\Vert u\Vert_V},$$ which also holds for the supremum.



## Example 2: Mixed method for the flux (also Neumann problem)
Find $u\in V$ s.t. $$-\Delta u = f,\quad u=u_D \text{ on }\Gamma_D, \quad \frac{\partial u}{\partial n} = g\text{ on }\Gamma_N.$$ Now we define the flux $\sigma := \nabla u$ and get $$\begin{aligned}
\sigma-\nabla u &= 0 \\ \nabla \cdot \sigma &= -f
\end{aligned}$$ or in weak form $$\begin{aligned}
&\int \sigma \tau + \int (\nabla\cdot\tau)  u && =\int_{\Gamma_D} u_D \tau n &&\forall \tau \in V_0\\
&\int (\nabla\cdot \sigma) v && =-\int f v  &&\forall v \in Q
\end{aligned}$$ with $\sigma\in V=H(\operatorname{div})$ and $u\in Q=L^2$ and where we have applied integration by parts on the second integral in the first line to get the "block structure" (the final big matrix should be symmetric).

Remark: here we have Dirichlet BC in the blf and Neumann BC in the space definition, which is reversed as in the Poisson problem.

Again we can apply [[Brezzi Theorem]].
1. $a,b$ are continuous by Cauchy-Schwartz
2. $\text{Ker}(b(\tau,v))=\{\tau \in H(\operatorname{div}) : \operatorname{div} \tau=0\}$. This already gives $$a(\sigma,\sigma)=\int \sigma^2 = \Vert \sigma\Vert^2 + \underbrace{\Vert \operatorname{div}\sigma\Vert^2}_{=0} =\Vert \sigma\Vert^2_{H(\operatorname{div})}$$ 
3. LBB condition. Fix $v \in L^2$, and construct a $\sigma$ that satisfies LBB. Now we solve an artificial Poisson problem: $-\Delta \phi = v$ with $\phi = 0$ on $\partial \Omega$. By [[Lax-Milgram lemma]] we find $\Vert \nabla \phi \Vert\prec \Vert v \Vert$.
   Now we choose $\sigma:= -\nabla \phi\implies \operatorname{div}\sigma=v$. This yields $$\begin{aligned} &b(\sigma,v)=\int v^2 = \Vert v\Vert^2 \\
   &\Vert \sigma \Vert^2_{H(\operatorname{div})} =\Vert \underbrace{\sigma}_{-\nabla \phi} \Vert ^2 +\Vert \underbrace{\operatorname{div}(\sigma)}_v \Vert^2 \prec \Vert v \Vert^2\end{aligned}.$$ From this we follow $$\frac{b(\sigma,v)}{\Vert\sigma \Vert_{H(\operatorname{div})}} \geq \beta \Vert v\Vert.$$
We can now also check the solvability on the discrete spaces $Q_h\subset L^2$ and $V_h\subset H(\operatorname{div})$, as described in [[Brezzi Theorem]]. Continuity is inherited from the cont. setting.
1. Kernel ellipticity: we have $\operatorname{div} V_h \subset Q_h$, which gives $$
\int \operatorname{div} \sigma_h q_h d x=0 \quad \forall q_h \in Q_h  \implies  \operatorname{div} \sigma_h=0 
.$$ This implies that in this case $V_{0,h}\subset V_0$ which means the cont. coercivity implies the discrete one.
2. We want to construct a Fortin operator (see [[Brezzi Theorem]]) to check the LBB. We can use the Raviart-Thomas interpolation operator as the Fortin operator. The abstract condition form [[Brezzi Theorem]]:
$$
b\left(I_h^{R T} \sigma, v_h\right)=b\left(\sigma, v_h\right) \quad v_h \in Q_h
$$ reads as
$$
\int_T \operatorname{div} I_h^{R T} \sigma d x=\int_T \operatorname{div} \sigma d x
$$ which is a property of the interpolation operator.


## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
