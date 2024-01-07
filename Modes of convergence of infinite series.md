# Modes of convergence of infinite series
different notions how series (or sequences) converge (have a limit) to a particular value/function.

## Definition: pointwise convergence
We say that an infinite series $\sum_{n=1}^{\infty} f_n(x)$ converges to $f(x)$ pointwise in $(a, b)$ if it converges to $f(x)$ for each $a<x<b$. That is, for each $a<x<b$ we have
$$
\left|f(x)-\sum_{n=1}^N f_n(x)\right| \rightarrow 0 \text { as } N \rightarrow \infty
$$

## Definition: uniform convergence
We say that the series converges uniformly to $f(x)$ in $[a, b]$ (closed interval includes boundary values $a$ and $b$!!!) if
$$
\max _{a \leq x \leq b}\left|f(x)-\sum_{n=1}^N f_n(x)\right| \rightarrow 0 \quad \text { as } \quad N \rightarrow \infty
$$

## Definition: mean-square/L2 convergence
We say that the series converges in the mean-square (or $\left.L^2\right)$ sense to $f(x)$ in $(a, b)$ if
$$
\int_a^b\left|f(x)-\sum_{n=1}^N f_n(x)\right|^2 d x \rightarrow 0 \quad \text { as } \quad N \rightarrow \infty
$$

## Interpretation
Every uniformly convergent sequence is pointwise convergent, to the same limiting function, but some pointwise convergent sequences are not uniformly convergent. If $$f_n:[0,1) \rightarrow[0,1)$$ is a sequence of functions defined by $$f_n(x)=x^n,$$then $$\lim _{n \rightarrow \infty} f_n(x)=0 \text{ pointwise}$$ on the interval $[0,1)$, but not uniformly.
The pointwise limit of a sequence of continuous functions may be a discontinuous function, but only if the convergence is not uniform.


## Source
- Prof. Tornberg - Numerical solutions of differential equations, KTH lecture notes 2022, lecture 10
- https://en.wikipedia.org/wiki/Pointwise_convergence
