[[Tensor transformation]]

Example: (0,2)-tensor, aka. bilinear form ( $B:V\times V \to \mathbb{R}: (v,w)\mapsto v^i w^j B_{ij}$)
1. transformation: 
$$\begin{aligned}
B &= B_{ij} (\epsilon^i\otimes \epsilon^j)\\
&=B_{ij} (({F^i}_a \tilde \epsilon^a)\otimes({F^j}_b\tilde \epsilon^b))\\
&= B_{ij}{F^i}_a {F^j}_b (\tilde \epsilon^a \otimes\tilde \epsilon^b)\\
&= \tilde B_{ab} (\tilde \epsilon^a \otimes\tilde \epsilon^b)\\
&\implies \tilde B_{ab}= B_{ij}{F^i}_a {F^j}_b
\end{aligned}$$
2. tensor action (taking two vectors and outputting number):
$$\begin{aligned}
    b=B(v,w)&= B_{ij} (\epsilon^i\otimes \epsilon^j) (v^k e_k w^l e_l)\\
    &= B_{ij} v^k w^l \delta^i_k \delta^j_l\\
    &= B_{ij} v^i w^j \in \mathbb{R}
\end{aligned}$$
3. array shape: given by kronecker product of $\epsilon^i \otimes \epsilon^j$, which yields a row of rows:
$$
    \epsilon^1 \otimes \epsilon^1=\begin{pmatrix}1&0\end{pmatrix}\otimes \begin{pmatrix}1&0\end{pmatrix} = ... = \begin{pmatrix}\begin{pmatrix}1&0\end{pmatrix}&\begin{pmatrix}0&0\end{pmatrix}\end{pmatrix}
$$
The [[Metric tensor]] is a bilinearform.


