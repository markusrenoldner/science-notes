
It is a symmetric, positive definite Bilinearform/(0,2)-tensor defined by dot products of basis vectors. It is used to 
... calculate dot products:
$$\begin{align}
    v\cdot w&= (v^1 e_1 + v^2 e_2)\cdot (w^1 e_1 + w^2 e_2)\\
    &= v^1 w^1 (e_1\cdot e_1)+v^1 w^2 (e_1\cdot e_2) + v^2 w^1 (e_\cdot e_2)+v^2 w^2 (e_2\cdot e_2) \\
    &=: v^i w^j \underbrace{e_i\cdot  e_j}_{=:g_{ij}\text{ ...metric tens.}}
\end{align}$$
... and vector lengths 
$$\begin{align}
    \Vert v \Vert ^2&\equiv v\cdot v \\
    &= v^i v^j e_i \cdot e_j \\
    &=: v^i v^j g_{ij}
\end{align}$$
... and angles between vectors
$$\begin{align}
    cos(\phi) &= \frac{v\cdot w}{\Vert v\Vert \Vert w\Vert}\\
    &= \frac{v^i w^j g_{ij}}{v^i v^j g_{ij} w^i w^j g_{ij} }
\end{align}$$
Transformation rule:
$$\begin{equation}
    \tilde g_{ij} \equiv \tilde e_i\cdot \tilde e_j =( {F^k}_ie_k)\cdot  ( {F^l}_j e_l) = {F^k}_i{F^l}_j g_{ij}
\end{equation}$$


## Raising and lowering indices
#todo video16




## Source:
Eigenchris playlist on Tensor algebra: https://www.youtube.com/playlist?list=PLJHszsWbB6hrkmmq57lX8BV-o-YIOFsiG