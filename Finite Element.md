[[Finite Element Method (FEM)]]


## Definition from Ciarlet
A finite element is a triple $(T, V^T, \Psi^T)$ where
- $T$ is a bounded set of points (e.g. an interval, a triangle, or tetrahedron) 
- $V^T$ is a finite dimensional function space in which functions can be interpolated
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
On $H(curl)$ the functionals are usually integrals over element edges, while on $H^1$ we often use point evaluation functionals instead.


## Mesh/triangulation
The domain in which the given problem will be solved is being denoted by $\Omega \subset \mathbb{R}^d$. It will be divided into a finite number of elements. The result of dividing the domain into subdomains (corresponding to the bounded set $T$ in definition 18) is called a mesh or a triangulation.

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
$$\begin{align}
\phi_1 &= \hat \phi_1\circ \left(F^T\right)^{-1} = 1-(x-2) = 3-x \\
\phi_2 &= \hat \phi_2\circ \left(F^T\right)^{-1} = x-2  \\
\end{align}$$
which is correct, as we defined the basis functions as hat functions. We can also transform the functionals:
$$\begin{align}
\psi_1(u) &= \hat \psi_1\circ \left(u\circ F^T\right) = \left(u\circ F^T\right)(0) = u(2) \\
\psi_2(u) &= \hat \psi_2\circ \left(u\circ F^T\right) = \left(u\circ F^T\right)(1) = u(3) \\
\end{align}$$
which is correct, as the functionals were defined as evaluations on the element boundary.


## Global point of view
The previous sections only discussed basis functions, etc. on one local element.

First we define the global interpolation operator $I_\mathcal{T}(\Omega)$ such that $$(I_\mathcal{T} u)\vert_T = I_T(u\vert_T)\quad \forall T\in \mathcal{T}$$
We define the global space $V_\mathcal{T}$ as the image of the global interpolation operator applied to smooth functions:$$V_\mathcal{T}:=\left\{ u=I_\mathcal{T}\omega:\omega\in C^m(\Omega)\right\}$$ alternatively, we can also define it as the subspace of $H^1$ (or another Sobolev space), whose elements are restricted to be polynomials of a certain degree: $$V_\mathcal{T}:=\left\{ u\in H^1(\Omega):u\vert_T \in \mathcal{P}^1(T) \quad\forall T\right\}$$
Global basis:
1. collect all linearly independent functionals $\psi_i^{T_i}$ from all elements $T_i$
2. identify functionals that coincide on element interfaces ("remove duplicates")
3. find $\phi_i$ by requiring globally: $\psi_j(\phi_i)=\delta_{ij}$ 

This is done by a so calloed "connectivity matrix" or a "local-global-map":
Matches indices of local and global functionals and global basis functions. This matrix/map has to be constructed once for each element.


## Assembly of the linear system of equations (in 1D)
The discrete problem by the Galerkin method is to find $u_h\in V_h$ st. $$a(u_h,v_h)=f(v_h)\quad \forall v_h\in V_h $$We interpolate the unknown $$u_h=I_\mathcal{T}u = \sum_i \underbrace{\psi_i(u)}_{=:u_i} \phi_i(x)$$where $u_i\in\mathbb{R}$ are the unknown coefficients of the final system; and we use the basis function as test functions: $$a\left(\sum_i u_i \phi_i, \phi_j\right)=f(\phi_j) \quad \forall j$$ We can use linearity of the blf. $a$ to pull out the $u_i$ and obtain $$A\vec{u}=\vec{f}$$with $A_{ji}=a(\phi_i,\phi_j), \vec{f}_j = f(\phi_j), \vec{u}_i=u_i$ (attention with the index order "ji" of $A$!). 
The matrix $A$ and the vector $\vec{f}$ are usually computed element-wise/locally, i.e. $A_T, \vec{f}_T$ by setting
$$A=\sum_T C_T A_T C_T^\intercal,\quad \vec{f}=\sum_T C_T \vec{f}_T$$
where $C_T$ is the connectivity matrix, briefly mentioned before. This is true due to the following calculation
$$
\begin{aligned}
\vec{f}_i & =f\left(\varphi_i\right)=\sum_{T \in \mathcal{T}} f_T\left(\left.\varphi_i\right|_T\right)=\sum_{T \in \mathcal{T}} f_T\left(\sum_{\ell} C_{T, i \ell} \varphi_T^{\ell}\right) \\
& =\sum_{T \in \mathcal{T}} \sum_{\ell} C_{T, i \ell} f_T\left(\varphi_T^{\ell}\right)=\sum_{T \in \mathcal{T}} \sum_{\ell} C_{T, i \ell} \vec{f}_{\ell}
\end{aligned}
$$
and
$$
\begin{aligned}
A_{j i} & =\sum_{T \in \mathcal{T}} A\left(\left.\varphi_i\right|_T,\left.\varphi_j\right|_T\right)=\sum_{T \in \mathcal{T}} A\left(\sum_{\ell} C_{T, i \ell} \varphi_T^{\ell}, \sum_k C_{T, j k} \varphi_T^k\right) \\
& =\sum_{T \in \mathcal{T}} \sum_{\ell} \sum_k C_{T, i \ell} A_{T, \ell k} C_{T, j k}
\end{aligned}
$$
The elements of the local matrix and vector are calculated only once on the reference element to save computation time. This is done by numerical quadrature (see [[Numerical analysis]]). For simple basis functions, the integrals can be computed exactly.

In the case of Dirichlet boundary conditions, let $\gamma_D \subset\{1, \ldots, N\}$ correspond to the vertices $x_i$ at the Dirichlet boundary, and $\gamma_f=\{1, \ldots N\} \backslash \gamma_D$.
We have the equations
$$
\sum_{i \in \gamma_D} A_{j i} u_i+\sum_{i \in \gamma_f} A_{j i} u_i=f_j \quad \forall j \in \gamma_f
$$
Inserting $u_i=u_D\left(x_D\right)$ for $i \in \gamma_i$ results in the reduced system
$$
\sum_{i \in \gamma_f} A_{j i} u_i=f_j-\sum_{i \in \gamma_D} A_{j i} u_D\left(x_i\right) .
$$
An overview of how to implement boundary conditions can be found here: [[Boundary conditions of linear systems]].

In 1D this suffices to know. 


## Assembly in higher dimensions
In higher dimensions we need to be more precise: the local matrices and right hand vectors are computed using the reference transformation introduced before

For the poisson problem the local objects looks like this: $$\begin{align}
A_T(\phi_i,\phi_j)&=\int_T\nabla\phi_i \nabla\phi_j = \int_{\widehat{T}} \nabla \widehat{\varphi}_i \cdot\left(F_T^{\prime}\right)^{-1}\left(F_T^{\prime}\right)^{-t} \nabla \widehat{\varphi}_j\left|\operatorname{det} F_T^{\prime}\right| \\ \vec{f}^T(\phi_j)&= ... =\int_{\widehat{T}} \widehat{f} \hat\phi_j\left|\operatorname{det} F_T^{\prime}\right|
\end{align}$$here $F'$ is the jacobi matrix of $F$. If $F$ is affine linear, i.e. $F=\vec{a}+B\vec{x}$, then $F'=B$.


## Assembly algorithm:

input: mesh $\mathcal{T}$, data $f$
initialize: ${A}:=0, \vec{f}:=0$
for $T \in \mathcal{T}$:
	compute $F_T$ and $F_T^{\prime}$
	compute ${A}^T$ and $\vec{f}^T$
	compute $C_T$ or the local-to-global map
	for $i\in{0, ... N_T}$:
		add element vector to global vector: $\vec{f}+=C_T \vec{f}^T$
		for $j\in 0,...N_T$:
			add element matrix to global matrix: $A+=C_T A_T C_T^\intercal$

For Dirichlet boundary conditions lines and columns corresponding to nodal basis functions with nodes on the Dirichlet boundary of the matrix A can be omitted. An overview of how to implement boundary conditions can be found here: [[Boundary conditions of linear systems]].


## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
- https://mfem.org/bilininteg/
- https://mfem.org/lininteg/
