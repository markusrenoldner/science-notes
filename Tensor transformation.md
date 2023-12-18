up: [[Tensor and multilinear algebra]]

We only talk about "arrow vectors", not the abstract vector that is just characterised as an element of a vector space, such as functions.
We also use Einsteins sum convention (implicit summation over pairs of co-/contravariant indices, see [[Vector and covector transformation]])


## General tensor transformation rule, action/multiplication formula and array shapes:
Def. Tensor: A (multi-)linear combination of vectors and covectors

General tensor (in Einstein sum convenction):
$$T=\underbrace{{T^{ij}}_k{}^l}_{\text{components}} \underbrace{e_i \otimes e_j  \otimes \epsilon^k \otimes e_l}_{\text{"basis tensor"}}$$
sometimes tensors (similar like vectors) are just represented by their components, i.e.:
$$
    {T^{ij}}_k{}^l
$$
We call this a (3,1)-tensor (nr of co-/contravariant components).

How does it transform? How does it act/multiply on/with other tensors? How does its array representation look like?
1. Transformation rule for componentes in new basis: just transform the vectors and covectors! 
$$\begin{aligned}
T &= {T^{ij}}_k{}^l (e_i \otimes e_j  \otimes \epsilon^k \otimes e_l)\\
&= {T^{ij}}_k{}^l (({B^a}_i\tilde e_a) \otimes ({B^b}_j\tilde e_b)  \otimes ({F^k}_c\tilde \epsilon^c )\otimes ({B^d}_l\tilde e_d))\\
&= {B^a}_i {B^b}_j{B^d}_l {T^{ij}}_k{}^l {F^k}_c (\tilde e_a \otimes \tilde e_b  \otimes \tilde \epsilon^c \otimes \tilde e_d)\\
&= { {\tilde T^{ab}}_c}{}^d  (\tilde e_a \otimes \tilde e_b  \otimes \tilde \epsilon^c \otimes \tilde e_d)
\end{aligned}$$
2. How does a tensor act on another? See video 14 and 15, sometimes there is more than one way to carry out the index summations: match components accordingly:
$$\begin{aligned}
    T(Q) &= {T^{ij}}_k{}^l (e_i \otimes e_j  \otimes \epsilon^k \otimes e_l) ({Q^a}_b (e_a\otimes \epsilon^b)) \quad &&\text{ambiguous }\\
    T(Q)&= {T^{ij}}_k{}^l {Q_i}^k &&\text{clear} \\
    T(Q)&= {T^{ij}}_k{}^l {Q_i}^k(e_j \otimes e_l ) &&\text{clear} 
\end{aligned}$$

1. Use the Kronecker product for arrays "$\otimes$": take the array on the left and distribute it to each component on the right, e.g consider the tensor with components ${{T^{ij}}_k}^l$:
$$\begin{aligned}
\begin{pmatrix}\cdot\\\cdot \end{pmatrix}\otimes \begin{pmatrix}\cdot\\\cdot \end{pmatrix}\otimes \begin{pmatrix}\cdot&\cdot \end{pmatrix}\otimes \begin{pmatrix}\cdot\\\cdot \end{pmatrix}
&= \begin{pmatrix}\begin{pmatrix}\cdot\\\cdot \end{pmatrix} \\ \begin{pmatrix}\cdot\\\cdot \end{pmatrix} \end{pmatrix}\otimes \begin{pmatrix}\cdot&\cdot \end{pmatrix}\otimes \begin{pmatrix}\cdot\\\cdot \end{pmatrix}\\
&= \begin{pmatrix}\begin{pmatrix}\begin{pmatrix}\cdot\\\cdot \end{pmatrix} \\ \begin{pmatrix}\cdot\\\cdot \end{pmatrix} \end{pmatrix} & \begin{pmatrix}\begin{pmatrix}\cdot\\\cdot \end{pmatrix} \\ \begin{pmatrix}\cdot\\\cdot \end{pmatrix} \end{pmatrix}\end{pmatrix}\otimes \begin{pmatrix}\cdot\\\cdot \end{pmatrix}\\
&= \begin{pmatrix}\begin{pmatrix}\begin{pmatrix}\begin{pmatrix}\cdot\\\cdot \end{pmatrix} \\ \begin{pmatrix}\cdot\\\cdot \end{pmatrix} \end{pmatrix} & \begin{pmatrix}\begin{pmatrix}\cdot\\\cdot \end{pmatrix} \\ \begin{pmatrix}\cdot\\\cdot \end{pmatrix} \end{pmatrix}\end{pmatrix}\\\begin{pmatrix}\begin{pmatrix}\begin{pmatrix}\cdot\\\cdot \end{pmatrix} \\ \begin{pmatrix}\cdot\\\cdot \end{pmatrix} \end{pmatrix} & \begin{pmatrix}\begin{pmatrix}\cdot\\\cdot \end{pmatrix} \\ \begin{pmatrix}\cdot\\\cdot \end{pmatrix} \end{pmatrix}\end{pmatrix} \end{pmatrix}
\end{aligned}$$
which is a "column of rows of colums of colums".
Wikpedia seems to define the kronecker product the other way round (distribte right array to left components) https://en.wikipedia.org/wiki/Kronecker_product
is this the same?


## Tensor product vs kronecker product vs tensor product of vector spaces
1. The kronecker product acts on arrays (explained above). It just creates a big array.
2. The tensor product combines abstract vectors and covectors in the tensor space in a multilinear way. It creates a tensor of higher order (sum of order of input tensors). But the components that the tensor product yields are exactly the components that the kronecker product yields on the respective row and column vectors representing the abstract (co-)vectors.
3. The tensor product of vector spaces combines vector and dual spaces. E.g. (1,1)-tensors (i.e. linear maps) $L={L^i}_j (e_i\otimes \epsilon^j) \in V \otimes V^*$. Elements of this space can be interpreted as the following (multilinear) maps:
$$\begin{aligned}
     v &\mapsto {L^i}_j v^j e_i \quad && V\to V\\
     \alpha &\mapsto {L^i}_j (e_i \otimes \epsilon^j)  (\alpha_k \epsilon^k) = {L^i}_j \alpha_i \epsilon^j && V^*\to V^*\\
     v\alpha &\mapsto {L^i}_j v^j\alpha_i &&V\times V^* \to \mathbb{R}\\
     \alpha v&\mapsto {L^i}_j \alpha_i v^j &&V^*\times V  \to \mathbb{R}
\end{aligned}$$
Again, one could also just consider the components without the basis which contains all information we need:
$$\begin{aligned}
     v &\mapsto {L^i}_j v^j \quad && V\to V\\
     \alpha &\mapsto {L^i}_j \alpha_i && V^*\to V^*
\end{aligned}$$
Depending on what we feed into the tensor, the output is a different object.


## Examples: 
[[Example (1,1)-tensor transformation]]

Compare this with this example with [[Linear algebra]] notation, check this:
[[Example linear map transformation]].
Linear maps from linear algebra perspective: [[Transformation matrices, linear maps]].

[[Example (0,2)-tensor transformation]]


## Source:
Eigenchris playlist on Tensor algebra, mostly video 13-15: https://www.youtube.com/playlist?list=PLJHszsWbB6hrkmmq57lX8BV-o-YIOFsiG