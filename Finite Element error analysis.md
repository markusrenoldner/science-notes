# Finite Element error analysis
We derive an error estimation based on the knowledge of a smooth enough exact solution.

Here we denote seminorms by $|u-u_h|_{H^1} \equiv \Vert\nabla u-\nabla u_h\Vert_{L^2}$, see [[Energy norm]]. 

## Goal:
we want to find a bound for the discretization error of the [[Finite Element Method (FEM)]]:$$\Vert u-u_h\Vert\leq ???$$ where $u_h$ is the discrete approximation of $u$.

We know $$\Vert u-u_h\Vert \preceq \inf_{v_h} \Vert u-v_h\Vert \preceq \Vert u- I_\mathcal{T} u\Vert$$the first inequality comes from Cea's lemma ([[Galerkin method]]) and the second one from properties of the global interpolation operator introduced in [[Local Finite Element interpolation]]. The symbol $\preceq$ means $\leq$ up to constants.

The real goal is therefore to find an error bound for$$\Vert u- I_\mathcal{T} u\Vert.$$ We do this in 3 steps:
1. bound for the reference transformation
2. estimating the matrix $B(=F')$
3. estimating the interpolation error


## Estimate the reference transformation
Given: $F:\hat T\rightarrow T: x\mapsto a+Bx$, then:$$\Vert u\circ F\Vert_{H^m(\hat T)} \simeq (det B)^{-\frac{1}{2}}\Vert B\Vert^m \Vert u\Vert_{H^m(T)}$$ (the norms are defined on different triangles!)
Proof idea:
transformation theorem + chain rule.

## Estimate matrix B
Local mesh width: $h_T:=diam(T) = \sup[\vert x-y\vert, x,y\in T]$ 
Shape-regular mesh: if $\vert T\vert \geq \gamma h_t$ with $\gamma\approx 1$
There holds: $$\Vert B\Vert \simeq h_T, \quad \Vert B\Vert ^{-1}\simeq h_T^{-1}$$ (No proof.)


## Estimate interpolation error:
Assume
- $u\in H^2(\Omega)$
- $\mathcal{P}^1$-FEM space
- $\mathcal{T}$ shape-regular
Then: $$\begin{aligned}\Vert u-I_\mathcal{T}v\Vert^2 &\preceq \sum_T h_T^4 \Vert v\Vert^2_{H^2}\\
\vert v-I_\mathcal{T}\vert_{H^1} &\preceq \sum_T h_T^2 \Vert v \Vert^2_{H^2}
\end{aligned}$$ Proof.
We prove $H^1$ estimate, $L_2$ follows with the same arguments. Transform interp. error on each $T$ to $\hat T$ using interpolation equivalence, "IE" as defined in [[Local Finite Element interpolation]], as well as estimate of the reference transformation "RT": $$
\begin{aligned}
\left|v-I_{\mathcal{T}} v\right|_{H^1(\Omega)}^2  & \overset{IE}{=}\sum_{T }\left|v_T-I_T v_T\right|_{H^1(T)}^2 \\
& \overset{RT}{\preceq} \sum_{T }\left(\operatorname{det} B_T\right)\left\|B_T^{-1}\right\|^2\left|\left(v_T-I_T v_T\right) \circ F_T\right|_{H^1(\widehat{T})}^2 \\
& = \sum_{T }\left(\operatorname{det} B_T\right)\left\|B_T^{-1}\right\|^2\left|v_T \circ F_T-I_{\widehat{T}}\left(v_T \circ F_T\right)\right|_{H^1(\widehat{T})}^2 . \\
\end{aligned}$$ Now as $I_{\widehat{T}}\left(v_T \circ F_T\right) \in \mathcal{P}_1$, we use  Bramble-Hilbert, "BH" (see [[Sobolev space properties]]) with $k=2$, which means: $\vert v_T \circ F_T - I_\hat T(v_T \circ F_T )\vert_{H^1(\hat T)} \preceq \vert v_T \circ F_T \vert_{H^2(\hat T)}$ . The right hand side is the H2 seminorm. Then using "RT" again as well as the estimate for $B$, we transform back to $T$
$$
\begin{aligned}
\left|v-I_{\mathcal{T}} v\right|_{H^1(\Omega)}^2 & \overset{BH}{\preceq} \sum_{T }\left(\operatorname{det} B_T\right)\left\|B_T^{-1}\right\|^2\left|v_T \circ F_T\right|_{H^2(\widehat{T})}^2 \\
& \preceq\sum_{T }\left(\operatorname{det} B_T\right)\left\|B_T^{-1}\right\|^2\left(\operatorname{det} B_T^{-1}\right)\left\|B_T\right\|^4\left|v_T\right|_{H^2(T)}^2 \\
& \simeq \sum_{T } h_T^2|v|_{H^2(T)}^2 \cdot
\end{aligned}
$$
**Remark:** this is an "a priori" bound, as it bounds the error by $h$ times the exact sol. "A-posteriori" bounds are bounds by $h$ times the numerical sol.


## FEM convergence order
Assume additionally to before:
- $\mathcal{T}$ quasi-uniform
Then (somehow using Cea's lemma again):$$
\begin{aligned}
\left\|u-I_{\mathcal{T}} u\right\|_{L_2(\Omega)} & \leq C h^2|u|_{H^2(\Omega)} \\
\left|u-I_{\mathcal{T}} u\right|_{H^1(\Omega)} & \leq C h|u|_{H^2(\Omega)}
\end{aligned}
$$(without the sums of the previous estimate and with only one "h") which means convergence: $$u\overset{h\rightarrow 0}{\longrightarrow} u_h=I_\mathcal{T}u$$
The same result is stated here: https://uvilla.github.io/inverse17/02_IntroToFenics/ConvergenceRates.html .

Reducing h is called h-FEM. Increasing the polynomial error is called p-FEM. Comparing the two only valid with equal size of the FEM space dimension in each "improvement step":$$\text{dim}(\mathcal{P}^p)=p^d h^{-d}$$
## Shift theorem
"When does $u\in H^2$ hold?"

Let $u$ be the weak solution of $-\Delta u = f$, then
1. $\Omega$ convex, $f\in L^2 \implies u\in H^2(\Omega)$
2. $\Omega$ parameterizable by $C^\infty$-functions, $f\in H^k\implies u\in H^{k+2}$
In both cases the solution depends continuously on the data.

For $u\notin H^2$ (e.g. if the domain is not a convex polygon), one can use graded meshes to ensure convergence.


## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
