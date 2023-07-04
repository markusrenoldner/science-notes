
[[Numerical analysis]]
#paper

The paper explains why Krylov methods make sense and why it is natural to represent a solution to a linear system as a member of a Krylov space. The paper shows that the solution to a nonsingular linear system Ax = b lies in a Krylov space whose dimension is the degree of the minimal polynomial of A. Therefore, if the minimal polynomial of A has low degree then the space in which a Krylov method searches for the solution can be small.

The minimal polynomial of a matrix A is the unique monic polynomial $q$ (i.e. a polynomial with 1 as the leading coefficient) of minimal degree such that 
$$q(A) = 0$$
In other words, it is the polynomial of smallest degree that has A as a root. The degree of the minimal polynomial of A plays a role in determining the dimension of the Krylov space in which a solution to a linear system Ax = b can be found.

When the matrix is singular, however, Krylov methods can fail. Even if the linear system does have a solution, it may not lie in a Krylov space. In this case, the paper describes a class of right-hand sides for which a solution lies in a Krylov space.

## Source
paper by Ipsen and Meyer
https://www.researchgate.net/publication/2761540_The_Idea_Behind_Krylov_Methods