# Vector analysis identities


There holds that
$$\nabla\times(\nabla\times f)\equiv \nabla(\nabla\cdot f) - \nabla\cdot (\nabla f)$$
and
$$\nabla\times \nabla f \equiv 0$$
and 
$$\nabla\cdot (\nabla\times f) \equiv 0$$
and (vector gradient)
$$\nabla \vec{f} = \nabla \otimes \vec{f} = \nabla\cdot \vec{f}^\intercal$$
and (vector Laplacian)
$$\Delta \vec{f} = \nabla\cdot(\nabla \vec{f}) = \nabla\cdot (\nabla \otimes \vec{f}) = \partial_x^2 \vec{f} + \partial_y^2 \vec{f} +...$$

[[Integration by parts for the curl operator]]

Integration by parts for $u, \boldsymbol{v}$:
$$\int_\Omega u\nabla\cdot \boldsymbol{v} = -\int_\Omega\nabla u \cdot \boldsymbol{v}+ \int_{\partial\Omega} u\boldsymbol{v}\cdot e_n $$
Integration by parts for Laplace op:
$$\int_\Omega v\Delta u = -\int_\Omega \nabla u \nabla v + \int_{\partial\Omega}v  \nabla u\cdot e_n$$
[[Leibnitz integral rule for higher dimensions]]



## Vector laplacian
vector laplace operator in cartesian coords:
$$\begin{aligned}
    \Delta \boldsymbol{u} &\equiv \nabla\cdot (\nabla \boldsymbol{u})\\
    (\Delta \boldsymbol{u})_{ij} & \equiv \nabla\cdot \left ( \frac{\partial u_i}{\partial x_j} \right ) = 
    \nabla\cdot 
    \begin{pmatrix}
    \frac{\partial u_1}{\partial_x} & 
    \frac{\partial u_1}{\partial_y} & 
    \frac{\partial u_1}{\partial_z} \\
    \frac{\partial u_2}{\partial_x} 
    & ... \\ 
    \frac{\partial u_3}{\partial_x} 
    & ... 
    \end{pmatrix} \equiv \nabla\cdot J_{ij}
\end{aligned}$$
where $J$ is the Jacobi-matrix. The divergence of a matrix (or rather: of a 2-tensor) is
$$
    \nabla\cdot J_{ij} = \frac{\partial J_{ik}}{\partial x_k} \boldsymbol{e}_i = 
    \begin{pmatrix}
    \frac{\partial J_{11}}{\partial_x} + \frac{\partial J_{12}}{\partial_y} + \frac{\partial J_{13}}{\partial_z}\\
    \frac{\partial J_{21}}{\partial_x} + ... + ...\\
    \frac{\partial J_{31}}{\partial_x}  + ... + ...
    \end{pmatrix}
$$
this gives
$$
    \Delta \boldsymbol{u}= \begin{pmatrix}\Delta u_1 \\\Delta u_2 \\ \Delta u_3 \end{pmatrix} = 
    \begin{pmatrix}
    \partial_{xx} u_1 + \partial_{yy} u_1 + \partial_{zz} u_1 \\
    \partial_{xx} u_2 + ... + ...\\
    \partial_{xx} u_3 + ... + ...
    \end{pmatrix}
$$

## Source
- Prof Schütz Grundlagen der Physik 2 TU Wien 2021
- https://en.wikipedia.org/wiki/Vector_calculus_identities