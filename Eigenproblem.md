
Problem in [Linear algebra](Linear%20algebra.md)

See also: 
- [Eigenvalue multiplicity](Eigenvalue%20multiplicity.md)
- [Jordan Normalform](Jordan%20Normalform.md)



## Introduction
Consider a square matrix $A$.
Any (nontrivial) eigenpair $(\lambda_i,v_i)$ per definition satisfies
$$(A-\lambda_i\mathbb{I})v_i=0 \quad \iff \quad \operatorname{det}(A-\lambda_i\mathbb{I})=0$$

Firstly, the right expression is called characteristic polynomial:
$$P_A(\lambda_i):=\operatorname{det}(A-\lambda \mathbb{I})$$
and the eigenvalues are its roots.

Secondly, the left expression from above yields:
$$v_i\in \operatorname{ker}(A-\lambda_i\mathbb{I})=:\mathcal{E}_A(\lambda_i)$$
this space is called eigenspace of $\lambda_i$. It is the span of the eigenvalues corresponding to $λ_i$.



## Sources
- Prof. Auzinger - Lineare Algebra für TPH, TU Wien lecture 2020, [Auzinger-ana2TPH.pdf](Auzinger-ana2TPH.pdf)