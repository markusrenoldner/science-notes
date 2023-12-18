[[Analysis]]


A vector
$$(\alpha_1,...,\alpha_d) \in \mathbb{N}_0^d$$
is called a multi index of order
$$|\alpha|:=\sum \alpha_i.$$
Partial derivatives for $C^\infty$-functions can be written as
$$

D^\alpha u(x)

\equiv \left( \frac{\partial}{\partial x_1} \right)^{\alpha_1}... \left( \frac{\partial}{\partial x_d} \right)^{\alpha_d}u

\equiv \frac{\partial^{\alpha_1}}{\partial x_1} ... \frac{\partial^{\alpha_d}}{\partial x_d} u

\equiv \partial^{\alpha_d}_1 ... \partial_d^{\alpha_d} u

$$
where $u(x):U\to \mathbb{R}, x=(x_1,..., x_d)\in U$.

WolframAlpha instead writes this:
$$D^\alpha u = u^\alpha$$

## Example

Assume $d=2$ and $\alpha = (1,3)$ then:
$$
D^\alpha u \equiv D^{(1,3)} u = \frac{\partial}{\partial x_1} \frac{\partial^3 u}{\partial x_2^3}
$$
Or in WolframAlpha notation:
$$D^{(1,3)}u=u^{(1,3)}$$

## Gradient, Hesse matrix, Laplace operator

Evans also defines an extension to the above notation for partial derivatives, one can define more complicated diff ops.
Let $k\in \mathbb{N}_0$ so $k$ is NOT a multiindex, its a natural number! Then
$$D^k u(x)$$
denotes a set of partial derivatives. For simple cases ($k=1,2,...$), one can identify this with the following differential operators:
$$\begin{aligned}

Du &\equiv D^1 u \equiv \nabla u \equiv (u_{x_1}, ..., u_{x_d}) & \quad \text{Gradient} \\

D^2 u &\equiv \begin{pmatrix}u_{x_1 x_1}&...&u_{x_1x_n}\\ \vdots \\ u_{x_nx_1} & ... \end{pmatrix} & \quad \text{Hessian} \\

\Delta u&\equiv \operatorname{tr}(D^2 u) & \quad \text{Laplacian} \\

\end{aligned}$$

## Source

- Evans - Partial Differential Equations, Appendix A.3: Notation for functions
- https://www.jku.at/fileadmin/gruppen/194/sobolev.pdf


