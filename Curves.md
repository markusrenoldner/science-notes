necessary do define [[Curvilinear and generalized coordinates]], and to compute line integrals, see [[Multidimensional integration]]

## Definition and parametrization

a curve $\gamma$ is a smooth line in d-dimensional space. It is the image of a vector-valued function
$$
    \gamma \equiv \{\boldsymbol{r}(t): t\in I\}
$$
which is given as
$$
    \boldsymbol{r} :I\to \mathbb{R}^d, \quad t\mapsto \boldsymbol{r}(t).
$$
This function is a (1 of infinitely many) parametrization of the curve, which not only discribes the shape but also how "fast" the point $\boldsymbol{r}$ moves with the parameter $t$.
Example: unit circle
$$
    \boldsymbol{r}(t) = \begin{pmatrix}\cos (2\pi t)\\ \sin(2\pi t)\end{pmatrix},\quad t\in [0,1)
$$

## Curve velocity and acceleration
(depends on the parametrization) is defined as
$$
    \boldsymbol{v}(t) = \lim_{h \to 0} \frac{\boldsymbol{r}(t+h)-\boldsymbol{r}(t)}{h} \equiv \frac{d \boldsymbol{r}}{dt}
$$ 
it is tangential to the curve $\gamma$, because for small $h$, the line $\boldsymbol{r}(t) + h \boldsymbol{v}(t)$ is a good approximation to the curve close to $\boldsymbol{r}(t)$:
$$
    \boldsymbol{r}(t+h) \approx \boldsymbol{r}(t) + h \boldsymbol{v}(t)
$$

Curve acceleration (depends on param.)
$$
    \boldsymbol{a}(t) = \lim_{h \to 0} \frac{\boldsymbol{v}(t+h)-\boldsymbol{v}(t)}{h} \equiv \frac{d \boldsymbol{v}}{dt}
$$

## Curve length and natural parametrization
(equal for any parametrization)
by constructing a Rieman sum, one gets:
$$
    L[\gamma] = \int_I \left\Vert \boldsymbol{v}(t) \right\Vert dt
$$

Natural parametrization
... is a parametrization with curve velocity $1$. Can be constructed by defining a the length of the curve from $0$ to $t$:
$$
    s(t) = \int_0^t \Vert \boldsymbol{v}(u) \Vert du
$$
it is a bijection, the inverse exists. We can parametrize the curve by its length function $s$:
$$
    \boldsymbol{r}_L: (0,L)\to \mathbb{R}^d,\quad s\mapsto \boldsymbol{t}_L(s)\equiv \boldsymbol{r}(t(s))
$$



## Line integrals
similarly as the length intregral $L[\gamma]$ of a curve, we define the "line integral" of a vector field $\boldsymbol{F}$ along $\gamma$: 
$$
    \int_I \boldsymbol{v}(t)\cdot \boldsymbol{F}(\boldsymbol{r}(t)) dt \equiv \int_\gamma \boldsymbol{F}\cdot d \boldsymbol{r},
$$
where the second term is only a symbolic notation.
The integral has the same value for any parametrization.

Example: computing the work necessary to move an object through a force field along a curve.


## Source:
Chapter V1 of Altland, Delft - Mathematics for Physicists