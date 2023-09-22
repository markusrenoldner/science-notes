fundamental idea of [[Tensor and vector analysis]]

Goal: describe physical systems in a language reflecting the symmtry of the problem.

## Cartesian coordinates
If $\left \{ \boldsymbol{e}_x, \boldsymbol{e}_y \right \}$ is a fixed, orthonormal basis and if we can describe a point $\boldsymbol{r}\in M$ like this: $$\begin{equation}
    \boldsymbol{r} = \boldsymbol{e}_x x + \boldsymbol{e}_y y, 
\end{equation}$$  then we call $\left ( x,y \right )^\intercal\equiv \boldsymbol{x}$ Cartesian coordinates, always denoted as "$\boldsymbol{x}$".


## Coordinate basis and local basis
Define coordinate map (invertible):
$$\begin{equation}
    \boldsymbol{r}:U\to M, \quad \boldsymbol{y}\mapsto \boldsymbol{r}(\boldsymbol{y}) \equiv \boldsymbol{r}(y^1, ..., y^d)
\end{equation}$$
where $\boldsymbol{y}$ are generalized/curvilinear coordinates. The map defines a system of such coordinates. The coordinate domain is $U\subset \mathbb{R}^d$.

$M$ is embedded in a d-dim. vector space and has an orthonormal basis, and $\boldsymbol{r}$ can be expanded as$$\begin{equation}
    \boldsymbol{r}(\boldsymbol{y}) = \boldsymbol{e}_a x^a \hspace{2cm} \substack{\text{index a for Cartesian} \\ \text{index j for curvilinear}}
\end{equation}$$ and represented by the Cartesian coordinate/componet vector:
$$\begin{equation}
    \boldsymbol{x}(\boldsymbol{y}) = \begin{pmatrix} x^1(\boldsymbol{y}), ... x^d(\boldsymbol{y})\end{pmatrix}^\intercal
\end{equation}$$
Define the $j$-th coordinate line:
$$\begin{align}
    \boldsymbol{r}_j :I_j &\to M\\
    y &\mapsto \boldsymbol{r}_j (y)\equiv \boldsymbol{r}(y^1, ... y, ...y^d) \hspace{2cm} \substack{\text{index j for curvilinear} \\ \text{$y$ takes place of $y^j$}}
\end{align}$$
Curve velocity of j-th coordinate line, see [[Curves]]:
$$\begin{equation}
    \boldsymbol{v}_{j} \equiv \frac{d}{dy} \boldsymbol{r}_j = \frac{d}{dy^j} \boldsymbol{r}(\boldsymbol{y})   \hspace{2cm}\text{depends on r!}
\end{equation}$$
Coordinate basis:
- the coordinate map $\boldsymbol{y}\mapsto \boldsymbol{r}(\boldsymbol{y})$ is invertible
- the $\boldsymbol{v}_{j}$ are lin. indep. and form a basis of $\mathbb{R}^d$
They define the coordinate basis of the $\boldsymbol{y}$-coordinates. Represented in Cartesian coordinates:
$$\begin{equation}
    \boldsymbol{v}_j (\boldsymbol{y}) = \boldsymbol{e}_a \frac{\partial x^a (\boldsymbol{y})}{\partial y^j}   \hspace{2cm} \substack{\text{depends on y and r} \\ \text{generally not orthonormal}}
\end{equation}$$
The [[Metric tensor]] describes the geometric relation between the $\boldsymbol{v}_j$:
$$\begin{equation}
    g_{ij}\equiv \boldsymbol{v}_i \cdot \boldsymbol{v}_j \equiv \left \langle \boldsymbol{v}_i , \boldsymbol{v}_j \right \rangle \hspace{2cm} \text{...standard scalar product in $\mathbb{R}^d$}
\end{equation}$$
In physics, its common to normalize the coordinate basis which yields the so called local basis:
$$\begin{equation}
    \boldsymbol{e}_j \equiv \frac{\boldsymbol{v}_j}{\Vert \boldsymbol{v}_j \Vert} = \frac{\boldsymbol{v}_j}{\sqrt{g_{jj}}} \hspace{2cm} \text{depends on y/r} 
\end{equation}$$

## Coordinates
We have introduced curvilinear coordinate systems as maps. The inverse assigns to each point in $M$ its coordinates. 
![[general-coordinate-maps.png]]
For example, $\mathbf{y}(\mathbf{r})=(\rho, \phi)^{\intercal}$ might be polar coordinates and $\mathbf{y}^{\prime}(\mathbf{r}) \equiv \mathbf{x}(\mathbf{r})$ Cartesian coordinates of a point $\mathbf{r}$, see [[Polar, cylindrical and spherical coordinates]].

To each $\mathbf{y}^{\prime}$ we can now assign $\mathbf{y}\left(\mathbf{y}^{\prime}\right)$, defined such that they represent the same point: $$\mathbf{r}\left(\mathbf{y}^{\prime}\right)=\mathbf{r}\left(\mathbf{y}\left(\mathbf{y}^{\prime}\right)\right)$$ This correspondence between coordinates is described by a coordinate transformation $$\mathbf{y}: U^{\prime} \rightarrow U,\quad \mathbf{y}^{\prime} \mapsto \mathbf{y}\left(\mathbf{y}^{\prime}\right)$$, a map between the coordinate domains. The image $\mathbf{y}\left(\mathbf{y}^{\prime}\right)$ is obtained by computing the $\mathbf{y}$-coordinates, $\mathbf{y}\left(\mathbf{r}\left(\mathbf{y}^{\prime}\right)\right)$, similar like in [[Change of basis in linear algebra]].

Concrete mathematical calculations (differentiation, integration, etc.) are always performed in a specific coordinate system, never using the abstract object $\boldsymbol{r}\in M$, where $M$ is embedded in a vector space. 
Always distinguish between $\boldsymbol{r}\in M$ and its coordinate representation, e.g. $\boldsymbol{y}(\boldsymbol{r})\in U \subset \mathbb{R}^d$!


## Linear algebra perspective
#todo 


## Source:
Chapter V2 of Altland, Delft - Mathematics for Physicists