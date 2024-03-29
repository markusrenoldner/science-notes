# Saddle point problem
"Sattelpunktproblem"

#unlinked 


## Definition:
Let
$$
M=\left(\begin{array}{cc}
A & B \\
B^T & 0
\end{array}\right)
$$
be a matrix, where $A$ and $B$ are smaller matrices. Then a saddle point problem is an equation of the form
$$Mx=0$$
with $x=(u,p)^T$. The respective quadratic form $F$ of $M$ is
$$x^T\cdot M \cdot x = u^TAu+u^TBp+p^TB^Tu =: F(u,p)$$
Now if $\tilde x=(\tilde u,\tilde p)^T$ is a solution of $Mx=0$, then it is also a saddle point of $F$.
A form is a polynomial whose nonzero terms all have the same degree, e.g. $x^2+xy+y^2$.


## Idea of proof:
1. notice that $F(\tilde u, \tilde p) = 0$
2. by using $Mx=0$ and A being pos. def. one can show for any $u$ that
$$F(u,\tilde p) \geq 0$$
3. similar one shows for any $p$ that   $$F(\tilde u, p) \leq 0$$This implies that $(\tilde u, \tilde p)$ is a saddle point.



## Introduction to Saddle Point Problems from Michele Benzi 
(from the Lectures of the Thirty-seventh Woudschoten Conference)
https://wsc.project.cwi.nl/woudschoten-conferences/2012-woudschoten-conference/Benzi1.pdf


## Source:
- https://de.wikipedia.org/wiki/Sattelpunktproblem
- https://en.wikipedia.org/wiki/Quadratic_form