# Equivalence class, quotient space

## Definition equivalence class
Let $v\in V$ and $u\in U$ with $U \subset V$.
We call $v_1\sim v_2$ "equivalent" iff.
$$v_1-v_2\in U \quad\text{for } v_1,v_2 \in V$$
That means, $v_1,v_2$ are equivalent if there difference is element of $U$ or: if the straight line through $v_1,v_2$ is parallel to $U$, they are equivalent.

An equivalence class of a vector $v$ is the set
$$ [v] := \text{"}v+U\text{"} := \{v+u | u\in U \}$$
in words: its the subspace of $V$ that passes $v$ and is parallel to $U$ 

An equivalence class is an [[Affine space]], see https://math.stackexchange.com/questions/3818358/show-that-an-equivalence-class-is-an-affine-subspace


## Definition quotient space
The quotient space "from $V$ to $U$" is the set of all equivalence classes, written as
$$V / U := \{[v] : v\in V\} $$
Alternative phrasing: the quotient space $V/U$ is the set of all affine subspaces of $V$ that are parallel to $U$.

A quotient space of two vector spaces is again a vector space.


## Sources
- https://de.wikipedia.org/wiki/Faktorraum
- https://en.m.wikipedia.org/wiki/Quotient_space_(linear_algebra)