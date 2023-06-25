This article talks about properties of the [[Finite Difference Method (FDM)]] and the [[Finite Volume Method (FVM)]].
For a similar property comparable to "consistency" in this article for FEM, refer to [[Consistency finite differences vs finite elements]].


## Notation
The approximation of the exact value $u_j^n$ is $Q_j^n$. Here, $n$ denotes the time $t_n:=n\Delta t$ and $j$ denotes the spatial position $x_j:=j\Delta x$.
The vector of unknowns is  $\boldsymbol{Q^n}:=(... Q_{j-1}^n, Q_j^n, Q_{j+1}^n,...)$ and the numerical scheme $\Phi$ is defined by $\boldsymbol{Q^{n+1}} = \Phi(\boldsymbol{Q^n},\Delta t, \Delta x)$, where each value is updated using a generic scheme
$$Q^{n+1}_j= \sum_l b_{j,l}(\Delta t, \Delta x) Q_{j+l}^n$$
with some coefficients $b$ that depend on the scheme. Every linear scheme can be written in this form.

The local truncation error $\tau_n$ at time step $n$ is the residual that appears when plugging in the exact solution $\boldsymbol{u}^n:=(...u_j^n, u_{j+1}^n, ...)$ into the scheme $\Phi$
$$\tau^n:=\frac{\boldsymbol{u}^{n+1}-\Phi(\boldsymbol{u}^n)}{\Delta t} $$
(we scale by $\Delta t$ as explained later). The scheme is consistent if $\tau_n$ converges to $0$ for $\Delta t, \Delta x \rightarrow 0$.


## Example (FVM?)
#todo FVM?
We consider the advection equation:
$$\partial_t u + a \partial_x u = 0$$
with the upwind scheme. The scheme evaluated with the exact solution values yields a residual:
$$u_{j}^{n+1}=u_{j}^{n}-a\frac{\Delta t}{\Delta x}(u_{j}^{n}-u_{j-1}^{n})+\Delta t \tau_n^j$$
We rewrite the scheme in the formulation introduced above:
$$u_{j}^{n+1}=\Phi(u_{j}^{n}) +\Delta t \tau_n^j = u_{j}^{n} \left(1-a\frac{\Delta t}{\Delta x}\right)+u_{j-1}^{n}\left(a\frac{\Delta t}{\Delta x}\right)+\Delta t \tau_n^j$$
the terms in parenthesis are the coefficients $b_j$. This formula gives
$$\tau_j^n=\frac{u_{j}^{n+1}-u_{j}^{n}}{\Delta t}+a\frac{u_{j}^{n}-u_{j-1}^{n}}{\Delta x}$$
(We get exactly the upwind scheme with a residual term instead of $0$. This explains the $\Delta t$ scaling.)
Now we use the definition of the exact cell average from FVM: $u_j^n:=\frac{1}{\Delta x}\int_{C_j} u(t^n,x)dx$ :
$$\tau_j^n=\frac{1}{\Delta x} \int_{C_j}\frac{u(t_{n+1},x)-u(t_n,x)}{\Delta t}+a\frac{u(t_n,x)-u(t_n,x-\Delta x)}{\Delta x}dx$$
- We Taylor-expand the values $u(t_{n+1},x)$ and $u(t_n,x-\Delta x)$ 
- we also use the fact that the PDE $\partial_t u+a\partial_x u=0$ is fulfilled
- And we use, that $\frac{1}{\Delta x}\int_C \mathcal{O}(\Delta x^2)=\mathcal{O}(\Delta x^2)$.
We get:
$$\tau_j^n=\frac{1}{\Delta x} \int_{C_j}\left(\frac{\Delta t}{2}\partial_{tt}u(t_n,x) - \frac{\Delta x}{2}a\partial_{xx}ut_n,x)\right)dx + \mathcal{O}(\Delta t^2 + \Delta x^2)$$
We find some bounds on the derivative terms:
$$\begin{align}
\frac{1}{\Delta x} \int_{C_j} \partial_{tt}u(t_n,x) dx &\leq \frac{1}{\Delta x} \int_{C_j}  \operatorname{max}_{y}\vert \partial_{tt}u(t_n,y)\vert dx &&= \operatorname{max}_{y}\vert \partial_{xx}u(t_n,y)\vert \frac{\Delta x}{\Delta x} = \mathcal{O}(1)\\
\frac{1}{\Delta x} \int_{C_j} \partial_{tt}u(t_n,x) dx &\leq\quad... &&= \operatorname{max}_{y}\vert \partial_{tt}u(t_n,y)\vert = \mathcal{O}(1)
\end{align}$$
with $y\in C_j$. This means that
$$\tau_j^n=\frac{\Delta t}{2}\mathcal{O}(1) + \frac{\Delta t}{2}\mathcal{O}(1) = \mathcal{O}(\Delta t + \Delta x),$$
or in words: the method is of order 1 in time and space.



#todo is this even a FVM example?
#todo schlatter: study question 22 order of scheme
#todo add this as further reading https://math.stackexchange.com/questions/1921554/local-vs-global-truncation-error
#todo add numpde exapmle
#todo check if this "scaled by delta t" also holds for finit diff
#todo upwind scheme for advection equation using finite diff method



## FVM
In FVM, the approximation of the exact cell average $u_j^n$ is 
$$Q_j^n\approx u_j^n:=\frac{1}{\Delta x}\int_{C_i} u(t_n, x) dx$$
where $C_j:=  [x_{j-1/2}, x_{j+1/2}]$. 
#todo do we need this?



## Source:
- Prof. Tornberg - Numerical solutions of differential equations, KTH lecture notes 2022, lecture 4





