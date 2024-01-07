# Vector and covector transformation
up: [[Tensor and multilinear algebra]]

We only talk about "arrow vectors", not the abstract vector that is just characterised as an element of a vector space, such as functions.

To define tensors, we need vectors, covectors and their transformation rules.

## Forward and backward transformations
Assume an "old basis" and a "new basis" respectively:
$$
    \{e_1,e_2\}:=\left \{ \begin{pmatrix}1\\0\end{pmatrix}, \begin{pmatrix}0\\1\end{pmatrix} \right \}, \qquad \{f_1,f_2\}:=\left \{ \begin{pmatrix}2\\1\end{pmatrix}, \begin{pmatrix}-\frac{1}{2}\\\frac{1}{4}\end{pmatrix} \right \}
$$
(all vector arrays above are represented in the canonical basis; also: all basis vectors are reresented by column vectors by convention)
Instead of the array representation, we can expand the new basis as a linear combination of the old basis vectors 
$$f_1 = 2e_1+1e_2,\quad f_2 = -\frac{1}{2}e_1 + \frac{1}{4}e_2$$

Then we define the forward transformation $F$ as the linear map, represented by a matrix such that the following matrix multiplication works out: 
$$\begin{aligned}
    (f_1, f_2) &= (e_1,e_2) \cdot F\\
    \implies \begin{pmatrix} 2&-\frac{1}{2}\\ 1&\frac{1}{4}\end{pmatrix} &= \begin{pmatrix}1&0\\0&1\end{pmatrix} \cdot \begin{pmatrix}2&-\frac{1}{2}\\1&\frac{1}{4}\end{pmatrix}
\end{aligned}$$
So $F$ is just the matrix of the basis vectors of the new basis represented as coordinate vectors (see [[Coordinate vectors, coordinate maps]]) of the old basis.

The inverse is the backwards transformation:

$$
    (e_1, e_2) = (f_1, f_2)\cdot B
$$

Using Einsteins summation convention:
$$\begin{aligned}
    f_i &= {F^j}_{i} e_j\\
    e_i &= {B^j}_{i} f_j
\end{aligned}$$
Easy to see, that the are inverses:
$$
    e_i = B^j_{i}f_j=B^j_{i} (F^k_{j}e_k)=F^k_{j}B^j_{i}e_k
$$
we need $e_1 = e_1, ...e_n=e_n$, so: $F^k_{j}B^j_{i}=\delta^k_{i}$

In [[Change of basis in linear algebra]], the matrix $S\equiv B$! 
Co-variant variables transform with $F$ from new to old and have lower indices
Contra-variant variables transform with $B$ and have upper indices.



## Vectors
Vectors are elements of vector spaces (denote by $V$), that means they can be added and scaled. Using a basis, we can write:
$$\begin{aligned}
    v&=1e_1+1.5e_2 \\
    &=1f_1+2f_2
\end{aligned}$$
or even:
$$
    \begin{pmatrix}1\\1.5\end{pmatrix}_{e_i}\quad and \quad \begin{pmatrix}1\\2\end{pmatrix}_{f_i} 
$$
see [[Coordinate vectors, coordinate maps]].


## Covectors
...are functionals, they map vectors to $\mathbb{R}$. 
We represent them by as "row-vectors":
$$\begin{aligned}
    \alpha:V&\to\mathbb{R} \\
     \begin{pmatrix}v^1\\v^2\end{pmatrix} &\mapsto \begin{pmatrix}\alpha_1&\alpha_2\end{pmatrix} \begin{pmatrix}v^1\\v^2\end{pmatrix} = \alpha_1v^1+\alpha_2 v^2
\end{aligned}$$

Visual, see video.
Covectors live in a vector space, called dual space, denoted by $V^*$. Properties
$$\begin{aligned}
    (m\alpha+n\beta)(v) &= m\alpha(v) + n\beta(v)\\
    \alpha(mv+nw)&=m\alpha (v)+n\alpha(w)
\end{aligned}$$
with $n,m\in\mathbb{N},\quad \alpha,\beta\in V^*, \quad v,w\in V$

They can be linearly combined from basis covectors:
$$\begin{aligned}

\alpha &= \alpha_i \epsilon^i

\end{aligned}$$
where the $\epsilon^i$ are defined by
$$

\epsilon^i (e_j) \equiv \delta^i_j

$$
which gives the following expression for its components:
$$\alpha_i = \alpha(e_i).$$

**Proof** (that the definition of $\epsilon_i$ yields the components and the fact that the $\epsilon_i$ form a basis of $V^*$):
notice, that
$$\begin{aligned}

\epsilon^1(v) &= \epsilon^1(v^1e_1 + v^2e_2) = ... &&= v^1\\

\epsilon^2(v) &= ... &&=v^2

\end{aligned}$$
Now we apply a general covector to a general vector
$$\begin{aligned}

\alpha(v) = ... &=v^1\alpha(e_1)+v^2\alpha(e_2) \\

&= \epsilon^1(v)\alpha(e_1)+\epsilon^2(v)\alpha(e_2)

\end{aligned}$$
now we give names to the coefficients: $\alpha_i := \alpha(e_i)$ and get
$$\begin{aligned}

\alpha(v) &= \alpha_1 \epsilon^1(v)+\alpha_2 \epsilon^2(v)\\

\implies \alpha &= \alpha_1 \epsilon^1 +\alpha_2 \epsilon^2

\end{aligned}$$
which means, that $\epsilon^i$ are indeed a basis of $V^*$ ("dual basis"), and $\alpha_i=\alpha(e_i)$ are the components.


## Transformation of vectors/covectors
Overview: "from old to new basis"
$$\begin{aligned}
    \text{Basis vectors }\qquad \tilde e_j &= {F^i}_j e_i \qquad \text{co-variant}\\
    \text{Vector comp.}\qquad \tilde v^i &= {B^i}_j v^j\qquad \text{contra-variant}\\
    \text{Basis covectors }\qquad \tilde \epsilon^i&={B^i}_j\epsilon^j\qquad \text{contra-variant}\\
    \text{Covector comp.}\qquad \tilde \alpha_j &= {F^i}_j \alpha_i \qquad \text{co-variant}
\end{aligned}$$
and "from new to old basis":
$$\begin{aligned}
    \text{Basis vectors }\qquad  e_j &= {B^i}_j \tilde e_i \qquad \text{co-variant}\\
    \text{Vector comp.}\qquad  v^i &= {F^i}_j \tilde v^j\qquad \text{contra-variant}\\
    \text{Basis covectors }\qquad  \epsilon^i&={F^i}_j\tilde\epsilon^j\qquad \text{contra-variant}\\
    \text{Covector comp.}\qquad  \alpha_j &= {B^i}_j \tilde\alpha_i \qquad \text{co-variant}
\end{aligned}$$
Compare this with [[Transformation matrices, linear maps]].


## Transformation using matrices/Array shape:
- Basis vectors and covector comp. are collected in row vectors, 
$$\begin{aligned}
    \begin{pmatrix}\tilde e_1&\tilde e_2\end{pmatrix} &= \begin{pmatrix}e_1&e_2\end{pmatrix} \cdot F\\
    \begin{pmatrix}\tilde\alpha_1&\tilde\alpha_2\end{pmatrix}&=\begin{pmatrix}\alpha_1&\alpha_2\end{pmatrix} \cdot F
\end{aligned}$$

- vector comp. and basis covectors, are collected in column vectors.
$$\begin{aligned}
    \begin{pmatrix}\tilde v^1\\\tilde v^2\end{pmatrix}&=B\cdot \begin{pmatrix}v^1\\v^2\end{pmatrix}\\
    \begin{pmatrix}\tilde \epsilon^1\\\tilde \epsilon^2\end{pmatrix} &= B\cdot \begin{pmatrix}\epsilon^1\\\epsilon^2\end{pmatrix}
\end{aligned}$$

But: 
- the component representation (=coordinate vectors) of basis vectors are column vectors! $v = v^i e_i =\begin{pmatrix}e_1 & e_2\end{pmatrix} \begin{pmatrix}v^1\\v^2\end{pmatrix}= v^1 \begin{pmatrix}\cdot \\ \cdot \end{pmatrix}+v^2 \begin{pmatrix}\cdot \\ \cdot \end{pmatrix}$
- and the component representation of basis covectors are row vectors! $\alpha = \alpha_i \epsilon^i = \begin{pmatrix}\alpha_1&\alpha_2\end{pmatrix} \begin{pmatrix}\epsilon^1\\ \epsilon^2\end{pmatrix}= \alpha_1  \begin{pmatrix}\cdot & \cdot \end{pmatrix} + \alpha_2 \begin{pmatrix}\cdot & \cdot \end{pmatrix}$


## Source:
Eigenchris playlist on Tensor algebra: https://www.youtube.com/playlist?list=PLJHszsWbB6hrkmmq57lX8BV-o-YIOFsiG, videos 0-6