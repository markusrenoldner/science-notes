Is a [[Finite Element Method (FEM)]] with discontinuities in the solutions across element boundaries.


## Example advection equation:
[[Advection equation]]:
$$\partial_t u + \partial_x u = f$$
We can use a space-time-mesh to get a discontinuous [[Variational problem]]. (No time stepping is necessary then).
We get
$$\operatorname{div}_{t,x}(b\cdot u)=f,\quad \operatorname{div}_{t,x} = \partial_t+\partial_x,\quad b = (1,1)$$
so $b$ just makes $u$ a vector field on the space-time domain. The elements are subsets of the space-time domain:
$$K\subset \Omega \times (0,T)$$
Multiply with testfunc and integrate over a single element $K$ (not the whole domain):
$$\int_K \operatorname{div}_{x,t}(b\cdot u)v=-\int_K b\cdot u \nabla v + \int_{\partial K}b\cdot n_x uv$$
where the last integral appears. The kernel of this integral is called flux: $\psi_K:=b\cdot n_K u$
This integral doesnt appear in integrals over single elements in continuous FEmethods. It couples the elements.
Because of the continuity, its not clear from which $K$ or neighbour-$K$ to take this flux $\psi_K$.

A possible choice is the "upwind flux". We approximate $\psi_K$ by the numerical flux $\widehat{\psi}_K:=b\cdot n_K \hat{u}$. On the interface $\gamma'$ between the two elements $K$ and $K'$
$$\begin{align}
\hat{u}&:=u\vert_K ,\quad b \cdot n_K \geq 0  \quad\text{ "outflow of K"}\\
\hat{u}&:=u\vert_{K'},\quad b\cdot n_K <0
\end{align}$$
i.e. if flow from $K$ to $K'$ we take $\psi_K$, otherwise we take $\psi_{K'}$. In the bilinearform we then take the difference between $u$ and $\hat{u}$. The variational formulation over the whole domain is therefore:
$$\sum_K \int_K \operatorname{div}_{x,t}(b\cdot u)v- \int_{\partial K}b\cdot n_x (\hat{u}-u)v=-\int_K b\cdot u \nabla v $$
The term $\hat{u}-u=:[u]$ is also called "jump term" and it vanishes for an element, with outflow. 

The function space is:
$$u,v\in V_h:=\{v\in L^2: v\vert_K \in \mathcal{P}_k\}$$
Error analysis works similar to the continuous FEM.


## Benefit:
The contribution of each element $K$ to the matrix $A$ is completely indepenedent of each other element, so $A$ can be assembled in parallel very efficiently.

"Engineers love DG methods so much".
Prof. Faustmann (2022)


## Source:
- Prof. Faustmann