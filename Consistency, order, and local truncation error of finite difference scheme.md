This article refers to [[Finite Difference Method (FDM)]] and [[Finite Volume Method (FVM)]].
For consistency for FEM, refer to [[Consistency finite differences vs finite elements]].



## Notation
#todo 
The approximation of the exact cell average $u_j^n$ is 

We want to check convergence:
$$Q_j^n\rightarrow u_j^n \quad\text{ for } \quad\Delta x, \Delta t \rightarrow 0$$



## Finite volume example
The approximation of the exact cell average $u_j^n$ is 
$$Q_j^n\approx u_j^n:=\frac{1}{\Delta x}\int_{C_i} u(t_n, x) dx$$
where $C_j:=  [x_{j-1/2}, x_{j+1/2}]$.
#todo add my summary of tornberg NDE lec4 with the adv. equ example!




## Finite diff example
#todo schlatter: study question 22 order of scheme
#todo add this as further reading https://math.stackexchange.com/questions/1921554/local-vs-global-truncation-error


## Source:
- Prof. Tornberg - Numerical solutions of differential equations, KTH lecture notes 2022, lecture 4





