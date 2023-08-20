up: [[Tensor and multilinear algebra]]

We only talk about "arrow vectors", not the abstract vector that is just characterised as an element of a vector space, such as functions.
We also use Einsteins sum convention (implicit summation over pairs of co-/contravariant indices, see [[Vector and covector transformation]])

## General tensor transformation rule, action/multiplication formula and array shapes:
Def. Tensor: A (multi-)linear combination of vectors and covectors

General tensor (in Einstein sum convenction):
$$\begin{equation}
    T = \underbrace{{{T^{ij}}_k}^l}_{\text{components}} \underbrace{e_i \otimes e_j  \otimes \epsilon^k \otimes e_l}_{\text{"basis tensor"}}
\end{equation}$$
sometimes tensors are just written in the component notation:
$$\begin{equation}
    {{T^{ij}}_k}^l
\end{equation}$$
We call this a (3,1)-tensor (nr of co-/contravariant components).

How does it transform? How does it act/multiply on/with other tensors? How does its array representation look like?
1. Transformation rule for componentes in new basis: just transform the vectors and covectors! 
$$\begin{align}
T &= {{T^{ij}}_k}^l (e_i \otimes e_j  \otimes \epsilon^k \otimes e_l)\\
&= {{T^{ij}}_k}^l (({B^a}_i\tilde e_a) \otimes ({B^b}_j\tilde e_b)  \otimes ({F^k}_c\tilde \epsilon^c )\otimes ({B^d}_l\tilde e_d))\\
&= {B^a}_i {B^b}_j{B^d}_l {{T^{ij}}_k}^l {F^k}_c (\tilde e_a \otimes \tilde e_b  \otimes \tilde \epsilon^c \otimes \tilde e_d)\\
&= {{ \tilde T^{ab}}_c}^d  (\tilde e_a \otimes \tilde e_b  \otimes \tilde \epsilon^c \otimes \tilde e_d)
\end{align}$$
2. How does a tensor act on another? See video, sometimes this is confusing, if one is too sloppy with Einsteins sum convention. If you know over which indices you want to sum, and which covectors take which vectors as inputs in the tensorproduct, you are good.
3. Use the Kronecker product for arrays "$\otimes$": take the array on the left and distribute it to each component on the right, e.g consider the tensor with components ${{T^{ij}}_k}^l$:
$$\begin{align}
\begin{pmatrix}\cdot\\\cdot \end{pmatrix}\otimes \begin{pmatrix}\cdot\\\cdot \end{pmatrix}\otimes \begin{pmatrix}\cdot&\cdot \end{pmatrix}\otimes \begin{pmatrix}\cdot\\\cdot \end{pmatrix}
&= \begin{pmatrix}\begin{pmatrix}\cdot\\\cdot \end{pmatrix} \\ \begin{pmatrix}\cdot\\\cdot \end{pmatrix} \end{pmatrix}\otimes \begin{pmatrix}\cdot&\cdot \end{pmatrix}\otimes \begin{pmatrix}\cdot\\\cdot \end{pmatrix}\\
&= \begin{pmatrix}\begin{pmatrix}\begin{pmatrix}\cdot\\\cdot \end{pmatrix} \\ \begin{pmatrix}\cdot\\\cdot \end{pmatrix} \end{pmatrix} & \begin{pmatrix}\begin{pmatrix}\cdot\\\cdot \end{pmatrix} \\ \begin{pmatrix}\cdot\\\cdot \end{pmatrix} \end{pmatrix}\end{pmatrix}\otimes \begin{pmatrix}\cdot\\\cdot \end{pmatrix}\\
&= \begin{pmatrix}\begin{pmatrix}\begin{pmatrix}\begin{pmatrix}\cdot\\\cdot \end{pmatrix} \\ \begin{pmatrix}\cdot\\\cdot \end{pmatrix} \end{pmatrix} & \begin{pmatrix}\begin{pmatrix}\cdot\\\cdot \end{pmatrix} \\ \begin{pmatrix}\cdot\\\cdot \end{pmatrix} \end{pmatrix}\end{pmatrix}\\\begin{pmatrix}\begin{pmatrix}\begin{pmatrix}\cdot\\\cdot \end{pmatrix} \\ \begin{pmatrix}\cdot\\\cdot \end{pmatrix} \end{pmatrix} & \begin{pmatrix}\begin{pmatrix}\cdot\\\cdot \end{pmatrix} \\ \begin{pmatrix}\cdot\\\cdot \end{pmatrix} \end{pmatrix}\end{pmatrix} \end{pmatrix}
\end{align}$$
which is a "column of rows of colums of colums".
Wikpedia seems to define the kronecker product the other way round (distribte right array to left components) https://en.wikipedia.org/wiki/Kronecker_product
is this the same?


## Tensor product vs kronecker product vs tensor product of vector spaces
1. The kronecker product acts on arrays (explained above). It just creates a big array.
2. The tensor product combines abstract vectors and covectors in the tensor space in a multilinear way, its a multilinear map. It creates a tensor of higher order (sum of order of input tensors). But the components that the tensor product yields are exactly the components that the kronecker product yields on the respective row and column vectors representing the abstract (co-)vectors.
3. The tensor product of vector spaces combines vector and dual spaces. E.g. (1,1)-tensors (i.e. linear maps) $L={L^i}_j (e_i\otimes \epsilon^j) \in V \otimes V^*$. Elements of this space can be interpreted as the following maps:
$$\begin{align}
     v &\mapsto {L^i}_j v^j e_i \quad && V\to V\\
     \alpha &\mapsto {L^i}_j (e_i \otimes \epsilon^j)  (\alpha_k \epsilon^k) = {L^i}_j \alpha_i \epsilon^j && V^*\to V^*\\
     v\alpha &\mapsto {L^i}_j v^j\alpha_i &&V\times V^* \to \mathbb{R}\\
     \alpha v&\mapsto {L^i}_j \alpha_i v^j &&V^*\times V  \to \mathbb{R}
\end{align}$$
Depending on what we feed into the tensor, the output is a different object.
#todo video15


## Example (1,1)-tensor/"linear map"
Linear maps from linear algebra perspective: [[Transformation matrices, linear maps]]
Example: (1,1)-tensor, aka. linear map ($L:V\to V:v\mapsto {L^i}_j v^j e_i$)
1. transformation:
$$\begin{align}
    L&={L^i}_j (e_i \otimes \epsilon^j) \\
    &= {L^i}_j ({B^a}_i\tilde e_a)\otimes({F^j}_b\tilde \epsilon^b)\\
    &= {B^a}_i{L^i}_j {F^j}_b (\tilde e_a\otimes\tilde \epsilon^b)\\
    &= {\tilde L^a}_b(\tilde e_a\otimes\tilde \epsilon^b)\\
    &\implies {\tilde L^a}_b = {B^a}_i{L^i}_j {F^j}_b
\end{align}$$
2. action on other tensors:
$$\begin{align}
    w=L(v)&= {L^i}_j (e_i \otimes \epsilon^j) (v^k e_k)\\
    &= {L^i}_j v^k (e_i \otimes \underbrace{\epsilon^j  e_k}_{=\delta^j_k})\\
    &= \underbrace{{L^i}_j v^j}_{\text{coeff.}} \underbrace{e_i}_{\text{basis}}\\
	&\equiv w^i e_i
\end{align}$$
The coefficients obey the known matrix-vector multiplication rule - and in this sense, define this rule!
The basis of $L$, i.e. $e_i \otimes \epsilon^j$, is indeed a linear map, as $\epsilon^j$ "eats" a vector by definition, and the result is a number; the rest is just $e_i$ - a vector, which is the output of a linear map.

3. array shape: given by kronecker product of $e_i \otimes \epsilon^j$, which yields a row of columns (matrices). Example:
$$\begin{align}
    e_1 \otimes \epsilon^1 &=\begin{pmatrix}1\\0\end{pmatrix}\otimes \begin{pmatrix}1&0\end{pmatrix}=\begin{pmatrix} 1\begin{pmatrix}1\\0\end{pmatrix}&0 \begin{pmatrix}1\\0\end{pmatrix}\end{pmatrix}&&= \begin{pmatrix}1&0\\0&0\end{pmatrix} \\
    e_1 \otimes \epsilon^2   &=\begin{pmatrix}1\\0\end{pmatrix}\otimes \begin{pmatrix}0&1\end{pmatrix}=...&&= \begin{pmatrix}0&1\\0&0\end{pmatrix}\\
    &...
\end{align}$$
For an example with actual numbers, check this:
[[Example linear map transformation]].


## Example (0,2)-tensor/"bilinear form"
Example: (0,2)-tensor, aka. bilinear form ( $B:V\times V \to \mathbb{R}: (v,w)\mapsto v^i w^j B_{ij}$)
1. transformation: 
$$\begin{align}
B &= B_{ij} (\epsilon^i\otimes \epsilon^j)\\
&=B_{ij} (({F^i}_a \tilde \epsilon^a)\otimes({F^j}_b\tilde \epsilon^b))\\
&= B_{ij}{F^i}_a {F^j}_b (\tilde \epsilon^a \otimes\tilde \epsilon^b)\\
&= \tilde B_{ab} (\tilde \epsilon^a \otimes\tilde \epsilon^b)\\
&\implies \tilde B_{ab}= B_{ij}{F^i}_a {F^j}_b
\end{align}$$
2. tensor action (taking two vectors and outputting number):
$$\begin{align}
    b=B(v,w)&= B_{ij} (\epsilon^i\otimes \epsilon^j) (v^k e_k w^l e_l)\\
    &= B_{ij} v^k w^l \delta^i_k \delta^j_l\\
    &= B_{ij} v^i w^j \in \mathbb{R}
\end{align}$$
3. array shape: given by kronecker product of $\epsilon^i \otimes \epsilon^j$, which yields a row of rows:
$$\begin{equation}
    \epsilon^1 \otimes \epsilon^1=\begin{pmatrix}1&0\end{pmatrix}\otimes \begin{pmatrix}1&0\end{pmatrix} = ... = \begin{pmatrix}\begin{pmatrix}1&0\end{pmatrix}&\begin{pmatrix}0&0\end{pmatrix}\end{pmatrix}
\end{equation}$$
The [[Metric tensor]] is a bilinearform.


## Source:
Eigenchris playlist on Tensor algebra: https://www.youtube.com/playlist?list=PLJHszsWbB6hrkmmq57lX8BV-o-YIOFsiG