
technique from [[Linear algebra]]


## Definition
A squared matrix is diagonalizable if e.g. the geometric and algebraic multiplicity of all eigenvalues is equal (see [[Eigenvalue multiplicity]]):
$$A=TDT^{-1}$$
where $T$ is a matrix consisting of eigenvectors.
If this is not the case, a Jordan normalform $J$ can be found:
$$A=QJQ^{-1}$$
where $Q$ is a matrix consisting of generalized eigenvectors.

The Jordan normalform is not unique, but always has the following structure:
$$J=\begin{pmatrix} \lambda_1&a&0&0&0\\0&\lambda_2&b&0&0\\0&0&\lambda_3&c&0\\0&0&0&\lambda_4&d\\0&0&0&0&\lambda_5\\\end{pmatrix}$$
$\lambda_i$ is an eigenvalue and $a,b,c,d$ are either 1 or 0, depending on the geometric multiplicity of the eigenvalues.


## Interpretation of the matrix strucure:

The geometric multiplicity defines how many "Jordan blocks" the matrix has. A Jordan block is the largest square submatrix centered around several instances of the same eigenvalue, and whose upper triangle entries are all 1.

That means, if all $\lambda$ disctinct $\implies$ $A$ diagonalizable and $J=D$.

In the following example $\lambda_1$ has geometric multiplicity 1 and $\lambda_2$ has 2 (and therefore 2 Jordan blocks)
$$
J=\left[ 
\begin{array}{c@{}c@{}c}
 \left[\begin{array}{cc}
         \lambda_1 & 1 \\
         & \lambda_1 \\
  \end{array}\right] &  & \\
   & \left[\begin{array}{c}
                       \lambda_2 
                      \end{array}\right] & \\
 &  & \left[ \begin{array}{cc}
                                   \lambda_2 & 1 \\
                                    & \lambda_2 \\
                                  \end{array}\right] \\
\end{array}\right]
$$
The ones are set, such that the number of blocks is equivalent to the geometric multiplicity.





## Sources:
- https://www.youtube.com/watch?v=TnQ5yCSdSsc&list=PLBh2i93oe2qvrzR114cOR9i-aJb6_GVuw&index=3&ab_channel=TheBrightSideofMathematics
- https://de.wikipedia.org/wiki/Jordansche_Normalform
- Prof. Auzinger - Lineare Algebra für TPH, TU Wien lecture 2020, [[Auzinger-ana2TPH.pdf]]


