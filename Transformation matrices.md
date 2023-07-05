"Darstellungsmatrix/Abbildungsmatrix"

is a matrix that represents a linear map/linear transformation between two vector spaces. Every linear transformation can be represented as a matrix, which is great as matrices are easy to analyze. E.g. one can find the kernel of a linear map by looking at its matrix representation and solving a linear system of equations.

We consider a linear map $L\in Hom(V,V)$ from a vector space $V$ to itself (=endomorphism, see [[Classification of maps in linear algebra]]). For such a map, the following commuting diagram holds:

![[commutingdiagram-transformationmatrix.png]]
Here $K_B$ is the coordinate map (see [[Coordinate vectors, coordinate maps]]) of the basis $B=\{b_1, ... b_n\}$. The map $L$ has an "equivalent" $L_B$, that maps the respective coordinate vectors of $v$ with respect to $B$. It can be found using $$L_B = K_B\circ L \circ K_B^{-1}$$ There is an easier way:


## Theorem.
Call the image of the basis vector $b_i$ under $L$  $$l_i:=L(b_i)$$The coordinate vector $l_i^B=K_B(l_i)$ is the i-th colum of the matrix $L_B$: $$L_B = (l_1^B, ... l_n^B).$$ That means, we only have to transform the basis (like in [[Change of basis in linear algebra]]).

Proof. See [1]


## Example
Assume
- $L:\mathbb{R}_{\leq 2}[x] \rightarrow \mathbb{R}_{\leq 1} [x]:p(x)\mapsto p'(x)$ be the first derivative map from polynomials of degree smaller or equal to 2
- $B=\left \{ 1,x,x^2 \right \}$
- $p(x) = ax^2+bx+c \implies p'(x) = 2ax+b$.

Lets apply the result of the theorem above to compute $L_B$:$$\left.\begin{align}
    l_1 &= L(1) =  0 &&\implies l_1^B = \begin{pmatrix}0\\0\\0\end{pmatrix} \\
    l_2 &= L(x) =  1 &&\implies l_2^B = \begin{pmatrix}1\\0\\0\end{pmatrix} \\
    l_3 &= L(x^2) =  2x &&\implies l_3^B = \begin{pmatrix}0\\2\\0\end{pmatrix}
\end{align}\quad\right\} \implies L_B\left(l_1^B, l_2^B, l_3^B\right) = \begin{pmatrix}0&1&0 \\0&0&2 \\0&0&0\end{pmatrix}$$As a test, we apply it to the polynomial:
$$p_B = \begin{pmatrix}c\\b\\a\end{pmatrix}, \quad p'_B = \begin{pmatrix}b\\2a\\0\end{pmatrix} \implies L_B\cdot p_B = \begin{pmatrix}0&1&0 \\0&0&2 \\0&0&0\end{pmatrix} \cdot \begin{pmatrix}c\\b\\a\end{pmatrix} = \begin{pmatrix}b\\2a\\0\end{pmatrix} \equiv p'_B $$

#todo second video [2]

## Source
1. https://www.youtube.com/watch?v=ixUCtiR6sxY&list=PLcQq8Z8G1vebIYGZOFmue7nmgpof4s0NG&index=7
2. https://www.youtube.com/watch?v=_ZYxpTqwujA&list=PLcQq8Z8G1vebIYGZOFmue7nmgpof4s0NG&index=8
