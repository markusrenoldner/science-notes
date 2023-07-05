
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


The map $S:K\rightarrow K:v_B\rightarrow v_C$ describes a change of basis of the vector. It is called "change-of-basis matrix" or "transisition matrix".

It can be found by $$S=K_C\circ K_B^{-1}=K_C(K_B^{-1})$$ due to the following commuting diagram ![[commutingdiagram-changeofbasis.png]]

## Example
Let $x=\begin{pmatrix}3\\2\end{pmatrix}$, $B=\left\{\begin{pmatrix}1\\1\end{pmatrix},\begin{pmatrix}1\\2\end{pmatrix} \right\}$, $C=\left\{\begin{pmatrix}1\\3\end{pmatrix},\begin{pmatrix}1\\2\end{pmatrix} \right\}$

Now we express $x$ in both bases:

$$\begin{align}
    x&=1  \begin{pmatrix}1\\1\end{pmatrix} 
+ 1 \begin{pmatrix}2\\1\end{pmatrix}=
\begin{pmatrix}3\\2\end{pmatrix} 
&&\implies x_B = K_B(x) = \begin{pmatrix}1\\1\end{pmatrix}\\
x &= -4 \begin{pmatrix}1\\3\end{pmatrix}+7 \begin{pmatrix}1\\2\end{pmatrix} = \begin{pmatrix}3\\2\end{pmatrix} &&\implies x_C = K_C(x) = \begin{pmatrix}-4\\7\end{pmatrix}
\end{align}$$

Now we want to find the transisition matrix $S=K_C\circ K_B^{-1}$ that desribes the change of basis.

1. assume a coordinate vector $x_B:=\begin{pmatrix}x_1\\x_2\end{pmatrix} \implies K_B^{-1} \begin{pmatrix}x_1\\x_2\end{pmatrix}= x_1 \begin{pmatrix}1\\1\end{pmatrix}+x_2 \begin{pmatrix}2\\1\end{pmatrix} = \begin{pmatrix}x_1+2x_2 \\x_1+x_2\end{pmatrix}=\begin{pmatrix}1&2\\1&1\end{pmatrix}\cdot \begin{pmatrix}x_1\\x_2\end{pmatrix}$
2. assume a general vector $v:=\begin{pmatrix}v_1\\v_2\end{pmatrix}$; use Ansatz $v=\mu_1 \begin{pmatrix}1\\3\end{pmatrix} + \mu_2 \begin{pmatrix}1\\2\end{pmatrix} = \begin{pmatrix}v_1\\v_2\end{pmatrix} \implies \mu_1+\mu_2 = v_1, \quad 3\mu_1 + 2\mu_2 = v_2$ from which we get $v_c = K_C(v) = \begin{pmatrix}\mu_1 \\ \mu_2\end{pmatrix} = \begin{pmatrix}-2v_1 + v_2\\3v_1 - v_2\end{pmatrix} = \begin{pmatrix}-2&1 \\ 3 & -1\end{pmatrix}\cdot \begin{pmatrix}v_1 \\v_2\end{pmatrix}$
This means that $$ S=K_C \cdot K_B^{-1} = \begin{pmatrix}-2&1 \\ 3 & -1\end{pmatrix}\cdot \begin{pmatrix}1&2\\1&1\end{pmatrix} = \begin{pmatrix}-1&-3\\2&5\end{pmatrix}$$

Test: we expect that $S\cdot x_B = x_C$, which indeed holds:
$$S\cdot x_B = \begin{pmatrix}-1&-3\\2&5\end{pmatrix}\cdot \begin{pmatrix}1\\1\end{pmatrix} = \begin{pmatrix}-4 \\7\end{pmatrix} \equiv x_C$$

The inverse of the transistion matrix describes the transformation in the other direction $S^{-1} =: T$.


## Faster way to find $S$

Theorem.
Let $V$ be a finite dimensional vector space over $K$ and let $B=\left \{ b_1,...b_n \right \}$ and $C=\left \{ c_1, ... c_n \right \}$ be bases of $V$. Then, the coordinate vector of the basis vector $b_i$ with respect to the basis $C$ is the i-th column of the transistion matrix $S$ for the change of basis from the basis $B$ to $C$.

In words: if we take each basis vector of $B$, represent it in the basis $C$, and collect these vectors in a matrix, we have found $S$.

Proof.
We transform each basis vector of $B$ to $C$:
$$\left. \begin{align}
    b_1 &= S_{11} c_1 + S_{21} c_2 + \dots S_{n1} c_n \\
    b_2 &= S_{12} c_1 + S_{22} c_2 + \dots S_{n2} c_n \\
    &\vdots\\
    b_2 &= S_{1n} c_1 + S_{2n} c_2 + \dots S_{nn} c_n 
\end{align} \quad \right\} \implies K_C(b_i) = \begin{pmatrix}S_{1i}\\S_{2i} \\ \vdots \\S_{ni}\end{pmatrix} \quad \forall i$$
The $S_{ij}$ are just the coordinates of each $b_i$ in the basis $C$. $K_C(b_i)$ will be the i-th colum of the transisition matrix, therefore the strange double-indices.

Let $v\in V$. In $B$ and $C$ we get:
$$\begin{align}
    v &= \mu_1 c_1 + \dots \mu_n c_n \implies v_C = K_C(v) = \begin{pmatrix}\mu_1 \\ \vdots \\ \mu_n\end{pmatrix} \\
    v &= \lambda_1 b_1 + \dots \lambda_n b_n \implies v_B = K_B(v) = \begin{pmatrix}\lambda_1 \\ \vdots \\ \lambda_n\end{pmatrix}
\end{align}$$

Now we insert the expression for $b_1$ in the formula for $v$:
$$\begin{align}
    v &= \lambda_1 b_1 + \lambda_2 b_2+\dots \lambda_n b_n \\
    &= \lambda_1 S_{11} c_1 + \lambda_1 S_{21} c_2 + \dots \lambda_1 S_{n1} c_n \\
    &+ \lambda_2 S_{12} c_1 + \lambda_2 S_{22} c_2 + \dots \lambda_2 S_{n2} c_n \\
    &\vdots \\
    &+\lambda_n S_{1n} c_1 + \lambda_n S_{2n} c_2 + \dots \lambda_n S_{nn} c_n \\
\end{align}$$

We factor out $c_i$, compare coefficients and find expressions for $\mu_i$:
$$\begin{align}
    v &= \underbrace{\left ( \lambda_1 S_{11} + \lambda_2 S_{12} + \dots \lambda_n S_{1n} \right )}_{\mu_1} \cdot c_1 \\
    &+ \underbrace{\left ( \lambda_1 S_{21} + \lambda_2 S_{22} + \dots \lambda_n S_{2n} \right )}_{\mu_2}\cdot c_2 \\
    &\vdots \\
    &+ \underbrace{\left ( \lambda_1 S_{n1} + \lambda_2 S_{n2} + \dots \lambda_n S_{nn} \right )}_{\mu_n} \cdot c_n 
\end{align}$$

The $\mu_i$ depend on the $\lambda_i$:
$$\begin{pmatrix}\mu_1 \\ \mu_2 \\\vdots \\ \mu_n\end{pmatrix} = \begin{pmatrix}
S_{11} & S_{12} & \dots & S_{1n} \\
S_{21} & S_{22} & \dots & S_{2n} \\
\vdots \\
S_{n1} & S_{n2} & \dots & S_{nn} 
\end{pmatrix} \cdot \begin{pmatrix}\lambda_1 \\\lambda_2 \\ \vdots \\ \lambda_n\end{pmatrix}$$

We have shown that $$v_c = S\cdot v_B$$

## Example
Let $p\in \mathbb{R}_{\leq 2}[x]$ be a real polynomial of order smaller or equal to 2, with $p(x) = ax^2 + bx + c$ with $a,b,c\in \mathbb{R}$ and $B=\left \{ 1+x,1-x,2x+x^2 \right \}, C= \left \{ 3x,x^2-1,1 \right \}$.
Represent $p$ in the bases $B$ and $C$ using the transistion matrix $S$.

We start with $B$.
$$ax^2 +bx+c = \lambda_1 (1+x) + \lambda_2 (1-x) + \lambda_3 (2x + x^2) $$
We compare coefficients and solve the system and get $$v_B = K_B(p) = \begin{pmatrix}\lambda_1\\ \lambda_2 \\ \lambda_3\end{pmatrix} = \begin{pmatrix} \frac{b+c-2a}{2}\\ \frac{c-b+2a}{2}\\ a\end{pmatrix} \in \mathbb{R}^3$$

Now we transform each $b_i\in B$ to $C$ to get $S$. After writing down all equations, comparing coefficients and solving the system we get $$\begin{align}
    K_C(1+x)&= \begin{pmatrix}1/3 \\0 \\1 \end{pmatrix} \\
    K_C(1-x) &= \begin{pmatrix}-1/3 \\ 0\\1 \end{pmatrix}  \\
    K_C(2x+x^2) &= \begin{pmatrix}2/3\\1\\1\end{pmatrix}
\end{align}$$ 

The matrix $S$ is therefore:
$$S = \begin{pmatrix}1/3 & -1/3 & 2/3 \\ 0&0&1 \\1&1&1\end{pmatrix}$$
Therefore $$ v_B = S\cdot v_B = \begin{pmatrix}1/3 & -1/3 & 2/3 \\ 0&0&1 \\1&1&1\end{pmatrix} \cdot \begin{pmatrix} \frac{b+c-2a}{2}\\ \frac{c-b+2a}{2}\\ a\end{pmatrix} = \begin{pmatrix}b/3 \\a\\c+a\end{pmatrix}$$

Which means that in $C$ we have $$p(x) = \frac{b}{3} \cdot 3x + a \cdot(x^2-1) + (c+1) \cdot 1 = ax^2+ bx + c$$




## Source
- https://www.youtube.com/watch?v=Qs3I594evk4&list=PLcQq8Z8G1vebIYGZOFmue7nmgpof4s0NG&index=6