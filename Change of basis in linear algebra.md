as described in [[Coordinate vectors, coordinate maps]], one can represent vectors in bases. The coordinates change, if one changes the basis, a vector is represented in.
[[Linear algebra]]

## Main idea
Let $V$ be an $n$-dimensional vector space over $K$ (usually $K=\mathbb{R}$ or $K=\mathbb{C}$), $v\in V$,  and $B=\{\boldsymbol{b}_1, ... \boldsymbol{b}_n\}, C=\{\boldsymbol{c}_1, ... \boldsymbol{c}_n\}$.
Lets find the coordinate vectors for $B,C$. First we find the coordinates:
$$v=\sum_i \lambda_i b_i ,\quad v=\sum_i \mu_i c_i$$
Then we collect the coordinates to get the coordinate vectors:
$$v_B=K_B(v)=\begin{pmatrix}\lambda_1\\\lambda_2 \\ \vdots \\ \lambda_n\end{pmatrix} , \quad v_C=K_c(v) =\begin{pmatrix}\mu_1\\\mu_2 \\ \vdots \\ \mu_n\end{pmatrix}$$
The map
$$\begin{aligned}
    S:K&\rightarrow K\\
    v_B&\mapsto v_C
\end{aligned}$$
describes a change of basis of the coordinate vector. It is called "change-of-basis matrix" or "transisition matrix". It can be found by $$S=K_C\circ K_B^{-1}=K_C(K_B^{-1})$$ due to the following commuting diagram ![[commutingdiagram-changeofbasis.png]]

One could now try to find $S$ by the given identity above, for which one would have to compute 
- $K_B^{-1}$ (by finding the canonical coordinates of a general coordinate vector $x_B=(x_1^B,... x_n^B)$)
- $K_C$ (by finding the $C$-coordinates of a general vector $v=(v_1,... v_n)$)
this is done in [1] as an example


## Theorem on how to find $S$
Let $V$ be a finite dimensional vector space over $K$ and let $B=\left \{ b_1,...b_n \right \}$ and $C=\left \{ c_1, ... c_n \right \}$ be bases of $V$. Then, the coordinate vector of the basis vector $b_i$ with respect to the basis $C$ is the i-th column of the transistion matrix $S$ for the change of basis from the basis $B$ to $C$.

In words: if we take each basis vector of $B$, represent it in the basis $C$, and collect these vectors in a matrix, we have found $S$.

In eigenchris' youtube playlist on tensor algebra, $S$ is the backwards matrix $B$!!!

Proof.
We transform each basis vector of $B$ to $C$:
$$\left. \begin{aligned}
    b_1 &= S_{11} c_1 + S_{21} c_2 + \dots S_{n1} c_n \\
    b_2 &= S_{12} c_1 + S_{22} c_2 + \dots S_{n2} c_n \\
    &\vdots\\
    b_2 &= S_{1n} c_1 + S_{2n} c_2 + \dots S_{nn} c_n 
\end{aligned} \quad \right\} \implies K_C(b_i) = \begin{pmatrix}S_{1i}\\S_{2i} \\ \vdots \\S_{ni}\end{pmatrix} \quad \forall i$$
The unknown coordinates $S_{ij}$ have to be found now. 
$K_C(b_i)$ will be the i-th colum of $S$, therefore the strange double-indices.

Let $v\in V$ be a general vector. In $B$ and $C$ we get:
$$\begin{aligned}
    v &= \mu_1 c_1 + \dots \mu_n c_n \implies v_C = K_C(v) = \begin{pmatrix}\mu_1 \\ \vdots \\ \mu_n\end{pmatrix} \\
    v &= \lambda_1 b_1 + \dots \lambda_n b_n \implies v_B = K_B(v) = \begin{pmatrix}\lambda_1 \\ \vdots \\ \lambda_n\end{pmatrix}
\end{aligned}$$
Now we insert the expression for $b_1$ in the formula for $v$:
$$\begin{aligned}
    v = \lambda_1 b_1 + \lambda_2 b_2+\dots \lambda_n b_n 
    &= \lambda_1 S_{11} c_1 + \lambda_1 S_{21} c_2 + \dots \lambda_1 S_{n1} c_n \\
    &+ \lambda_2 S_{12} c_1 + \lambda_2 S_{22} c_2 + \dots \lambda_2 S_{n2} c_n \\
    &\vdots \\
    &+\lambda_n S_{1n} c_1 + \lambda_n S_{2n} c_2 + \dots \lambda_n S_{nn} c_n \\
\end{aligned}$$

We factor out the $c_i$, compare coefficients and find expressions for $\mu_i$:
$$\begin{aligned}
    v &= \underbrace{\left ( \lambda_1 S_{11} + \lambda_2 S_{12} + \dots \lambda_n S_{1n} \right )}_{\mu_1} \cdot c_1 \\
    &+ \underbrace{\left ( \lambda_1 S_{21} + \lambda_2 S_{22} + \dots \lambda_n S_{2n} \right )}_{\mu_2}\cdot c_2 \\
    & \vdots \\
    &+ \underbrace{\left ( \lambda_1 S_{n1} + \lambda_2 S_{n2} + \dots \lambda_n S_{nn} \right )}_{\mu_n} \cdot c_n 
\end{aligned}$$
The $\mu_i$ depend on the $\lambda_i$ in the follwing way
$$\begin{pmatrix}\mu_1 \\ \mu_2 \\\vdots \\ \mu_n\end{pmatrix} = \begin{pmatrix}
S_{11} & S_{12} & \dots & S_{1n} \\
S_{21} & S_{22} & \dots & S_{2n} \\
\vdots \\
S_{n1} & S_{n2} & \dots & S_{nn} 
\end{pmatrix} \cdot \begin{pmatrix}\lambda_1 \\\lambda_2 \\ \vdots \\ \lambda_n\end{pmatrix}$$
Which is just $$v_c = S\cdot v_B$$

## Example: change of basis using $S$
Let 
- $p\in \mathbb{R}_{\leq 2}[x]$ be a real polynomial of order smaller or equal to 2, where $p(x) = ax^2 + bx + c$ with $a,b,c\in \mathbb{R}$ in canonical representation 
- $B=\left \{ 1+x,1-x,2x+x^2 \right \}, C= \left \{ 3x,x^2-1,1 \right \}$.

Represent $p$ in $B$ and $C$ using the transistion matrix $S$. We start with $B$.
$$ax^2 +bx+c = \lambda_1 (1+x) + \lambda_2 (1-x) + \lambda_3 (2x + x^2) $$
We compare coefficients, solve the system and get $$v_B = K_B(p) = \begin{pmatrix}\lambda_1\\ \lambda_2 \\ \lambda_3\end{pmatrix} = \begin{pmatrix} \frac{b+c-2a}{2}\\ \frac{c-b+2a}{2}\\ a\end{pmatrix}$$Now we apply the theorem above, i.e. transform each $b_i\in B$ to $C$ to get $S$. After writing down all equations, comparing coefficients and solving the system we get $$\left.\begin{aligned}
    K_C(1+x)&= \begin{pmatrix}1/3 \\0 \\1 \end{pmatrix} \\
    K_C(1-x) &= \begin{pmatrix}-1/3 \\ 0\\1 \end{pmatrix}  \\
    K_C(2x+x^2) &= \begin{pmatrix}2/3\\1\\1\end{pmatrix}
\end{aligned}\quad\right\} \implies S = \begin{pmatrix}1/3 & -1/3 & 2/3 \\ 0&0&1 \\1&1&1\end{pmatrix}$$ Therefore $$ v_C = S\cdot v_B = \begin{pmatrix}1/3 & -1/3 & 2/3 \\ 0&0&1 \\1&1&1\end{pmatrix} \cdot \begin{pmatrix} \frac{b+c-2a}{2}\\ \frac{c-b+2a}{2}\\ a\end{pmatrix} = \begin{pmatrix}b/3 \\a\\c+a\end{pmatrix}$$
We can check, this is true as $p(x)$ in $C$ is just $$p(x) =\sum_{i=1}^3 \mu_i c_i= \left(\frac{b}{3}\right) \cdot (3x) + (a) \cdot(x^2-1) + (c+1) \cdot (1) = ax^2+ bx + c$$

## Source
1. https://www.youtube.com/watch?v=Qs3I594evk4&list=PLcQq8Z8G1vebIYGZOFmue7nmgpof4s0NG&index=6

