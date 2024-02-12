# Group
fundamental idea in [[Linear algebra]]

## Definition

A group is a set $G$ together with an element $e\in G$, the neutral element, as well as an operation $G\cdot G \rightarrow G$ that satisfies
- $a\cdot (b\cdot c) = (a\cdot b) \cdot c$ ... Associativity
- $e\cdot g = g$ ... neutral element
- $g' \cdot g = e$ ... inverse element
Its denoted by the triple: $(G,e,\cdot)$

The notation of the operation means, that $\cdot$ takes two elements and outputs a third element, all from $G$.

An example of a group is $(\mathbb{R}, 0, +)$. The triple $(\mathbb{N},0,+)$ is not a group, as its members dont have inverse elements.

## Some results for groups

- The neutral element of a group is unique
- The inverse element of  is unique, which allows to write 
- for all $a,b\in G$ we have $(a^{-1})^{-1} = a$ and $(ab)^{-1} = a^{-1} b^{-1}$
- for all $a,b,c\in G$ we have $ab=ac$ if and only if $b=c$. Same for $ba=ca$

(Proof in [1])

## Some more definitions:

- A group is called abelian ("abelsch") if it is commuative: $a\cdot b = b\cdot a$
- A subset of $G$ is a subgroup of $G$ if it is a group.
- Let $(G,\cdot)$ and $(H,*)$ be groups. A mapping $\phi : G\rightarrow H$ is a homomorphism if
$$\phi(a \cdot b) = \phi(a) * \phi(b), \qquad \forall a,b\in H $$
- A bijective homomorphism is an isomorphism.

## Lemma: homomorphisms map neutral and inverse elements of groups

Let $\phi$ be a homomorphism and $e_i$ be the neutral element of group $i$. Then:
$$\phi(e_G) = e_H,\quad \text{and }\quad\phi(a^{-1}) = \phi(a)^{-1}$$
Proof: 
1. by above definitions: $$\phi(e_G) = \phi(e_G\cdot e_G) = \phi (e_G)* \phi(e_G)$$Now apply $\phi(e_G)^{-1}$ from left
$$e_H = \phi(e_G)^{-1} * \phi (e_G)* \phi(e_G) = e_H *\phi (e_G) = \phi(e_G) $$

2. Let $a\in G$. We just showed that$$ \phi(a) * \phi(a^{-1}) = \phi (a\cdot a^{-1}) = \phi (e_G) = e_H$$But we also know that
$$ \phi(a^{-1}) * \phi(a) = \phi (a^{-1} \cdot a) = \phi (e_G) = e_H$$

As the inverse element is unique (see [[Group#Some results for groups]]), the statement follows.


## Source
1. Dr. Ginosar - Lineare Algebra, ETH lecture notes 2021
2. Atland, Delft - Mathematics for Physicists
