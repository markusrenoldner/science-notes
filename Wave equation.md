[[Differential equations]]


## "Traditional" form
Find $u$ (scalar valued) such that

$$
    \partial_{tt} u + \Delta u = 0
$$

## Energy conservation quantity

start in 1D, and assume $u\in C^2(\Omega)$, and $\Omega \subseteq \mathbb{R}$ and 
$$
    \partial_{tt}u = \partial_{xx} u
$$
we use the fact that $\frac{1}{2}\partial_t u^2 = u\partial_t u$ (and similarly for $\partial_x$) and get 
$$\begin{aligned}
    \frac{1}{2}\partial_t (\partial_t u)^2 = \partial_t u\partial_{tt} u,\qquad \frac{1}{2}\partial_t (\partial_x u)^2 = \partial_x u\partial_{tx} u\\
\end{aligned}$$
then we multiply the wave equation with $\partial_t u$ and integrate over the domain
$$\begin{aligned}
    \partial_t \left [ \frac{1}{2} \int_\Omega (\partial_t u)^2 \right ] - \int_\Omega \partial_t u \partial_{xx} u &= 0 \\
\end{aligned}$$
now we integrate the second integral by parts, use the identity from before and $\partial_{xt}=\partial_{tx}$
$$\begin{aligned}
    \partial_t \left [ \frac{1}{2} \int_\Omega (\partial_t u)^2 \right ] + \int_\Omega \partial_{xt} u \partial_{x} u - \int_{\partial\Omega}\partial_{t} u \partial_{x} u &= 0 \\    
    \partial_t \left [ \frac{1}{2} \int_\Omega (\partial_t u)^2 \right ] + \int_\Omega \partial_{xt} u \partial_{x} u - \int_{\partial\Omega}\partial_{t} u \partial_{x} u &= 0 \\    
    \partial_t \left [ \frac{1}{2} \int_\Omega (\partial_t u)^2  + (\partial_x u)^2 \right ]- \int_{\partial\Omega}\partial_{t} u \partial_{x} u &= 0 
\end{aligned}$$
which means, that the energy 
$$1/2\int_\Omega (\partial_t u)^2  + (\partial_x u)^2$$ is conserved up to boundary contributions. The for a multidimensional domain $\Omega$ yields (without boundary terms)
$$
    \partial_t \left [ \frac{1}{2} \int_\Omega (\partial_t u)^2  + (\partial_x u)^2 + (\partial_y u)^2+ (\partial_z u)^2\right ]= 0 
$$


## vector valued unknown u

Using the vector gradient, and taking the divergence of the resulting 2-tensor gives the vector Laplacian (see [[Vector analysis identities]]). Then, the wave equation becomes:
$$\begin{aligned}
    \begin{pmatrix}\partial_t u_1\\\partial_t u_2\\\partial_t u_3\end{pmatrix}= 
    \begin{pmatrix}
    \partial_{xx} u_1 + \partial_{yy} u_1 + \partial_{zz} u_1 \\
    \partial_{xx} u_2 + ... + ...\\
    \partial_{xx} u_3 + ... + ...
    \end{pmatrix}
\end{aligned}$$
which is exactly one scalar wave equation for each component. Therefore, the conservation proof from before can be applied to each component separately.


## Velocity-stress form

$u\in C^2(\Omega)$ is scalar, $\boldsymbol{\sigma}\in \left [C^2 (\Omega)\right ]^3$ is vector-valued, and $\Omega \subseteq \mathbb{R}^3$, then the velocity-stress form is:
$$\begin{aligned}
    \partial_t u + \text{div} \boldsymbol{\sigma} &= 0\\
    \partial_t \boldsymbol{\sigma} + \nabla u &= 0
\end{aligned}$$
now take the time derivative of the first, and the divergence of the second equation
$$\begin{aligned}
\partial_{tt} u + \partial_t (\text{div} \boldsymbol{\sigma}) &= 0\\ 
\partial_t (\text{div} \boldsymbol{\sigma}) + \text{div}(\nabla u) &= 0    
\end{aligned}$$
now subtract the second from the first equation and get the traditional form.


## conservation property of velocity-stress form

again, $\boldsymbol{u}$ is a vector, $\sigma$ is a 2-tensor, and $\Omega \subseteq \mathbb{R}^3$. Multiply the first equation by $u$ and the second by $\sigma$, and we get
$$\begin{aligned}
    \boldsymbol{u}\partial_t \boldsymbol{u} + \boldsymbol{u}\text{div} \boldsymbol{\sigma} &= 0\\
    \boldsymbol{\sigma} \partial_t \boldsymbol{\sigma} + \boldsymbol{\sigma} \nabla \boldsymbol{u} &= 0
\end{aligned}$$

Now we use $\boldsymbol{u}\partial_t \boldsymbol{u} = \frac{1}{2}\partial_t (\boldsymbol{u}^2)$, integrate over the domain and use integration by parts:
$$\begin{aligned}
    0=& \frac{1}{2}\partial_t \int_\Omega \boldsymbol{u}^2 + \int_\Omega \boldsymbol{u} \text{div} \boldsymbol{\sigma} \\
    =& \frac{1}{2}\partial_t \int_\Omega \boldsymbol{u}^2 - \int_\Omega \nabla \boldsymbol{u}  \boldsymbol{\sigma} + \int_{\partial \Omega} \boldsymbol{u}\boldsymbol{\sigma}\cdot  e_n \\
\end{aligned}$$
now we replace the second integral using the second equation from the velocity-stress formulation and apply the identity for derivatives of a square from before:
$$\begin{aligned}
    0=& \frac{1}{2}\partial_t \int_\Omega \boldsymbol{u}^2 + \int_\Omega \boldsymbol{\sigma} \partial_t \boldsymbol{\sigma} -\int_{\partial \Omega} \boldsymbol{u}\boldsymbol{\sigma}\cdot  e_n \\
    =& \frac{1}{2}\partial_t \int_\Omega \boldsymbol{u}^2 + \frac{1}{2} \partial_t \int_\Omega \boldsymbol{\sigma}^2  - \int_{\partial \Omega} \boldsymbol{u}\boldsymbol{\sigma} \cdot e_n \\
    =& \frac{1}{2}\partial_t \int_\Omega (\boldsymbol{u}^2 +\boldsymbol{\sigma}^2) - \int_{\partial \Omega} \boldsymbol{u}\boldsymbol{\sigma} \cdot e_n \\
\end{aligned}$$

The velocity-stress form conserves
$$
    \frac{1}{2}\int_\Omega (\boldsymbol{u}^2 +\boldsymbol{\sigma}^2)
$$
which is different than the quantity from the traditional form.