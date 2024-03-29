# Calculus of variations


## Goal:
find extremum of a functional


## Definition of functional:
a function $f$ maps a vector/number to a vector/number

a functional $I$ maps a function to a real number

an example of a functional is an integral over a real-valued function:
$$I[f]:f\mapsto \int_\Omega f(s)\text{d}s$$

## Idea:
- let $(f_\alpha)$ be a familiy/set of functions parametrized by $\alpha\in(-\epsilon, \epsilon)$ for some $\epsilon > 0$
- its important to define the function $f_0$ to be the function that minimizes $I$ 
- replace the functional by a function: $F(\alpha):=I[f_\alpha]$ that is differentiable for $\alpha = 0$

this function $F$ has a minimum at $\alpha = 0$ as this point is also a minimum for $I$ :
$$\frac{\text{d}}{\text{d}\alpha}F(\alpha)\Large |_{\alpha=0} = 0$$
this also means:
$$\frac{\text{d}}{\text{d}\alpha}I[f_\alpha]\Large |_{\alpha=0} = 0$$

#todo  add euler lagrange, example with membrane, rope, etc, connection to variational formualtions of PDEs
https://math.stackexchange.com/questions/2393534/what-is-the-connection-between-calculus-of-variations-and-pdes
https://math.stackexchange.com/questions/3261183/variational-problem-is-equivalent-to-minimizing-the-energy-functional


## Sources
https://de.wikipedia.org/wiki/Variationsrechnung



## Example: quadratic functionals
[[Minimum of quadratic functionals]]
