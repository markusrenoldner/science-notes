# Coordinate transformation of differential operator in 2D example


## Problem:
Given is a coord transformation in $\mathbb{R}^2$ :
$$s=\frac{1}{2}(x+y) \qquad t=\frac{1}{2}(x-y)$$
Transform the operator $L$ given as:
$$L\psi := \frac{\partial^2 \psi}{\partial x^2} - \frac{\partial^2 \psi}{\partial y^2} $$
to the new coordinates $s,t$ .



## Solution:

Operator:
$$
    L\phi\equiv \partial_{xx}\phi - \partial_{yy}\phi
$$
Change of variables:
$$\begin{aligned}
    s&= \frac{1}{2}(x+y), \hspace{1cm} x=s+t\\
    t&= \frac{1}{2}(x-y), \hspace{1cm} y=s-t
\end{aligned}$$
define
$$\begin{aligned}
    \tau:\mathbb{R}^2&\to\mathbb{R}^2\\
    \begin{pmatrix}s\\t\end{pmatrix}&\mapsto \begin{pmatrix}s+t\\s-t\end{pmatrix}=\begin{pmatrix}x\\y\end{pmatrix}
\end{aligned}$$
and
$$
    \tilde\phi(s,t) = \phi(\tau(s,t))
$$
Find: $\tilde L\tilde\phi = L\phi$

### Idea 1: Guess the operator

... by combining $\partial_s \tilde\phi$ and $\partial_t \tilde \phi$, in a smart way.
$$\begin{aligned}
    \partial_s \tilde \phi &= \partial_{\tau_1}\phi\cdot \partial_s \tau_1 +  \partial_{\tau_2} \phi\cdot\partial_s \tau_2\\
    \partial_t \tilde \phi &= ...\\
    \partial_{st}\tilde \phi &= ...
\end{aligned}$$
.. and find that
$$
    \partial_{s,t}\tilde\phi =\tilde L\tilde \phi
$$

### Idea 2: Construct the operator

define
$$\begin{aligned}
    \sigma\equiv \tau^{-1}:\mathbb{R}^2&\to\mathbb{R}^2\\
    \begin{pmatrix}x\\y\end{pmatrix}&\mapsto \begin{pmatrix}\frac{1}{2}(x+y)\\\frac{1}{2}(x-y)\end{pmatrix}=\begin{pmatrix}s\\ t\end{pmatrix}
\end{aligned}$$
and this time:
$$
    \tilde\phi(\sigma(x,y)) =\phi(x,y)
$$
Again, find $\tilde L\tilde\phi = L\phi$

Its easy now:
$$\begin{aligned}
    L\phi &= \partial_{xx} \phi - \partial_{yy} \phi \\
    &= \partial_{xx}\tilde \phi(\sigma) - \partial_{yy}\tilde \phi(\sigma)\\
    &= \partial_x \left ( \partial_{\sigma_1}\tilde \phi \partial_x \sigma_1+ \partial_{\sigma_2}\tilde \phi  \partial_x \sigma_2\right )
        - \partial_y \left ( \partial_{\sigma_1}\tilde \phi \partial_y \sigma_1+ \partial_{\sigma_2}\tilde \phi  \partial_y \sigma_2 \right )\\
    &= .... \\
    &= \frac{1}{4}\left ( \partial_{ss}\tilde \phi + 2\partial_{st}\tilde \phi + \partial_{tt}\tilde \phi \right ) 
    - \frac{1}{4}\left ( \partial_{ss}\tilde \phi - 2\partial_{st}\tilde \phi + \partial_{tt}\tilde \phi \right ) \\
    &= \partial_{st}\tilde\phi \\
    &= \tilde L \phi
\end{aligned}$$

## Source

This is homework example 4.2 from Prof. Faustmanns Applied Mathematics Foundations lecture at TU Wien 2021.


