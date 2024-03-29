# Trace operator
As described in [[Function spaces]], $L^2$-functions that differ on sets with measure $0$ are "the same". This means, that boundary values are meaningless for these functions.
For functions in $H^1$ one can define boundary values, by the means of the trace operator:

## Existence of continuous trace operator
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

## Existence of multidimensional trace operator
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
For a special case of $\Omega \subset \mathbb{R}^2$ being a convex polygon and $v\in C^\infty$, we can show that $$\|v\|^2 \preceq\|v\|_{H^1}^2$$ which shows continuity of the trace operator map from $C^{\infty}({\Omega})$ to $L^2(\partial \Omega)$. By density of $C^{\infty}$ in $H^1$ this result can be extended to $H^1(\Omega)$.

## Trace space
By construction, every function in $H^1(\Omega)$ has a trace in $L^2(\partial\Omega)$, but not every function in $L^2(\partial\Omega)$ is the trace of some function in $H^1(\Omega)$ - i.e. the trace operator is not bijective on these spaces.
The following space "fixes" this:
$$H^\frac{1}{2}:=\{\text{tr}(u): u\in H^1(\Omega)\}$$ with the norm
$$\Vert \text{tr}u\Vert_{H^\frac{1}{2}}:= \inf_{\text{tr}u=\text{tr}v} \Vert v\Vert_{H^1}.$$
The trace operator allows the definition of spaces with boundary values, e.g.:
$$
H_0^1=\left\{u \in H^1(\Omega): \operatorname{tr} u=0\right\}.
$$

## Traces on subdomain interfaces
This theorem allows to construct globally $H^1$-"conforming" discrete subspaces.

Let $u \in L^2(\Omega)$ and $\Omega=\Omega_1 \cup \Omega_2 \cup F_{12}$ s.t.
- $u_i:=\left.u\right|_{\Omega_i} \in H^1\left(\Omega_i\right)$, and $g_i:=\nabla u_i$ is its weak gradient,
- traces on common interfaces of subdomains coincide: $\operatorname{tr}^{F_{12}} u_1=\operatorname{tr}^{F_{12}} u_2$.
Then, $u$ belongs to $H^1(\Omega)$, i.e. globally for the whole domain $\Omega$.

Proof. 
(Details in Faustmann, Theorem 3.16)
It suffices to show, that the weak gradient of $u$ is in $L^2$. The idea is to use the definition of the weak derivative/gradient. Apply Green's first integral formula on the subdomains $\Omega_i$ and use the fact that the outer normal vectors on common faces are oriented opposite to each other.


## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021