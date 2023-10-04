
we know that the tensor product allows to write
$$\vec{a} \cdot \underset{\sim}{T}=\sum_{i, j, k} a_i T_{j k} \vec{e}_i \cdot\left(\vec{e}_j \otimes \vec{e}_k\right)=\sum_{i, j, k} a_i T_{j k} \delta_{i j} \vec{e}_k=\sum_{i, k} a_i T_{i k} \vec{e}_k$$ as well as
$$\underset{\sim}{T} \cdot \widetilde{\vec{b}}=\sum_{i, j, k} T_{i j} b_k\left(\vec{e}_i \otimes \vec{e}_j\right) \cdot \vec{e}_k=\sum_{i, j, k} T_{i j} b_k \delta_{j k} \vec{e}_i=\sum_{i, j} T_{i j} b_j \vec{e}_i$$
which allows to get the components from the tensor:
$$\begin{aligned}
\vec{e}_i \underset{\sim}{T} \vec{e}_l &= \sum_{ijkl} (1 T_{jk}\cdot 1) \vec{e}_i (\vec{e}_j \otimes\vec{e}_k)\vec{e}_l \\
&= \sum_{ijkl} T_{jk} \delta_{ij} \vec{e}_k \vec{e}_l\\
&= \sum_{ijkl} T_{jk} \delta_{ij} \delta_{kl}\\
&= T_{il}
\end{aligned}$$
source: prechtl-edyn
#todo i dont understand what $T$ is, is it the tensor in the standard basis?
