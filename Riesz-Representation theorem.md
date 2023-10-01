Shows unisolvence of continuous and discrete [[Variational problem]]s where the bilinearform is an inner product.
See [[Solvability of variational problems]].


One can always define a functional $$l_u(v):= (u,v) \quad \forall v\in V$$ for any $u$, as the inner product is linear in $v$. But interestingly, one can also do the reverse:
One can always define an inner product with a unique $u_l$: $$(u_l, v) := l(v) \quad \forall v\in V$$ for any bounded $l$. 

This gives unisolvence of the abstract problem to find a unique $u$ that satisfies $$(u,v)=f(v) \quad \forall v,$$ if $(.,.)$ is an inner product (and therefore also a bilinearform). 
It shows that the poisson problem $-\Delta u = f$ in weak form has a unique solution. This also applies to the discrete approximation of this problem.


## Sources
- Prof. Faustmann - Numerical Methods for Partial Differential Equations, TU Wien lecture notes 2021