We derive an error estimation based on the knowledge of the exact solution.


## Goal:
we want to find a bound for the discretization error of the [[Finite Element Method (FEM)]]:$$\Vert u-u_h\Vert\leq ???$$ where $u_h$ is the discrete approximation of $u$.

We know $$\Vert u-u_h\Vert \preceq \inf_{v_h} \Vert u-v_h\Vert \preceq \Vert u- I_\mathcal{T} u\Vert$$the first inequality comes from Cea's lemma ([[Finite Element theory]]) and the second one from properties of the global interpolation operator introduced in [[Finite Element]]. The symbol $\preceq$ means $\leq$ up to constants.

The real goal is therefore to find an error bound for$$\Vert u- I_\mathcal{T} u\Vert.$$ We do this in 3 steps:
1. bound for the reference transformation
2. estimating the matrix $B$
3. estimating the interpolation error


## Estimate the reference transformation
Given: $F:\hat T\rightarrow T: x\mapsto a+Bx$, then:$$\Vert u\circ F\Vert_{H^m(\hat T)} \simeq (det B)^{-\frac{1}{2}}\Vert B\Vert^m \Vert u\Vert_{H^m(T)}$$ (the norms are defined on different triangles!)
Proof idea:
transformation theorem + chain rule.

## Estimate matrix B
Local mesh width: $h_T:=diam(T) = \sup[\vert x-y\vert, x,y\in T]$ 
Shape-regular mesh: if $\vert T\vert \geq \gamma h_t$ with $\gamma\approx 1$
Quasi-uniform mesh: $h\simeq h_T \quad \forall T$
There holds: $$\Vert B\Vert \simeq h_T, \quad \Vert B\Vert ^{-1}\simeq h_t^{-1}$$ (No proof.)


## Estimate interpolation error:
Let $\mathcal{T}$ be shape-regular, then we get $$\begin{align}\Vert u-I_\mathcal{T}v\Vert^2 &\preceq \sum_T h_T^4 \Vert v\Vert^2_{H^2}\\
\vert v-I_\mathcal{T}\vert_{H^1} &\preceq \sum_T h_T^2 \Vert v \Vert^2_{H^2}
\end{align}$$ Proof.
We prove the $H^1$ estimate, the $L_2$ one follows with the same arguments. The interpolation error on each element is transformed to the interpolation error on the reference element. Using the interpolation equivalence of the elements to the reference element gives
$$
\begin{aligned}
& \left|v-I_{\mathcal{T}} v\right|_{H^1(\Omega)}^2 \quad=\sum_{T \in \mathcal{T}}\left|v_T-I_T v_T\right|_{H^1(T)}^2 \\
& \stackrel{\text { Lem. }}{\leq}{ }^{4.7} C \sum_{T \in \mathcal{T}}\left(\operatorname{det} B_T\right)\left\|B_T^{-1}\right\|^2\left|\left(v_T-I_T v_T\right) \circ F_T\right|_{H^1(\widehat{T})}^2 \\
& =\quad \sum_{T \in \mathcal{T}}\left(\operatorname{det} B_T\right)\left\|B_T^{-1}\right\|^2\left|v_T \circ F_T-I_{\widehat{T}}\left(v_T \circ F_T\right)\right|_{H^1(\widehat{T})}^2 . \\
&
\end{aligned}
$$
On the reference element $\widehat{T}$ we apply the Bramble-Hilbert lemma, meaning that $\mid v_T \circ F_T-I_{\widehat{T}}\left(v_T \circ\right.$ $\left.F_T\right)\left.\right|_{H^1(\widehat{T})} \leq C\left|v_T \circ F_T\right|_{H^2(\widehat{T})}$. Then, we transform back to the individual elements, which gives
$$
\begin{aligned}
\left|v-I_{\mathcal{T}} v\right|_{H^1(\Omega)}^2 & \leq C \sum_{T \in \mathcal{T}}\left(\operatorname{det} B_T\right)\left\|B_T^{-1}\right\|^2\left|v_T \circ F_T\right|_{H^2(\widehat{T})}^2 \\
& \leq C \sum_{T \in \mathcal{T}}\left(\operatorname{det} B_T\right)\left\|B_T^{-1}\right\|^2\left(\operatorname{det} B_T^{-1}\right)\left\|B_T\right\|^4\left|v_T\right|_{H^2(T)}^2 \\
& =C \sum_{T \in \mathcal{T}} h_T^2|v|_{H^2(T)}^2 \cdot
\end{aligned}
$$
This gives the estimate in the $H^1$-seminorm.


## FEM convergence order
If the mesh $\mathcal{T}$ is additionally quasi-uniform with mesh-width $h$, there hold the interpolation error estimates
$$
\begin{aligned}
\left\|u-I_{\mathcal{T}} u\right\|_{L_2(\Omega)} & \leq C h^2|u|_{H^2(\Omega)} \\
\left|u-I_{\mathcal{T}} u\right|_{H^1(\Omega)} & \leq C h|u|_{H^2(\Omega)}
\end{aligned}
$$
Now, together with the Cea-lemma, we actually have derived convergence rates for the FEM.
Theorem 4.11 (Finite element convergence). Assume that
- the weak solution of the model problem is in $H^2(\Omega)$,
- the triangulation $\mathcal{T}$ is quasi-uniform with mesh-size $h$,
- the local finite element spaces contain $P^1$.
Then, the finite element error is bounded by
$$
\left\|u-u_h\right\|_{H^1(\Omega)} \leq C h|u|_{H^2(\Omega)}
$$
 



#todo 


## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
