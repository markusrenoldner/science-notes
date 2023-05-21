[[Numerics for differential equations]]


a discretization method that replaces differential quotients by difference quotients.

For example in 1D and for a first order derivative:
$$\frac{f(x+\Delta x)-f(x)}{\Delta x}\approx\frac{df(x)}{dx}$$
Equally one can approximate "backwards":
$$\frac{f(x-\Delta x)-f(x)}{\Delta x}\approx\frac{df(x)}{dx}$$
or "centrally":
$$\frac{f(x+\Delta x)-f(x-\Delta x)}{2\Delta x}\approx\frac{df(x)}{dx}$$

## Assessing the "quality" of the approximation by finite differences:
[[Convergence, consistency, stability, condition of FDM]]
