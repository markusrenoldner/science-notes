t
## Functions
if it is not important
- how the function value is called
- what the function is doing
$$f(x): \mathbb{R}\rightarrow \mathbb{R}$$

if its not important what the domain and target set are:
$$f:(x,y) \mapsto x^2+4y$$

if additionally the domain and target set are important:
$$\begin{aligned}
f:\mathbb{R}^2 &\rightarrow \mathbb{R}\\
(x,y) &\mapsto x^2+4y
\end{aligned}$$
Or if we are only interested in the spaces:
$$\begin{aligned}
&f=f(x,y):\mathbb{R}^2 \rightarrow \mathbb{R} \\
\text{or alternatively: } \quad &f:(x,y)\mapsto \mathbb{R}
\end{aligned}$$


## Notation for $C^p$- and $L^p$-function spaces
Consider
$$\begin{aligned}
f:M &\rightarrow N\\
(x,y) &\mapsto x^2+4y
\end{aligned}$$
where $M\subseteq \mathbb{R}^2$ and $N\subseteq \mathbb{R}$. As the function is infinitely differentiable in both variables, we can write
$$f\in C^\infty(M)$$
If we would have a function with a multidimensional target set, e.g. $N\subseteq \mathbb{R}^3$, we can write
$$f\in [C^\infty(M)]^3$$
$C^\infty(M)$ is a function space, see [[Function spaces]].
The same notation is used for $L^p$ spaces, e.g.
$$f\in [L^2(M)]^3$$


## Operators
are maps that map functions to functions. An operator can e.g. map from a vector space into another vector space.

An example is a differential operator $D$. It can be denoted as follows:
$$D:C^1(M) \rightarrow C^0(M)$$
where $M$ is an open subset of $\mathbb{R}^n$.

Another example is a trace operator:
$$T:C^1(M)\rightarrow L^p(\partial M)$$
or e.g.
$$T:W^{1,p}(M)\rightarrow L^p(\partial M)$$
where now $W$ is a Sobolev space and $\partial M$ is the boundary of $M$

