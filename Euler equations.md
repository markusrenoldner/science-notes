Special case of [[Navier-Stokes equations]] with infinite Reynolds number. They are given as:
$$
\begin{align}
    \displaystyle\frac{\partial \mathbf{u}}{\partial t}+\mathbf{u} \cdot \nabla \mathbf{u} &=-\nabla p_{\text{stat}} + \boldsymbol{f} \\
    \displaystyle\nabla \cdot \boldsymbol{u} &= 0
\end{align}
$$

## Conservative form/conservation form:
$$
y_t + \nabla \cdot J(y) = 0
$$
with
$$y=\begin{pmatrix} 1\\ \boldsymbol{u} \end{pmatrix} ,\quad J=\begin{pmatrix} \boldsymbol{u}\\ \boldsymbol{u}\otimes\boldsymbol{u} + p I\end{pmatrix}$$
