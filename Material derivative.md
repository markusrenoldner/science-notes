

also convective or substantial derivative.

describes the time rate of change of a physical quantity (like heat or momentum) of a material element that is under the influence of a space and time dependent velocity field (=it moves).

Does appear in [[Fluid Dynamics]] .

For a quantity or tensor field $\phi(x,t)$ the material derivative is
$$\frac{D\phi}{Dt} \equiv \frac{\partial\phi }{\partial t}+ u \cdot \nabla \phi$$
where $u$ is the velocity field and $\nabla \phi$ is the "covariant derivative" of the tensor $y$ .


## Cartesian coordinates and $\phi:=u$
If $u$ is the 2- or 3- dimensional velocity, then in cart. coord. the material derivative looks like this 
$$\begin{align}\frac{Du}{Dt} &\equiv \frac{\partial u }{\partial t}+ (u \cdot \nabla )u \\
&= \frac{\partial u }{\partial t}+(u_x \partial_x + u_y  \partial_y) \begin{pmatrix}u_x\\u_y\end{pmatrix}  \\
&= \frac{\partial u }{\partial t}+\begin{pmatrix}u_x \partial_x u_x+ u_y  \partial_y u_x\\ u_x \partial_x u_y + u_y  \partial_y u_y\end{pmatrix}
\end{align}$$
here $u:=(u_x, u_y)^\intercal$.
If one does not apply the parantheses, the quantities should be rearranged so that the matrix vector product is noted correctly
$$\begin{align}\frac{Du}{Dt} &\equiv \frac{\partial u }{\partial t}+  (\nabla u) \cdot u\\
&=\frac{\partial u }{\partial t}+ \begin{pmatrix}\partial_x u_x & \partial_y u_x\\\partial_x u_y & \partial_y u_y\end{pmatrix}\cdot \begin{pmatrix}u_x\\u_y\end{pmatrix}\\
&= \frac{\partial u }{\partial t}+ \begin{pmatrix}u_x \partial_x u_x+ u_y  \partial_y u_x\\ u_x \partial_x u_y + u_y  \partial_y u_y\end{pmatrix}
\end{align}$$
In cartesian coordinates, the volicity gradient $\nabla u$ is the Jacobi matrix.



## Derivation
#todo derivation, eulerian/lagrangian viewpoint
#todo derivation in polar, spherical, general coordinates 



### Sources:
- https://en.wikipedia.org/wiki/Material_derivative
- Bartelmann 1, equation 8.186