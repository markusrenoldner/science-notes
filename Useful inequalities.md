# Useful inequalities
related to: [[Analysis]] and [[Linear algebra]]

Cauchy Schwarz
$$\langle u,v\rangle\leq \Vert u\Vert\Vert v\Vert$$
Triangle/Minkowski
$$\Vert u+v\Vert_{L^p}\leq \Vert u\Vert_{L^p}+\Vert v\Vert_{L^p}$$
The negative triangle inequality
$$\Vert z\Vert-\Vert a\Vert\leq \Vert z-a\Vert$$
Poincare
$$\Vert u\Vert_{L^p}\leq c\Vert\nabla u \Vert_{L^p},\quad\text{ if } \int_\Omega u=0, \text{or }u\in H_0^p(\Omega)$$
Curved Poincare
$$\Vert u\Vert_2 \leq C\Vert b \cdot \nabla u\Vert_2,\quad\text{if } u\in H_0(\Gamma_{in}) \text{ and } b \text{ 'filling'}$$
Hölder
$$\Vert uv\Vert_{L^1}\leq \Vert u\Vert_{L^p}\Vert v\Vert_{L^q},\quad\text{if } \frac{1}{p}+\frac{1}{q}=1$$
Young
$$ab\leq \frac{a^p}{p} + \frac{b^q}{q}, \qquad ab\leq \frac{a^2}{2} + \frac{b^2}{2}$$
a-b-inequality
$$
...\leq\frac{1}{2}(a+b)^2 \leq a^2 + b^2 \leq (a+b)^2  \leq ... \qquad \forall a,b>0
$$
#TODO Is this true for all $p\in(0,1), a>0,b>0$?
$$(a+b)^p\leq a^p+b^p$$
infinity norm trick: ($b,u$ can be vector valued functions):
$$\Vert b\cdot u\Vert_2 \leq\Vert b\Vert_\infty\Vert u\Vert_2 = \sup\vert b\vert\ \Vert u\Vert_2$$

## Proofs:

a-b-inequality
$$a^2+b^2\leq (a+b)^2 = a^2+b^2+2ab\stackrel{Young}{\leq} a^2+b^2+a^2+b^2=...$$
Negative triangle: use triangle with $z=a+b$.

Youngs inequality ($a,b\geq 0,\epsilon >0$):
$$0\leq (a-\epsilon b)^2=a^2+\epsilon^2 b^2-2ab\epsilon \implies ab\leq \frac{1}{2\epsilon}a^2+\frac{\epsilon}{2}b^2$$
infinity norm trick:
$$\begin{align}
\Vert b\cdot u\Vert_2^2 &= \int\vert b\cdot u\vert^2\\
&\stackrel{CS}{\leq} \int (\vert b\vert \vert u\vert)^2\\
&= \int \vert b\vert^2 \vert u\vert^2\\
&\leq \int \Vert b\Vert_\infty^2 \vert u\vert^2\\
&= \Vert b\Vert_\infty^2\int  \vert u\vert^2\\
&=\Vert b\Vert_\infty^2\Vert u\Vert_2^2
\end{align}$$
