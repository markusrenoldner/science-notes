
#todo 
1. every vector can be represented in every basis (see coordinate vectors)
2. commuting diagram: the change of basis matrix is a composition of coordinate maps + example
3. 2nd method to get this matrix: the coordinate vector of the basisvector i of the first basis with respect to the second basis is the i-th column of the transformation matrix + proof and examples



Let $V$ be an $n$-dimensional vector space over $K$ (usually $K=\mathbb{R}$ or $K=\mathbb{C}$) with two bases 
$$B=\{\boldsymbol{b}_1, ... \boldsymbol{b}_n\},\quad C=\{\boldsymbol{c}_1, ... \boldsymbol{c}_n\}$$
Let $v\in V$, then in the basis $B$ we can find the coordinate vector of $v$ with the coordinate map (see [[Coordinate vectors, coordinate maps]]). The vector can be represented in the basis $B$ using:
$$v=\sum_i \lambda_i b_i$$
and its coordinate vector is
$$v_B=K_B(v)=\begin{pmatrix}\lambda_1\\\lambda_2 \\ \vdots \\ \lambda_n\end{pmatrix}$$ and similar in basis $C$ the vector can be represented as $$v=\sum_i \mu_i c_i$$ and its coordinate vector is $$v_C=K_c(v) =\begin{pmatrix}\mu_1\\\mu_2 \\ \vdots \\ \mu_n\end{pmatrix}$$
The map $S:K\rightarrow K:v_B\rightarrow v_C$ describes a change of basis of the vector. It can be found by $$S=K_C\circ K_B^{-1}=K_C(K_B^{-1})$$ due to the following commuting diagram ![[commutingdiagram-changeofbasis.png]]

Example
Let $x=\begin{pmatrix}3\\2\end{pmatrix}$, $B=\left\{\begin{pmatrix}1\\1\end{pmatrix},\begin{pmatrix}1\\0\end{pmatrix} \right\}$, $C=\left\{\begin{pmatrix}1\\3\end{pmatrix},\begin{pmatrix}1\\2\end{pmatrix} \right\}$



## Source
- https://www.youtube.com/watch?v=Qs3I594evk4&list=PLcQq8Z8G1vebIYGZOFmue7nmgpof4s0NG&index=6