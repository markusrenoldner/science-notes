# Coordinate vectors, coordinate maps
Coordinate vectors allow to represent vectors (elements of vector spaces) as a list of numbers called coordinates with respect to a certain basis of said vector space.
Coordinate maps yield this coordinate representation for a given vector in the canonical basis.
[[Linear algebra]]

## Representing a vector in a basis
Let $V$ be an $n$-dimensional vector space (finite dimensional) over the field $K$ (usually $K=\mathbb{R}$ or $K=\mathbb{C}$) with a basis $B=\{\boldsymbol{b}_1, ... \boldsymbol{b}_n\}$ then every $\boldsymbol{v} \in V$ can be expressed as a linear combination of "coordinates" $\lambda_i \in K$ and basis vectors $\boldsymbol{b}_i$ $$\boldsymbol{v} = \sum_{i=1}^n \lambda_i \cdot \boldsymbol{v}_i $$In general, a vector space has infinitely many bases $B$, and the coordinates of $\boldsymbol{v}$ are different in each of them. 

Example:
Let $\boldsymbol{x}=\begin{pmatrix}3\\2 \end{pmatrix} \in \mathbb{R}^2$, let $B = \{\boldsymbol{e}_1, \boldsymbol{e}_2\}$ be the canonical basis and $C=\left\{\begin{pmatrix}1\\-1\end{pmatrix}, \begin{pmatrix}1\\1\end{pmatrix}\right\}$.

By construction, $\boldsymbol{x}$ is represented in the canonical basis $B$. Lets represent it in $C$:
$$\begin{aligned}
    \boldsymbol{x}& = \sum_i\lambda_i \boldsymbol{c}_i=\lambda_1 \begin{pmatrix}1\\-1\end{pmatrix} + \lambda_2 \begin{pmatrix}1\\1\end{pmatrix} = \begin{pmatrix}\lambda_1 + \lambda_2\\-\lambda_1 + \lambda_2\end{pmatrix} = \begin{pmatrix}3\\2\end{pmatrix}
\end{aligned}$$
Now one can compute the coefficients/coordinates and obtain
$$\lambda_1 = \frac{5}{2} ,\quad \lambda_2 = \frac{1}{2} \implies \boldsymbol{x}_C = \begin{pmatrix}5/2\\ 1/2\end{pmatrix}$$


## Definition: coordinate map and coordinate vector
Let $V$ be a finite dimensional vector space over $K$ and $B=\{b_1, b_2, ... b_n\}$. Then we call
$$\begin{aligned}
K_B:V&\rightarrow K^n\\
v=\sum_{i=1}^n v_i^B b_i &\mapsto\begin{pmatrix}v_1^B\\v_2^B \\ \vdots \\ v_n^B\end{pmatrix} =:v_B
\end{aligned}$$
the coordinate map of $V$ and its image $v_B$ the coordinate vector of $v$ with respect to the basis $B$. It is bijective, i.e. 
$$K_B^{-1}:K^n\rightarrow V$$
exists.


## Example: given basis, find $K_B$ and $x_B$
Example: vector space of $2\times2$- matrices denoted as $M(2\times2,\mathbb{R})$. Consider the basis
$$B=\left\{ \begin{pmatrix}1&0\\0&0\end{pmatrix} , \begin{pmatrix}0&1\\1&0\end{pmatrix} , \begin{pmatrix}0&1\\-1&0\end{pmatrix} , \begin{pmatrix}0&0\\0&1\end{pmatrix} \right \}$$
Find $K_B:M(2\times2,\mathbb{R})\rightarrow \mathbb{R}^4$.
$$\begin{aligned}
A&:=\begin{pmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{pmatrix} = v_1^B \begin{pmatrix}1&0\\0&0\end{pmatrix} + v_2^B\begin{pmatrix}0&1\\1&0\end{pmatrix} + v_3^B \begin{pmatrix}0&1\\-1&0\end{pmatrix} + v_4^B \begin{pmatrix}0&0\\0&1\end{pmatrix} \\
&= \begin{pmatrix}v_1^B&v_2^B+v_3^B\\v_2^B-v_3^B&v_4^B\end{pmatrix}
\end{aligned}$$
Solving this for the coefficients/coordinates gives:
$$v_1^B=a_{11},\quad v_2^B=\frac{a_{12}+a_{21}}{2},\quad v_3^B=\frac{a_{12}-a_{21}}{2},\quad v_4^B=a_{22}$$
and then
$$\displaystyle K_B(A)=K_B\begin{pmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{pmatrix} = \begin{pmatrix}a_{11}\\\frac{a_{12}+a_{21}}{2}\\\frac{a_{12}-a_{21}}{2}\\a_{44}\end{pmatrix}$$
Now we compute the inverse map. Consider a general coordinate vector 
$$x_B:=\begin{pmatrix}x_1^B \\ x_2^B \\ x_3^B \\ x_4^B \\\end{pmatrix}$$
It is the coordinate vector of the matrix
$$x_1^B \begin{pmatrix}1&0\\0&0\end{pmatrix} + x_2^B\begin{pmatrix}0&1\\1&0\end{pmatrix} + x_3^B \begin{pmatrix}0&1\\-1&0\end{pmatrix} + x_4^B \begin{pmatrix}0&0\\0&1\end{pmatrix} = \begin{pmatrix}x_1^B & x_2^B+x_3^B\\ x_2^B-x_3^B & x_4^B  \\\end{pmatrix}$$
which gives the inverse map of $K_B$:
$$K^{-1}_B:\mathbb{R}^4 \rightarrow M(2\times2,\mathbb{R}):\begin{pmatrix}x_1^B \\ x_2^B \\ x_3^B \\ x_4^B \\\end{pmatrix} \mapsto \begin{pmatrix}x_1^B & x_2^B+x_3^B\\ x_2^B-x_3^B & x_4^B  \\\end{pmatrix}$$
Clearly, as $K_B$ and $K_B^{-1}$ are inverses, one gets
$$(K_B^{-1}\circ K_B)A=A, \quad \text{and }\quad (K_B\circ K_B^{-1})x_B = x_B$$


## Source
- https://www.youtube.com/watch?v=I1le67SZKjU&list=PLcQq8Z8G1vebIYGZOFmue7nmgpof4s0NG&index=5
- Atland, Delft - Mathematics for Physicists
