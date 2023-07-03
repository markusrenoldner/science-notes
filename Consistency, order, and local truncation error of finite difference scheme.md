This article discusses properties of the [[Finite Difference Method (FDM)]] and the [[Finite Volume Method (FVM)]].
For a "consistency" in the sense of FEM, refer to [[Consistency finite differences vs finite elements]].


## Notation
We discuss problems with unknown functions that depend on space and time $$u_j^n:=u(t_n,x_j) =(n\Delta t, j\Delta x).$$Exact unknowns are denoted by: $$\boldsymbol{u}^n:=(...u_j^n, u_{j+1}^n, ...)$$Approximation values of unknowns are denoted by:  $$\boldsymbol{Q^n}:=(... Q_{j-1}^n, Q_j^n, Q_{j+1}^n,...)$$The numerical scheme can be denoted as the "discretized differential equation" $\Psi$ that can be used to find $\boldsymbol{Q^{n+1}}$: $$\Psi({\boldsymbol{Q^{n+1}},\boldsymbol{Q^n},\boldsymbol{Q^{n-1}},...})=0.$$ or as an update rule $\Phi$, that finds $Q$ at the next time step depending on the previous ones: $$\boldsymbol{Q^{n+1}} = \Phi(\boldsymbol{Q^n},\boldsymbol{Q^{n-1}},...),$$The scheme (either as $\Phi$ or $\Psi$) depends on $\Delta t$ and $\Delta x$. It is called "linear", if it is linear in the unknowns $Q^n_j$.


## Example 
We consider the [[Advection equation]]:
$$\partial_t u + a \partial_x u = 0$$
using a "forward finite difference" in time and a "backward finite difference" in space, we get the "upwind scheme"/forward-time-backward-space (FTBS) scheme:
$$\begin{align}
\Psi(\boldsymbol{Q^n_j})&=\frac{Q^{n+1}-Q^n}{\Delta t} + \frac{Q_j -Q_{j-1}}{\Delta x} =0\\
Q^{n+1}=\Phi(\boldsymbol{Q^n_j})&=Q^{n}_{j}-a\frac{ \Delta t}{\Delta x}\left(Q^{n}_{j}-Q^{n}_{j-1}\right)
\end{align}$$


## Definition of local truncation error
The local truncation error $\tau^n$ at time step $n$ is the residual that appears when plugging in the exact solution into the scheme:$$\tau^n:=\Psi({\boldsymbol{u^{n+1}},\boldsymbol{u^n},\boldsymbol{u^{n-1}},...}).$$ Equivalently, we can use the formulation with the update rule $\Phi$ and get $$\tau^n:=\frac{\boldsymbol{u}^{n+1}-\Phi(\boldsymbol{u}^n)}{\Delta t^r} .$$ where $r$ is the order of the time derivative in the equation. The scaling with $\Delta t$ appears as we have formulated the scheme as an update rule that already discretizes the time derivative.


## Truncation error of advection equation and upwind scheme
The scheme from the example above evaluated with the exact solution values yields the local truncation error
$$\begin{align}
u_{j}^{n+1}&=u_{j}^{n}-a\frac{\Delta t}{\Delta x}(u_{j}^{n}-u_{j-1}^{n})+\Delta t \tau_j^n \\ 
\implies \tau_j^n&=\frac{u_{j}^{n+1}-u_{j}^{n}}{\Delta t}+a\frac{u_{j}^{n}-u_{j-1}^{n}}{\Delta x}
\end{align}$$
We get exactly the upwind scheme with a residual term instead of $0$. If we Taylor-expand the following terms:$$\begin{align}
u_j^{n+1} &= u_j^n + \Delta t \partial_t u_j^n + \frac{\Delta t^2}{2} \partial_{tt} u_j^n + \mathcal{O}(\Delta t ^3)\\ 
u_{j-1}^n &= u_j^n - \Delta x \partial_x u_j^n + \frac{\Delta x^2}{2} \partial_{xx} u_j^n + \mathcal{O}(\Delta x ^3)
\end{align}$$ we get
$$\begin{align}
\tau_j^n&=\frac{ u_j^n + \Delta t \partial_t u_j^n + \frac{\Delta t^2}{2} \partial_{tt} u_j^n -u_{j}^{n} }{\Delta t} + a\frac{u_{j}^{n} -u_j^n + \Delta x \partial_x u_j^n - \frac{\Delta x^2}{2} \partial_{xx} u_j^n  }{\Delta x} +\mathcal{O}(\Delta t^2+\Delta x^2)\\
&=\partial_t u_j^n + \frac{\Delta t}{2} \partial_{tt} u_j^n + a\partial_x u_j^n - a\frac{\Delta x}{2} \partial_{xx} u_j^n +\mathcal{O}(\Delta t^2+\Delta x^2)
\end{align}$$
and using the PDE $\partial_t u + a \partial_x u = 0$, we get
$$\tau_j^n= \frac{\Delta t}{2} \partial_{tt} u_j^n - a\frac{\Delta x}{2} \partial_{xx} u_j^n +\mathcal{O}(\Delta t^2+\Delta x^2) = \mathcal{O}(\Delta t+\Delta x)$$
The scheme applied to the advection equation is consistent and it is of first order in time and space.


## Truncation error of the scheme viewed as a FVM
We perform the exact same analysis as above, but interpret the upwind scheme as a [[Finite Volume Method (FVM)]]. We show that we get the same consistency order as before.
In FVM, $Q^n_j$ approximates the exact cell average of the unknown funciton $u(t,x)$ which is given as
$$Q_j^n\approx u_j^n:=\frac{1}{\Delta x}\int_{C_i} u(t_n, x) dx$$
where $C_j:=  [x_{j-1/2}, x_{j+1/2}]$ is a computational volume/cell. 
The upwind scheme is (exactly as above) given as
$$\begin{align}
u_{j}^{n+1}&=u_{j}^{n}-a\frac{\Delta t}{\Delta x}(u_{j}^{n}-u_{j-1}^{n})+\Delta t \tau^n_j \\ 
\implies \tau_j^n &=\frac{u_{j}^{n+1}-u_{j}^{n}}{\Delta t}+a\frac{u_{j}^{n}-u_{j-1}^{n}}{\Delta x}
\end{align}$$
which yields the expression for the truncation error.
Differently than before, we use the definition of the exact cell average from FVM: $$u_j^n:=\frac{1}{\Delta x}\int_{C_j} u(t^n,x)dx$$and plug this into the formula:
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
or in words: the method is consistent and of order 1 in time and space.
Summary: we can apply the exact same analysis onto a FVM and receive the same local truncation error.


## Source:
- Prof. Tornberg - Numerical solutions of differential equations, KTH lecture notes 2022, lecture 4
- Some explanations on different error definitions: https://math.stackexchange.com/questions/1921554/local-vs-global-truncation-error
- Prof. Schlatter - Computational Fluid Dynamics, KTH lecture notes 2022
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021
- Website summarizing truncation errors for a collection of finite difference schemes https://hplgit.github.io/INF5620/doc/pub/main_trunc-A4.pdf





