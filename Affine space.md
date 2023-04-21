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
It is not a [[Vector space]], as
- $\vec{0} \notin \hat{V}$
- $v_1+v_2 \notin \hat{V}$ for $v_1, v_2 \in \hat{V}$


## Interpretation
the affine space $\hat{V}$ is a "shifted" or "translated" subspace


## Example
In this image, $P_1:= V_0$ and $P_2:=\hat{V}$ and the whole space $\mathbb{R}^3=V$ 
The vector $\hat{v}$ could be 
$$\hat{v}=\begin{pmatrix}0\\0\\k \end{pmatrix}$$
where $k$ is the point where $P_2$ intersects the z-axis.

![[affinespace.png]]



## Source:
- https://en.wikipedia.org/wiki/Affine_space#/media/File:Affine_space_R3.png
- Hiptmair, Numeric methods for PDEs
