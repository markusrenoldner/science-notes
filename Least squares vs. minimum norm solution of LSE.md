[[Numerics]]


## Goal
solve matrix equation $Ax=b$ 
$A\in \mathbb{R}^{n\times m}$, $x\in \mathbb{R}^m$, and $b\in \mathbb{R}^n$


## 2 options:
1. if $n<m$: the system is "underdetermined", there are more unknowns $m$ than equations $n$, then there are infinitely many solutions and one can find a minimum norm solution, i.e. finding $x$ such that $||x||_2$ is minimized. This can be done using the Moore-Penrose Pseudoinverse, or the SVD. A MINRES solver can also find a unique solution.
2. if n>m: the system is overdetermined, there are more equations $n$ than unknowns $m$, then there is no exact solution that satsfies $Ax=b$. But one can find the minimum-residual solution as an approximation - it minimizes the residual $Ax-b$ . This can be done using the Least Squares method


## Sources
- Prof. Melenk - Numerical Computations
- https://math.stackexchange.com/questions/2253443/difference-between-least-squares-and-minimum-norm-solution