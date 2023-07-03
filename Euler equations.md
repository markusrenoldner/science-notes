Special case of [[Navier-Stokes equations]] with infinite Reynolds number. They are given as:
$$
\begin{align}
    \displaystyle\frac{\partial \mathbf{u}}{\partial t}+\mathbf{u} \cdot \nabla \mathbf{u} &=-\nabla p_{\text{stat}} + \boldsymbol{f} \\
    \displaystyle\nabla \cdot \boldsymbol{u} &= 0
\end{align}
$$

## Conservative form/conservation form:
$$
Y_t + \nabla \cdot J(Y) = 0
$$
with
$$Y=\begin{pmatrix} 1\\ \boldsymbol{u} \end{pmatrix} ,\quad J=\begin{pmatrix} \boldsymbol{u}\\ \boldsymbol{u}\otimes\boldsymbol{u} + p \mathbb{I}\end{pmatrix}$$
see [[Conservation law, transport equation]], and [[Numerical methods for conservation laws]].
