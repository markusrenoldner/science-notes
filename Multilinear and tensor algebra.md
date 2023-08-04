[[Linear algebra]]


#pdf-note [[tensors-short.pdf]]

#todo (also take "online summary from F J")


#todo generalize the following articles to index notation:
- [[Coordinate vectors, coordinate maps]]
- [[Change of basis in linear algebra]]
- [[Transformation matrices, linear maps]]
(and maybe simplify the articles or extract the main theorems in a short overview)


## Topics
- asdf



## Some tensor algebra stuff
we know that the tensor product allows to write
$$\vec{a} \cdot \underset{\sim}{T}=\sum_{i, j, k} a_i T_{j k} \vec{e}_i \cdot\left(\vec{e}_j \otimes \vec{e}_k\right)=\sum_{i, j, k} a_i T_{j k} \delta_{i j} \vec{e}_k=\sum_{i, k} a_i T_{i k} \vec{e}_k$$ as well as
$$\underset{\sim}{T} \cdot \widetilde{\vec{b}}=\sum_{i, j, k} T_{i j} b_k\left(\vec{e}_i \otimes \vec{e}_j\right) \cdot \vec{e}_k=\sum_{i, j, k} T_{i j} b_k \delta_{j k} \vec{e}_i=\sum_{i, j} T_{i j} b_j \vec{e}_i$$
which allows to get the components from the tensor:
$$\begin{align}
\vec{e}_i \underset{\sim}{T} \vec{e}_l &= \sum_{ijkl} (1 T_{jk}\cdot 1) \vec{e}_i (\vec{e}_j \otimes\vec{e}_k)\vec{e}_l \\
&= \sum_{ijkl} T_{jk} \delta_{ij} \vec{e}_k \vec{e}_l\\
&= \sum_{ijkl} T_{jk} \delta_{ij} \delta_{kl}\\
&= T_{il}
\end{align}$$
source: prechtl-edyn






#todo do i need this?
- ingmathe yt
- Prof. Svozil - Mathematische Methoden der theoretischen Physik, TU Wien lecture notes
- uniwien lecture
- vec calcl from altland: L10 multilin algebra (maybe more tensor/diffgeo?)


## Source
- Dr. Ginosar - Lineare Algebra, ETH lecture notes 2021, [[Ginosar-Lineare_Algebra.pdf]]
- Altland, Delft - Mathematics for Physicists
- Eigenchris playlist on Tensor algebra: https://www.youtube.com/playlist?list=PLJHszsWbB6hrkmmq57lX8BV-o-YIOFsiG

