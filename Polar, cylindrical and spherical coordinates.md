these are examples of [[Curvilinear and generalized coordinates]]


## Polar coordinates
In the 2D plane, we can describe the point $\boldsymbol{r}$ using polar coordinates
$$\begin{equation}
    \left ( \rho,\phi \right )^\intercal\equiv \boldsymbol{y}
\end{equation}$$
($\rho$... distance to origin, $\phi$... angle to $\boldsymbol{e}_x$).

Transformation from Cartesian to polar = expressing Cartesian through polar:
$$\begin{equation}
    \boldsymbol{y}: U\to U_C, \quad \boldsymbol{y}\mapsto \boldsymbol{x}(\boldsymbol{y}) = \begin{pmatrix} x(\boldsymbol{y})\\ y(\boldsymbol{y}) \end{pmatrix} = \begin{pmatrix} \rho \cos \phi \\\rho \sin \phi \end{pmatrix}
\end{equation}$$
The inverse transformation from polar to Cartesian is:
$$\begin{equation}
    \boldsymbol{y}: U_C\to U, \quad \boldsymbol{x}\mapsto \boldsymbol{y}(\boldsymbol{x}) =  \begin{pmatrix}\rho(\boldsymbol{x})\\ \phi (\boldsymbol{x})\end{pmatrix} = \begin{pmatrix}\sqrt{x^2+y^2}\\\arctan(y/x) \end{pmatrix}    
\end{equation}$$
The polar coordinate basis:
$$\begin{align}
    \boldsymbol{v}_\rho &= \boldsymbol{e}_x \cos \phi + \boldsymbol{e}_y \sin \phi\\
    \boldsymbol{v}_\phi &= \boldsymbol{e}_x (-\rho \sin\phi)+ \boldsymbol{e}_y \rho \cos \phi
\end{align}$$
The polar coordinate [[Metric tensor]]:
$$\begin{equation}
    g_{\rho\rho} = 1,\quad g_{\phi\phi} = \rho^2, \quad g_{\phi,\rho} = 0  \hspace{2cm} \text{it is orthogonal}
\end{equation}$$
The polar local basis:
$$\begin{align}
    \boldsymbol{e}_\rho &= \boldsymbol{v}_\rho = \boldsymbol{e}_x \cos \phi + \boldsymbol{e}_y \sin \phi\\
    \boldsymbol{e}_\phi &= \frac{1}{\rho} \boldsymbol{v}_\phi = \boldsymbol{e}_x (- \sin\phi)+ \boldsymbol{e}_y  \cos \phi
\end{align}$$

## Example: Motion along curve in polar local basis vs coordinate basis
Motion along a curve (see [[Curves]]) parametrized by $\boldsymbol{r}(t)$ in various coordinates:
$$\begin{equation}
    \boldsymbol{r}(t) = \boldsymbol{e}_x x(t) + \boldsymbol{e}_y y(t) = \boldsymbol{e}_\rho \rho(t) = \boldsymbol{v}_\rho \rho(t)
\end{equation}$$
Curve velocity:
$$\begin{align}
    \boldsymbol{v}=\partial_t \boldsymbol{r} \equiv \boldsymbol{\dot r} &=  \boldsymbol{e}_\rho \dot \rho + \boldsymbol{\dot e}_\rho \rho\\
    &=\boldsymbol{v}_\rho \dot \rho + \boldsymbol{\dot v}_\rho \rho
\end{align}$$
$\boldsymbol{e}_\rho, \boldsymbol{v}_\rho$ depend on $\boldsymbol{r}(t)$. Chain rule and the local basis definition give
$$\begin{align}
    \boldsymbol{\dot e}_\rho &= \partial_\rho \boldsymbol{e}_\rho \dot \rho+\partial_\phi \boldsymbol{e}_\rho \dot \phi =  \boldsymbol{e}_\phi \dot\phi\\
    \boldsymbol{\dot v}_\rho &= \partial_\rho \boldsymbol{v}_\rho \dot\rho + \partial_\phi \boldsymbol{v}_\rho \dot\phi = \frac{1}{\rho}\boldsymbol{v}_\phi \dot\phi
\end{align}$$
Local basis and coordinate basis are: 
$$\begin{align}
    \boldsymbol{v}&= \boldsymbol{\dot r} = \boldsymbol{e}_\rho \dot \rho + \boldsymbol{e}_\phi \rho \dot\phi \\
    \boldsymbol{v}&= \boldsymbol{\dot r} = \boldsymbol{v}_\rho \dot \rho + \boldsymbol{v}_\phi \dot \phi
\end{align}$$ 
The coordinate basis representation is simpler, as $\boldsymbol{v}_\phi$ is scaled with $\rho$, which is more natural.



## Cylindrical coordinates
In the 3D space, we can describe the point $\boldsymbol{r}$ using:
$$\begin{equation}
    \left ( \rho,\phi,z \right )^\intercal\equiv \boldsymbol{y}
\end{equation}$$
($\rho$... distance to origin, $\phi$... angle to $\boldsymbol{e}_x$, $z$... height).
Transformation from Cartesian to Cylindrical (expressing Cartesian through Cylindrical):
$$\begin{equation}
    \boldsymbol{y}: U\to U_C, \quad \boldsymbol{y}\mapsto \boldsymbol{x}(\boldsymbol{y}) = \begin{pmatrix} x(\boldsymbol{y})\\ y(\boldsymbol{y}) \\z(\boldsymbol{y}) \end{pmatrix} = \begin{pmatrix} \rho \cos \phi \\\rho \sin \phi\\z \end{pmatrix}
\end{equation}$$
The inverse transformation from polar to Cartesian is:
$$\begin{equation}
    \boldsymbol{y}: U_C\to U, \quad \boldsymbol{x}\mapsto \boldsymbol{y}(\boldsymbol{x}) =  \begin{pmatrix}\rho(\boldsymbol{x})\\ \phi (\boldsymbol{x}) \\z(\boldsymbol{x})\end{pmatrix} = \begin{pmatrix}\sqrt{x^2+y^2}\\\arctan(y/x) \\ z\end{pmatrix}    
\end{equation}$$

The coordinate basis, [[Metric tensor]], and local basis:
$$
\begin{align}
\mathbf{v}_\rho &=\mathbf{e}_x \cos \phi+\mathbf{e}_y \sin \phi 
                &g_{\rho \rho}&=1
                &\mathbf{e}_\rho&=\mathbf{v}_\rho \\
\mathbf{v}_\phi &=\rho\left(-\mathbf{e}_x \sin \phi+\mathbf{e}_y \cos \phi\right)
                &g_{\phi \phi}&=\rho^2
                &\mathbf{e}_\phi&=\frac{1}{\rho} \mathbf{v}_\phi \\
\mathbf{v}_z    &=\mathbf{e}_z
                &g_{z z}&=1
                &\mathbf{e}_z&=\mathbf{e}_z 
\end{align}
$$
Point $r$ in local cylindrical basis and its curve velocity:
$$\begin{align}
    \boldsymbol{r} &= \boldsymbol{e}_\rho \rho + \boldsymbol{e}_z z\\
    \boldsymbol{v} = \dot{\mathbf{r}} &= \mathbf{e}_\rho \dot{\rho}+\mathbf{e}_\phi \rho \dot{\phi}+\mathbf{e}_z \dot{z}
\end{align}$$


## Spherical coordinates
In the 3D space, we can describe the point $\boldsymbol{r}$ using:
$$\begin{equation}
    \left ( r,\theta,\phi \right )^\intercal\equiv \boldsymbol{y}
\end{equation}$$
($r$... distance to origin, $\theta$... angle to $\boldsymbol{e}_x$, $\phi$... height).
Transformation from Cartesian to Cylindrical (expressing Cartesian through Cylindrical):
$$\begin{equation}
    \boldsymbol{y}: U\to U_C, \quad \boldsymbol{y}\mapsto \boldsymbol{x}(\boldsymbol{y}) = \begin{pmatrix} x(\boldsymbol{y})\\ y(\boldsymbol{y}) \\ z(\boldsymbol{y}) \end{pmatrix} = \begin{pmatrix} r\sin \theta  \cos \phi \\ r \sin \theta \sin \phi \\ r \cos \phi \end{pmatrix}
\end{equation}$$
The inverse transformation from polar to Cartesian is:
$$\begin{equation}
    \boldsymbol{y}: U_C\to U, \quad \boldsymbol{x}\mapsto \boldsymbol{y}(\boldsymbol{x}) = \begin{pmatrix} r(\boldsymbol{x})\\ \theta(\boldsymbol{x}) \\ \phi(\boldsymbol{x}) \end{pmatrix} = \begin{pmatrix}\sqrt{x^2+y^2+z^2}\\ \arccos (z/\sqrt{x^2+y^2+z^2}) \\ \arctan(y/x) \end{pmatrix}    
\end{equation}$$

The coordinate basis
$$
\begin{align}
\mathbf{v}_r&=\mathbf{e}_x \sin \theta \cos \phi+\mathbf{e}_y \sin \theta \sin \phi+\mathbf{e}_z \cos \theta  \\
\mathbf{v}_\theta&=r\left(\mathbf{e}_x \cos \theta \cos \phi+\mathbf{e}_y \cos \theta \sin \phi-\mathbf{e}_z \sin \theta\right) \\
\mathbf{v}_\phi &=r \sin \theta\left(-\mathbf{e}_x \sin \phi+\mathbf{e}_y \cos \phi\right) 
\end{align}
$$
[[Metric tensor]] and local basis:
$$\begin{align}
    g_{r r}&=1 & \mathbf{e}_r&=\mathbf{e}_r\\
      g_{\theta \theta}&=r^2 & \mathbf{e}_\theta &=\frac{1}{r} \mathbf{v}_\theta, \\
      g_{\phi \phi} &=r^2 \sin ^2 \theta & \mathbf{e}_\phi &=\frac{1}{r \sin \theta} \mathbf{v}_\phi
\end{align}$$
Point $r$ in local cylindrical basis and its curve velocity:
$$\begin{align}
    \mathbf{r} &= \mathbf{e}_r r \\
    \boldsymbol{v} = \dot{\mathbf{r}} &=\mathbf{e}_r \dot{r}+\mathbf{e}_\theta r \dot{\theta}+\mathbf{e}_\phi r \dot{\phi} \sin \theta
\end{align}$$




## Source:
Chapter V2 of Altland, Delft - Mathematics for Physicists