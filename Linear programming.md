... is a type of linear, convex, constrained optimization problem
#unlinked 

We consider the example of a mars rover transporting a number of scientific instruments under a mass constraint.


## Given problem

science instruments: A,B,C (these three variables are either 0 or 1, depending on whether we chose the instrument or not)
with different masses $m_A, m_B, m_C$ 
and scientific values $s_A, s_B, s_C$
the rover can only carry a mass of $M$ 
also, each instrument will of course only be chose once (we dont take the same instrument twice, that would be redundant) 


## Reformulate problem

given: $s_A, s_B, s_C$, $m_A, m_B, m_C$, and $M$
maximize (the so called "objective function"): $S(A,B,C)=A s_a + B s_b + C s_c$
under the inequality constraints: $A m_a + B m_b + C m_c \leq M$, $A-1\leq 0$, $B\leq 1$ , and $C\leq 1$
It is implicitly assumed, that $A,B,C$ are nonnegative.


## Formulate linear program

$$X=\begin{pmatrix}
A \\ B \\ C
\end{pmatrix},\quad c=\begin{pmatrix}
s_A \\ s_B \\ s_C
\end{pmatrix},\quad A_{ineq}=\begin{pmatrix}
m_A&m_B&m_C\\
1&0&0\\
0&1&0\\
0&0&1\\
\end{pmatrix},\quad B_{ineq}=\begin{pmatrix}
M \\ 1 \\ 1 \\ 1
\end{pmatrix}$$

which translates to
maximize: $S(A,B,C)=c\cdot X$
under the constraint $A_{ineq}X\leq B_{ineq}$


## Python code using scipy

``` 
from scipy.optimize import linprog

# Linear programming
sA = 8
sB = 9
sC = 6
mA = 3
mB = 4
mC = 3
M  = 8

# define matrices and vectors
c = [-sA, -sB, -sC]
A = [[mA, mB, mC], 
     [1., 0., 0.], 
     [0., 1., 0.],
     [0., 0., 1.]]
b = [M, 
     1., 
     1., 
     1.]

# solve linear program
res = linprog(c, A_ub=A, b_ub=b)
print(res.fun)
print(res.x)
print(res.message)
```


## Source
https://towardsdatascience.com/solving-your-first-linear-program-in-python-9e3020a9ad32
