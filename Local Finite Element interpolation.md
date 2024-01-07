# Local Finite Element interpolation
[[Finite Element Method (FEM)]]


## Definition from Ciarlet
A finite element is a triple $(T, V^T, \Psi^T)$ where
- $T$ is a bounded set of points (e.g. an interval, a triangle, or tetrahedron) 
- $V^T$ is a finite dimensional function space in which functions can be interpolated. In [[Galerkin method]], we denote $V^T\equiv V_h$.
- $\Psi^T=\{\psi_1, ...\}$ is a set of linearly independent functionals from $V^T\rightarrow \mathbb{R}$ called "degrees of freedom"


## Basis functions on $V^T$
The linear functionals in $\psi^T$ allow the definition of a local nodal basis $\{\phi_1^T, ... \phi_{NT}^T\}$ (also called local shape functions) of $V^T$ by requiring 
$$\psi_i^T\left(\boldsymbol{\phi}_j^T\right)=\delta_{i j} .$$
this relates functionals and basis functions. The latter allow interpolation of functions in the local discrete space $V^T$ by the means of the local interpolation operator is defined as
$$
\begin{aligned}
I^T: C(T) & \rightarrow V^T \\
\boldsymbol{u} & \mapsto \sum_{j=1}^{N^T} \psi_j^T(\boldsymbol{u}) \boldsymbol{\phi}_j^T .
\end{aligned}
$$
Note that it is idempotent/it is a projection, i.e. $I^T\left(I^T \boldsymbol{u}\right)=I^T \boldsymbol{u}$.

Remark:
The functionals, and therefore also the shape functions can be chosen in different ways! There are different possible choices for $H^1$-spaces, but even different Finite Elements for other function spaces.
On $H(curl)$ the functionals are usually integrals over element edges, in $H(div)$ they are element-face integrals, while on $H^1$ we often use point evaluation functionals instead.


## Mesh/triangulation
The domain in which the given problem will be solved is being denoted by $\Omega \subset \mathbb{R}^d$. It will be divided into a finite number of elements. The result of dividing the domain into subdomains (corresponding to the bounded set $T$) is called a mesh or a triangulation.

A regular mesh $\mathcal{T}=\left\{T_1, \ldots T_N\right\}$ of a domain $\Omega \subset \mathbb{R}^d$ is a subdivision of $\Omega$ such that 
- $\Omega=\bigcup_i T_i$ 
- and that $T_i \cap T_{j \neq i}$ is empty for non-neighbour elements 
- or that $T_i \cap T_{j \neq i}$ is exactly one common vertex/edge/face for neighbour elements.


## Reference element
To reduce computational complexity, the functionals and therefore also the basis functions will be defined and computed on one standardised reference element and then transformed to each element.

For the reference element $\hat{T}$ and another ("physical") element $T$, let the transformation $F^T:\hat T \rightarrow T$ be affine linear and
1. $T=F^T(\hat{T})$
2. $u=\hat{u} \circ\left(F^T\right)^{-1}$ for $u \in V^T, \hat{u} \in V^{\hat{T}}$,
3. $\psi^T(u)=\psi^{\hat{T}}\left(u \circ F^T\right)$,
If such an $F^T$ exists, then the two elements $\left(T, V^T, \Psi^T\right)$ and $\left(\hat{T}, V^{\hat{T}}, \Psi^{\hat{T}}\right)$ are called affine equivalent. 
(Some FE dont satisfy these properties, and are only "interpolation equivalent": $I_T(u)\circ F = I_\hat T (u\circ F)$. All equivalent FEs are also interpolation equivalent.)

Interpretation:
1. The first property holds by construction of $F^T$. $V^T$ is then exactly the space $V^\hat T$ but on the physical element $T$.
2. The second property defines the basis function $u$ on the physical element. Let $\hat x:=\left(F^T\right)^{-1}(x)$ be a point on $\hat T$. This just means $u(x):=\hat u (\hat x)$.
3. The third property: notice that $\left(u \circ F^T\right)(\hat x) = u\left(F^T(\hat x)\right)=u(x)$. The reason why $\psi^\hat T$ is evaluated with $u(x)$ is that $\psi^\hat T$ does not care where $x$ is, only what value its argument (in this case $u$) has. The functional just maps its argument to a real number in a certain way (in this case it evaluates its argument at a certain point). The physical functional is characterised in a way that it "behaves exactly like the reference functional". The example below makes it clear:

Example:
$$\hat T = [0,1],\quad T=[2,3] $$
therefore: $F^T:x\mapsto x+2$ and $\left(F^T\right)^{-1} :x\mapsto x-2$.
Moreover, we set $\hat\psi_1(u)=u(0)$ and $\hat\psi_2(u)=u(1)$. 
The basis functions are $\hat\phi_1 = 1-x$ and $\hat\phi_2 = x$.
Now, we want to use the properties discussed before to find basis functions on $T$:
$$\begin{aligned}
\phi_1 &= \hat \phi_1\circ \left(F^T\right)^{-1} = 1-(x-2) = 3-x \\
\phi_2 &= \hat \phi_2\circ \left(F^T\right)^{-1} = x-2  \\
\end{aligned}$$
which is correct, as we defined the basis functions as hat functions. We can also transform the functionals:
$$\begin{aligned}
\psi_1(u) &= \hat \psi_1\circ \left(u\circ F^T\right) = \left(u\circ F^T\right)(0) = u(2) \\
\psi_2(u) &= \hat \psi_2\circ \left(u\circ F^T\right) = \left(u\circ F^T\right)(1) = u(3) \\
\end{aligned}$$
which is correct, as the functionals were defined as evaluations on the element boundary.




## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
