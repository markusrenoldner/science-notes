[[Tensor transformation]]

Example: (1,1)-tensor, aka. linear map ($L:V\to V:v\mapsto {L^i}_j v^j e_i$)
1. transformation:
$$\begin{aligned}
    L&={L^i}_j (e_i \otimes \epsilon^j) \\
    &= {L^i}_j ({B^a}_i\tilde e_a)\otimes({F^j}_b\tilde \epsilon^b)\\
    &= {B^a}_i{L^i}_j {F^j}_b (\tilde e_a\otimes\tilde \epsilon^b)\\
    &= {\tilde L^a}_b(\tilde e_a\otimes\tilde \epsilon^b)\\
    &\implies {\tilde L^a}_b = {B^a}_i{L^i}_j {F^j}_b
\end{aligned}$$
2. action on other tensors:
$$\begin{aligned}
    w=L(v)&= {L^i}_j (e_i \otimes \epsilon^j) (v^k e_k)\\
    &= {L^i}_j v^k (e_i \otimes \underbrace{\epsilon^j  e_k}_{=\delta^j_k})\\
    &= \underbrace{{L^i}_j v^j}_{\text{coeff.}} \underbrace{e_i}_{\text{basis}}\\
	&\equiv w^i e_i
\end{aligned}$$
The coefficients obey the known matrix-vector multiplication rule - and in this sense, define this rule!
The basis of $L$, i.e. $e_i \otimes \epsilon^j$, is indeed a linear map, as $\epsilon^j$ "eats" a vector by definition, and the result is a number; the rest is just $e_i$ - a vector, which is the output of a linear map.

3. array shape: given by kronecker product of $e_i \otimes \epsilon^j$, which yields a row of columns (matrices). Example:
$$\begin{aligned}
    e_1 \otimes \epsilon^1 &=\begin{pmatrix}1\\0\end{pmatrix}\otimes \begin{pmatrix}1&0\end{pmatrix}=\begin{pmatrix} 1\begin{pmatrix}1\\0\end{pmatrix}&0 \begin{pmatrix}1\\0\end{pmatrix}\end{pmatrix}&&= \begin{pmatrix}1&0\\0&0\end{pmatrix} \\
    e_1 \otimes \epsilon^2   &=\begin{pmatrix}1\\0\end{pmatrix}\otimes \begin{pmatrix}0&1\end{pmatrix}=...&&= \begin{pmatrix}0&1\\0&0\end{pmatrix}\\
    &...
\end{aligned}$$
