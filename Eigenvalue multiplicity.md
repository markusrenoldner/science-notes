[[Linear algebra]]




Consider a square matrix $A$.
Any (nontrivial) eigenpair $(\lambda_i,v_i)$ per definition satisfies
$$(A-\lambda_i\mathbb{I})v_i=0 \quad \iff \quad \operatorname{det}(A-\lambda_i\mathbb{I})=0$$

Firstly, the right expression is called characteristic polynomial:
$$P_A(\lambda_i):=\operatorname{det}(A-\lambda \mathbb{I})$$
and the eigenvalues are its roots.

Secondly, the left expression from above yields:
$$v_i\in \operatorname{ker}(A-\lambda_i\mathbb{I})=:\mathcal{E}_A(\lambda_i)$$
this space is called eigenspace of $\lambda_i$. It is the span of the eigenvalues corresponding to $λ_i$.

## Algebraic multiplicity
The multiplicity of a root $\lambda_i$ of $P_A$ is called algebraic multiplicity of that eigenvalue.


## Geometric multiplicity
...is the dimension of $\mathcal{E}_A(\lambda_i)$



-------------------------
## Example
$$A=\pmatrix{
2&1&0\\
0&2&0\\
0&0&1}$$
$\implies P_A = (1-\lambda)(2-\lambda)^2$  and:
- $\lambda_1=1$ with algebraic multiplicity 1 
- $\lambda_2=2$ with algebraic multiplicity 2

Lets consider $\lambda_2=2$:
$$M:=A-\lambda_2\mathbb{I}=
\pmatrix{
0&1&0\\
0&0&0\\
0&0&-1
}
$$
and further: $\mathcal{E}_A(\lambda_2)=\operatorname{ker}M$
The dimension of $M$ is 2. Due to the rank-nullity theorem (Rangsatz/Dimensionssatz):
$$\begin{align}
\operatorname{dim}n&=\operatorname{dim}\operatorname{ker}(M)&&+\operatorname{dim}\operatorname{im}(M)\\
3&=1&&+2
\end{align}$$
where $n$ is the dimension of the domain which $A$ is mapping from ($\operatorname{dim}\operatorname{im}(\cdot)$ is also called $\operatorname{rank}(\cdot)$).

The geometric multiplicity of $\lambda_2$ is 1 as this is the eigenspace dimension.

## Implications:
1. It holds:
$$1 \leq g.m.(\lambda)\leq a.m.(\lambda)$$
2. A matrix is diagonalizable iff. the geom. multiplicity of every eigenvalue is equal to its algebraic multiplicity (this is the case if all $\lambda$ are distinct). 
   Or equivalent: the sum of the geom. multiplicities of all eigenvalues is $n$ (the dimension of the domain).

source:
https://www.youtube.com/watch?v=Xcln3xG8QGQ&ab_channel=mathapptician

https://math.stackexchange.com/questions/1859839/how-can-i-find-the-dimension-of-the-eigenspace?rq=1

