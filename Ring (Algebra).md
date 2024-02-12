# Ring (Algebra)
[[Linear algebra]]


## Definition
A ring is a set $R$ with the two operations addition and multiplication:
$$\begin{aligned}
+ &: R\times R \rightarrow R \\
\cdot &: R\times R \rightarrow R
\end{aligned}$$
and the following properties:
-  is an Abelian Group (see [[Group]])
- $\cdot$ is associative
- it holds that $a\cdot(b+c) = a\cdot b + a\cdot c$
  
A ring is called unitary ring or ring with unity if $$\exists 1 \in R \ \text{ st. } 1\cdot a = a\cdot 1 = a \forall a\in R$$ this element is called unity- or one-element.


## Lemma ("good to know")
Seemingly

$$a \cdot 0 = 0$$
Proof
Take $0+ 0 = 0$ and distributivity:
$$0\cdot a = (0+0)\cdot a = 0\cdot a+ 0\cdot a$$
add the inverse of (fancy way of saying subtract) $0\cdot a$ and use associativity
$$0 = 0\cdot a - 0\cdot a (0\cdot a + 0\cdot a) - 0\cdot a = 0\cdot a + (0\cdot a -0\cdot a)= 0\cdot a + 0 = 0\cdot a$$
Beautiful.


## Source
Dr. Ginosar - Lineare Algebra, ETH lecture notes 2021