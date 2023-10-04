[[Finite Element Method (FEM)]]


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

For the poisson problem the local objects looks like this: $$\begin{aligned}
A_T(\phi_i,\phi_j)&=\int_T\nabla\phi_i \nabla\phi_j = \int_{\widehat{T}} \nabla \widehat{\varphi}_i \cdot\left(F_T^{\prime}\right)^{-1}\left(F_T^{\prime}\right)^{-t} \nabla \widehat{\varphi}_j\left|\operatorname{det} F_T^{\prime}\right| \\ \vec{f}^T(\phi_j)&= ... =\int_{\widehat{T}} \widehat{f} \hat\phi_j\left|\operatorname{det} F_T^{\prime}\right|
\end{aligned}$$here $F'$ is the jacobi matrix of $F$. If $F$ is affine linear, i.e. $F=\vec{a}+B\vec{x}$, then $F'=B$.


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
