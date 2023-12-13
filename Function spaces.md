[[Analysis]]


## Topics:
- [[Function and operator notation]]
- Spaces: normed, Banach, Hilbert
- The space $C^m$
- The space $L^p$

## Lp spaces

#todo mention that "L2 spaces with norm" are defined using [[Equivalence class, quotient space]]. This implies that point values of functions in that space have no meaning. Two functions that only differ on intervals/sets with measure zero (like e.g. points), are equal in the "L2-sense".
see https://math.stackexchange.com/questions/4539948/notation-for-multivariate-lebesgue-space
see https://de.wikipedia.org/wiki/Lp-Raum
### $L^2$
#todo 

## Sobolev spaces

### $H^1$
is defined as $H^1:=\{u\in L^2: \nabla u\in L^2\}$
$H1$ functions are continuous! Otherwise the weak differentiability would not work!

### $H^1_0$
is defined as $H^1:=\{u\in H^1: tr(u)=0 \text{ on } \partial \Omega\}$

### $H^{-1}$ 
is the dual space of $H^1_0$ , i.e. it contains linear functionals/covectors map from $H_0^1\rightarrow \mathbb{R}$ 

### $H(\text{curl})$
is defined as $H(\text{curl}):=\{u\in L^2: \nabla\times u\in L^2\}$

Properties of these spaces in the context of [[Finite Element Method (FEM)]] are described in [[Sobolev space properties]].


## Subsets

Of course 
$$H^1 \subset L^2$$
and 
$$H^2\subset H^1$$
etc.


## Sources:
- Prof. Auzinger - Analysis 2 für TPH, TU Wien lecture notes
- Prof. Kaltenböck - Analysis für technische Mathematik, TU Wien lecture notes
