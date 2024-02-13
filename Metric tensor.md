# Metric tensor
[[Tensor and multilinear algebra]]
[[Example (0,2)-tensor transformation]]


## Definition 
for basis vectors $\boldsymbol{e}_i$:
$$g_{ij} \equiv \left\langle \boldsymbol{e}_i , \boldsymbol{e}_j \right \rangle \equiv \boldsymbol{e}_i \cdot \boldsymbol{e}_j$$
with the standard, scalar product in $\mathbb{R}^d$.

## Example usage:
It is a symmetric, positive definite Bilinearform/(0,2)-tensor. It is used to 
... calculate dot products:
$$\begin{aligned}
    v\cdot w&= (v^1 e_1 + v^2 e_2)\cdot (w^1 e_1 + w^2 e_2)\\
    &= v^1 w^1 (e_1\cdot e_1)+v^1 w^2 (e_1\cdot e_2) + v^2 w^1 (e_\cdot e_2)+v^2 w^2 (e_2\cdot e_2) \\
    &=: v^i w^j \underbrace{e_i\cdot  e_j}_{=:g_{ij}\text{ ...metric tens.}}
\end{aligned}$$
... and vector lengths 
$$\begin{aligned}
    \Vert v \Vert ^2&\equiv v\cdot v \\
    &= v^i v^j e_i \cdot e_j \\
    &=: v^i v^j g_{ij}
\end{aligned}$$
... and angles between vectors
$$\begin{aligned}
    cos(\phi) &= \frac{v\cdot w}{\Vert v\Vert \Vert w\Vert}\\
    &= \frac{v^i w^j g_{ij}}{v^i v^j g_{ij} w^i w^j g_{ij} }
\end{aligned}$$
Transformation rule:
$$
    \tilde g_{ij} \equiv \tilde e_i\cdot \tilde e_j =( {F^k}_ie_k)\cdot  ( {F^l}_j e_l) = {F^k}_i{F^l}_j g_{ij}
$$


## Raising and lowering indices
See eigenchris video16


## Source:
Eigenchris playlist on Tensor algebra: https://www.youtube.com/playlist?list=PLJHszsWbB6hrkmmq57lX8BV-o-YIOFsiG