# Big O  small o notation


With 
$$f\in \mathcal{O}(g)$$
we mean, that for at **least one** choice of a constant $C > 0$, you can find a constant $x_C$ such that the inequality 
$$0 \leq f(x) \leq C g(x)\quad \forall x>x_C$$

holds. 

And with 
$$f\in o(g)$$
we mean, that for at **every** choice of a constant $C > 0$, you can find a constant $x_C$ such that the inequality 
$$0 \leq f(x) \leq C g(x)\quad \forall x>x_C$$

holds.

Here $\mathcal{O}(g)$ and $o(g)$ are function spaces. 

--------------

We use them to discribe upper bounds of the functions, where small $o$ is the stronger bound:
$$f\in \mathcal{O}(g)\implies f\in o(g)$$

------------

$f\in \mathcal{O}(g)$ means that $f$'s asymptotic growth is **no faster** than $g$'s. This holds if the value of $g(x)$ is a constant multiple of the value of $f(x)$.

$f\in o(g)$ means that $f$'s asymptotic growth is **strictly slower** than $g$'s. This only holds if $g(x)$ includes a higher power of $x$ in its formula!

------------

Examples:
- $x^2 \in \mathcal{O}(x^2)$
- $x^2 \in \mathcal{O}(x^2+x)$
- $x^2 \in \mathcal{O}(1000x^2)$

but
- $x^2 \in o(x^3)$
- $x^2 \in o(x!)$
- $\text{ln}(x) \in o(x)$

---------

With limits

$$\begin{aligned}
    f\in \mathcal{O}(g) &\implies \lim_{x\to \infty} \frac{f(x)}{g(x)}=0\\
    f\in o(g) &\implies \limsup_{x\to \infty} \frac{f(x)}{g(x)}=0
\end{aligned}$$

## Source

- stack overflow: https://stackoverflow.com/questions/1364444/difference-between-big-o-and-little-o-notation
- wikipedia big O notation: https://en.wikipedia.org/wiki/Big_O_notation#Family_of_Bachmann%E2%80%93Landau_notations
- wikipedia limit superior: https://en.wikipedia.org/wiki/Limit_inferior_and_limit_superior

