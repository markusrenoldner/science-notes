
#todo put this into latex [linearmaps-matrices.pdf](linearmaps-matrices.pdf)





Let $V$ be an $n$-dimensional vector space (finite dimensional) over $K$ (usually $K=\mathbb{R}$ or $K=\mathbb{C}$) with a basis $B=\{\boldsymbol{b}_1, ... \boldsymbol{b}_n\}$ then every $\boldsymbol{v} \in V$ can be expressed as a linear combination of "coordinates" $\lambda_i \in K$ and basis vectors $\boldsymbol{b}_i$ $$\begin{equation}\boldsymbol{v} = \sum_{i=1}^n \lambda_i \cdot \boldsymbol{v}_i \end{equation}$$
In general, a vector space has infinitely many bases $B$, and $\boldsymbol{v}$ looks different in each of them. Consider the example:


Let $\boldsymbol{x}=\begin{pmatrix}3\\2 \end{pmatrix} \in \mathbb{R}^2$, let $B_1 = \{\boldsymbol{e}_1, \boldsymbol{e}_2\}$ be the canonical basis and $B_2=\{\boldsymbol{b}_1, \boldsymbol{b}_2\}$ with $\boldsymbol{b}_1:=\begin{pmatrix}1\\-1\end{pmatrix}$ and $\boldsymbol{b}_2:=\begin{pmatrix}1\\1 \end{pmatrix}$  

Then $\boldsymbol{x}$ in the canonical basis is of course
$$\boldsymbol{x}=\begin{pmatrix}3\\2 \end{pmatrix}$$
and $\boldsymbol{x}$ in the basis $B_2$ is
$$\boldsymbol{x}=\lambda_1 b_1 + \lambda_2 b_2 = \lambda_1 \begin{pmatrix}1\\-1\end{pmatrix} + \lambda_2 \begin{pmatrix}1\\1\end{pmatrix} = \begin{pmatrix}\lambda_1 + \lambda_2\\-\lambda_1 + \lambda_2\end{pmatrix} = \begin{pmatrix}3\\2\end{pmatrix}$$
Now one can compute the coefficients/coordinates and obtain
$$\lambda_1 = \frac{5}{2} ,\quad \lambda_2 = \frac{1}{2} $$
## Definition: coordinate map
Now we define the coordinate map ("Koordinatenabbildung"):
Let $V$ be a finite dimensional vector space over $K$ and $B=\{b_1, b_2, ... b_n\}$. Then we call
$$\begin{align}
K_B:V&\rightarrow K^n\\
v=\sum_{i=1}^n v_i^B b_i &\mapsto v_B:=\begin{pmatrix}v_1^B\\v_2^B \\ \vdots \\ v_n^B\end{pmatrix}
\end{align}$$
the coordinate map of $V$ and $v_B$ the coordinate vector of $v$ with respect to the basis $B$. It is bijective, i.e. 
$$K_B^{-1}:K^n\rightarrow V$$
exists.


## Example: $2\times2$ matrices
Example: vector space of $2\times2$- matrices denoted as $M(2\times2,\mathbb{R})$. Consider the basis
$$B=\left\{ \begin{pmatrix}1&0\\0&0\end{pmatrix} , \begin{pmatrix}0&1\\1&0\end{pmatrix} , \begin{pmatrix}0&1\\-1&0\end{pmatrix} , \begin{pmatrix}0&0\\0&1\end{pmatrix} \right \}$$
Find $K_B:M(2\times2,\mathbb{R})\rightarrow \mathbb{R}^4$.
$$\begin{align}
A&:=\begin{pmatrix}a_{11}&a_{12}\\a_{21}&a_{22}\end{pmatrix} = v_1^B \begin{pmatrix}1&0\\0&0\end{pmatrix} + v_2^B\begin{pmatrix}0&1\\1&0\end{pmatrix} + v_3^B \begin{pmatrix}0&1\\-1&0\end{pmatrix} + v_4^B \begin{pmatrix}0&0\\0&1\end{pmatrix} \\
&= \begin{pmatrix}v_1^B&v_2^B+v_3^B\\v_2^B-v_3^B&v_4^B\end{pmatrix}
\end{align}$$
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
- https://www.youtube.com/watch?v=I1le67SZKjU&list=PLcQq8Z8G1vebIYGZOFmue7nmgpof4s0NG&index=6&ab_channel=AngewandteMathematikf%C3%BCrIngenieure