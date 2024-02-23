# Affine space
Important idea in [[Finite Element Method (FEM)]]

## Definition
Given:
- a vector space $V$
- a subspace $V_0\subset V$
- some $g \in V$ ("offset function/vector")
- some $v_0 \in V_0$
we call
$$ \hat{V} := g + V_0 := \{v = g+v_0 \} $$
an affine subspace of $V$.  It holds that
$$\hat{V} \subset V$$
It is not a vector space, as
- $\vec{0} \notin \hat{V}$
- $v_1+v_2 \notin \hat{V}$ for $v_1, v_2 \in \hat{V}$


## Interpretation
the affine space $\hat{V}$ is a "shifted" or "translated" subspace


## Source:
- https://en.wikipedia.org/wiki/Affine_space#/media/File:Affine_space_R3.png
- Prof. Hiptmair - Numerical Methods for Partial Differential Equations, ETH lecture notes 2021

