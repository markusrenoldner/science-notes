# Leibnitz integral rule for higher dimensions

[[Vector analysis identities]]

We want to take (time-)derivatives of integrals over (time-)varying domains.
We apply multidimensional versions of the Leibnitz integral rule (="Parameterintegral").

## Surface integral

$$
\frac{d}{d t} \iint_{\Sigma(t)} \mathbf{F} \cdot d \mathbf{A}=\iint_{\Sigma(t)}\left(\partial_t\mathbf{F}+[\nabla \cdot \mathbf{F}] \mathbf{v}\right) \cdot d \mathbf{A}-\oint_{\partial \Sigma(t)}[\mathbf{v} \times \mathbf{F}] \cdot d \mathbf{s}
$$
where:
- $\Sigma\subseteq\mathbb{R}^2$ is a surface 
- $\partial \Sigma$ is the boundary of $\Sigma$ and it is a closed curve,
- $\mathbf{v}$ is the (Eulerian) velocity of movement of the region $\Sigma$ (NOT NECESSARILY THE "MATERIAL VELOCITY!!")
- $\nabla \cdot$ is the vector divergence,


## Volume integral ("Reynolds transport theorem")

$$
\frac{d}{d t} \int_{D(t)} F d V=\int_{D(t)} \partial t F d V+\int_{\partial D(t)} F \mathbf{v} \cdot d \mathbf{A}
$$
where:
- $F$ is a scalar function
- $D(t)\subseteq \mathbb{R}^3$ and $\partial D(t)$ denote a time-varying connected region and its boundary, respectively, 
- $\mathbf{v}$ is the (Eulerian) velocity of the boundary (NOT NECESSARILY THE "MATERIAL VELOCITY!!")


## Source:
https://en.wikipedia.org/wiki/Leibniz_integral_rule#Higher_dimensions