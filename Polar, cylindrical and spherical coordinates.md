these are examples of [[Curvilinear and generalized coordinates]]


## Polar coordinates
In the 2D plane, we can describe the point $\boldsymbol{r}$ using polar coordinates
$$
    \left ( \rho,\phi \right )^\intercal\equiv \boldsymbol{y}
$$
($\rho$... distance to origin, $\phi$... angle to $\boldsymbol{e}_x$).

Transformation from Cartesian to polar = expressing Cartesian through polar:
$$
    \boldsymbol{y}: U\to U_C, \quad \boldsymbol{y}\mapsto \boldsymbol{x}(\boldsymbol{y}) = \begin{pmatrix} x(\boldsymbol{y})\\ y(\boldsymbol{y}) \end{pmatrix} = \begin{pmatrix} \rho \cos \phi \\\rho \sin \phi \end{pmatrix}
$$
The inverse transformation from polar to Cartesian is:
$$
    \boldsymbol{y}: U_C\to U, \quad \boldsymbol{x}\mapsto \boldsymbol{y}(\boldsymbol{x}) =  \begin{pmatrix}\rho(\boldsymbol{x})\\ \phi (\boldsymbol{x})\end{pmatrix} = \begin{pmatrix}\sqrt{x^2+y^2}\\\arctan(y/x) \end{pmatrix}    
$$
The polar coordinate basis:
$$\begin{aligned}
    \boldsymbol{v}_\rho &= \boldsymbol{e}_x \cos \phi + \boldsymbol{e}_y \sin \phi\\
    \boldsymbol{v}_\phi &= \boldsymbol{e}_x (-\rho \sin\phi)+ \boldsymbol{e}_y \rho \cos \phi
\end{aligned}$$
The polar coordinate [[Metric tensor]]:
$$
    g_{\rho\rho} = 1,\quad g_{\phi\phi} = \rho^2, \quad g_{\phi,\rho} = 0  \hspace{2cm} \text{it is orthogonal}
$$
The polar local basis:
$$\begin{aligned}
    \boldsymbol{e}_\rho &= \boldsymbol{v}_\rho = \boldsymbol{e}_x \cos \phi + \boldsymbol{e}_y \sin \phi\\
    \boldsymbol{e}_\phi &= \frac{1}{\rho} \boldsymbol{v}_\phi = \boldsymbol{e}_x (- \sin\phi)+ \boldsymbol{e}_y  \cos \phi
\end{aligned}$$

## Example: Motion along curve in polar local basis vs coordinate basis
Motion along a curve (see [[Curves]]) parametrized by $\boldsymbol{r}(t)$ in various coordinates:
$$
    \boldsymbol{r}(t) = \boldsymbol{e}_x x(t) + \boldsymbol{e}_y y(t) = \boldsymbol{e}_\rho \rho(t) = \boldsymbol{v}_\rho \rho(t)
$$
Curve velocity:
$$\begin{aligned}
    \boldsymbol{v}=\partial_t \boldsymbol{r} \equiv \boldsymbol{\dot r} &=  \boldsymbol{e}_\rho \dot \rho + \boldsymbol{\dot e}_\rho \rho\\
    &=\boldsymbol{v}_\rho \dot \rho + \boldsymbol{\dot v}_\rho \rho
\end{aligned}$$
$\boldsymbol{e}_\rho, \boldsymbol{v}_\rho$ depend on $\boldsymbol{r}(t)$. Chain rule and the local basis definition give
$$\begin{aligned}
    \boldsymbol{\dot e}_\rho &= \partial_\rho \boldsymbol{e}_\rho \dot \rho+\partial_\phi \boldsymbol{e}_\rho \dot \phi =  \boldsymbol{e}_\phi \dot\phi\\
    \boldsymbol{\dot v}_\rho &= \partial_\rho \boldsymbol{v}_\rho \dot\rho + \partial_\phi \boldsymbol{v}_\rho \dot\phi = \frac{1}{\rho}\boldsymbol{v}_\phi \dot\phi
\end{aligned}$$
Local basis and coordinate basis are: 
$$\begin{aligned}
    \boldsymbol{v}&= \boldsymbol{\dot r} = \boldsymbol{e}_\rho \dot \rho + \boldsymbol{e}_\phi \rho \dot\phi \\
    \boldsymbol{v}&= \boldsymbol{\dot r} = \boldsymbol{v}_\rho \dot \rho + \boldsymbol{v}_\phi \dot \phi
\end{aligned}$$ 
The coordinate basis representation is simpler, as $\boldsymbol{v}_\phi$ is scaled with $\rho$, which is more natural.



## Cylindrical coordinates
In the 3D space, we can describe the point $\boldsymbol{r}$ using:
$$
    \left ( \rho,\phi,z \right )^\intercal\equiv \boldsymbol{y}
$$
($\rho$... distance to origin, $\phi$... angle to $\boldsymbol{e}_x$, $z$... height).
Transformation from Cartesian to Cylindrical (expressing Cartesian through Cylindrical):
$$
    \boldsymbol{y}: U\to U_C, \quad \boldsymbol{y}\mapsto \boldsymbol{x}(\boldsymbol{y}) = \begin{pmatrix} x(\boldsymbol{y})\\ y(\boldsymbol{y}) \\z(\boldsymbol{y}) \end{pmatrix} = \begin{pmatrix} \rho \cos \phi \\\rho \sin \phi\\z \end{pmatrix}
$$
The inverse transformation from polar to Cartesian is:
$$
    \boldsymbol{y}: U_C\to U, \quad \boldsymbol{x}\mapsto \boldsymbol{y}(\boldsymbol{x}) =  \begin{pmatrix}\rho(\boldsymbol{x})\\ \phi (\boldsymbol{x}) \\z(\boldsymbol{x})\end{pmatrix} = \begin{pmatrix}\sqrt{x^2+y^2}\\\arctan(y/x) \\ z\end{pmatrix}    
$$

The coordinate basis, [[Metric tensor]], and local basis:
$$
\begin{aligned}
\mathbf{v}_\rho &=\mathbf{e}_x \cos \phi+\mathbf{e}_y \sin \phi 
                &g_{\rho \rho}&=1
                &\mathbf{e}_\rho&=\mathbf{v}_\rho \\
\mathbf{v}_\phi &=\rho\left(-\mathbf{e}_x \sin \phi+\mathbf{e}_y \cos \phi\right)
                &g_{\phi \phi}&=\rho^2
                &\mathbf{e}_\phi&=\frac{1}{\rho} \mathbf{v}_\phi \\
\mathbf{v}_z    &=\mathbf{e}_z
                &g_{z z}&=1
                &\mathbf{e}_z&=\mathbf{e}_z 
\end{aligned}
$$
Point $r$ in local cylindrical basis and its curve velocity:
$$\begin{aligned}
    \boldsymbol{r} &= \boldsymbol{e}_\rho \rho + \boldsymbol{e}_z z\\
    \boldsymbol{v} = \dot{\mathbf{r}} &= \mathbf{e}_\rho \dot{\rho}+\mathbf{e}_\phi \rho \dot{\phi}+\mathbf{e}_z \dot{z}
\end{aligned}$$


## Spherical coordinates
In the 3D space, we can describe the point $\boldsymbol{r}$ using:
$$
    \left ( r,\theta,\phi \right )^\intercal\equiv \boldsymbol{y}
$$
($r$... distance to origin, $\theta$... angle to $\boldsymbol{e}_x$, $\phi$... height).
Transformation from Cartesian to Cylindrical (expressing Cartesian through Cylindrical):
$$
    \boldsymbol{y}: U\to U_C, \quad \boldsymbol{y}\mapsto \boldsymbol{x}(\boldsymbol{y}) = \begin{pmatrix} x(\boldsymbol{y})\\ y(\boldsymbol{y}) \\ z(\boldsymbol{y}) \end{pmatrix} = \begin{pmatrix} r\sin \theta  \cos \phi \\ r \sin \theta \sin \phi \\ r \cos \phi \end{pmatrix}
$$
The inverse transformation from polar to Cartesian is:
$$
    \boldsymbol{y}: U_C\to U, \quad \boldsymbol{x}\mapsto \boldsymbol{y}(\boldsymbol{x}) = \begin{pmatrix} r(\boldsymbol{x})\\ \theta(\boldsymbol{x}) \\ \phi(\boldsymbol{x}) \end{pmatrix} = \begin{pmatrix}\sqrt{x^2+y^2+z^2}\\ \arccos (z/\sqrt{x^2+y^2+z^2}) \\ \arctan(y/x) \end{pmatrix}    
$$

The coordinate basis
$$
\begin{aligned}
\mathbf{v}_r&=\mathbf{e}_x \sin \theta \cos \phi+\mathbf{e}_y \sin \theta \sin \phi+\mathbf{e}_z \cos \theta  \\
\mathbf{v}_\theta&=r\left(\mathbf{e}_x \cos \theta \cos \phi+\mathbf{e}_y \cos \theta \sin \phi-\mathbf{e}_z \sin \theta\right) \\
\mathbf{v}_\phi &=r \sin \theta\left(-\mathbf{e}_x \sin \phi+\mathbf{e}_y \cos \phi\right) 
\end{aligned}
$$
[[Metric tensor]] and local basis:
$$\begin{aligned}
    g_{r r}&=1 & \mathbf{e}_r&=\mathbf{e}_r\\
      g_{\theta \theta}&=r^2 & \mathbf{e}_\theta &=\frac{1}{r} \mathbf{v}_\theta, \\
      g_{\phi \phi} &=r^2 \sin ^2 \theta & \mathbf{e}_\phi &=\frac{1}{r \sin \theta} \mathbf{v}_\phi
\end{aligned}$$
Point $r$ in local cylindrical basis and its curve velocity:
$$\begin{aligned}
    \mathbf{r} &= \mathbf{e}_r r \\
    \boldsymbol{v} = \dot{\mathbf{r}} &=\mathbf{e}_r \dot{r}+\mathbf{e}_\theta r \dot{\theta}+\mathbf{e}_\phi r \dot{\phi} \sin \theta
\end{aligned}$$




## Source:
Chapter V2 of Altland, Delft - Mathematics for Physicists