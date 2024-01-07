# Error norm: choosing the correct one

choose the norm associated to the function space in which the solution lives.

E.g. say, $u\in H^1$. Then it makes sense to measure functions in the $H^1$-norm. Its also meaningful, to measure functions in a space larger than $H^1$, e.g. $L^2 \supset H^1$.

It is not meaningful to measure functions in a smaller space, such as $H^2\subset H^1$, as functions in $H^1$ can have non-square integrable second derivatives, so the $H^2$-norm is not well-defined for $H^1$-functions.

The $L^2$-norm is especially well-known and often used, as it is sometimes easier to compute it, e.g. in FEM, often one can assemble the L^2-norm using $U^T M U$, where $U$ is the solution vector and $M$ the mass matrix, which is usually already available in the code. 



## Source:

https://scicomp.stackexchange.com/questions/2822/what-norm-to-choose-when

