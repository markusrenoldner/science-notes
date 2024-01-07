# Boundary conditions of linear systems
[[Numerical analysis]]


consider linear system of equations written as a matrix equation:
$$A\cdot \vec{u} = \vec{f}$$
where some values of $\vec{x}$ are fixed, and some are unknown:
$u_f$ ... free/unknown entries of u
$u_D$ ... dirichlet/fixed entries
$g$ ... values of $u_D$, that have to be enforced 


## Basic option 1: "the large system"
correct $\vec{f}$ and $A$ such that the equations for the values $u_D$ just state: $u_D=g$, without removing values from the vector $\vec{u}$

Each ROW of $A$ corresponding to an entry of $u_D$ is being deleted except for the diagonal element (which is set 1).

In $\vec{f}$, one has to add $g$ at the right locations. For every ROW/equation where an entry is deleted, $g$ has to be subtracted from $\vec{f}$ in this ROW.

This is probably easier to implement.

For example, for the FD/FEM approximation of $\Delta u = f$ :
$$\frac{1}{\Delta x^2}\begin{pmatrix}
1 &  & & & & \\ 
1 & -2 &1 & & &\\ 
& 1 &-2 &1 & &\\ 
&  & &... && \\ 
&  & & &...& \\
&  & & 1&-2&1 \\
 &  & & &&1 
\end{pmatrix} \cdot
 \begin{pmatrix} 
u_0 \\
u_1 \\
u_2 \\
...\\
...\\
u_n \\
u_{n+1}
\end{pmatrix} = \begin{pmatrix} 
\frac{g_0}{\Delta x^2}\\
f_1\\
f_2 \\
...\\
...\\
f_n\\
\frac{g_{n+1}}{\Delta x^2}
\end{pmatrix}$$
or for boundary values at a different location (ignoring the $\Delta x$)
$$\begin{pmatrix}
... &   &   &   &   &   &  \\
1   &-2 &1  &   &   &   &  \\ 
    & 1 &-2 & 1 &   &   &  \\ 
    &   & \textcolor{red}{0} & \textcolor{red}{1} &\textcolor{red}{0}  &   &  \\
    &   &   & 1 &-2 & 1 &  \\
    &   &   &   &1  &-2 & 1\\
    &   &   &   &   &   &... 
\end{pmatrix} \cdot
\begin{pmatrix} 
... \\
u_1 \\
u_2 \\
u_3\\
u_4\\
u_5 \\
...
\end{pmatrix} = \begin{pmatrix} 
... \\
f_1 \\
f_2 \\
\textcolor{red}{g}   \\
f_4 \\
f_5 \\
...
\end{pmatrix}$$
This is relatively simple to implement.

## Basic option 2: "the reduced system"
removing values from $\vec{u}$ and add them to $\vec{f}$

The benefit is, the system is smaller, but its more difficult to implement, as one has to remove the values $u_D$ from the unknown vector (i.e. $g$) and add them to ALL (!) entries of $\vec{f}$ corresponding to values from $u_f$ that depend on the respective entry of $u_D$.

again, the example $\Delta u = f$
$$\frac{1}{\Delta x^2}\begin{pmatrix}
-2 & 1 & & & \\
1 & -2 &1 & & \\ 
&  &... & & \\ 
&  & 1& -2&1 \\ 
&  & & 1&-2 
\end{pmatrix} \cdot
 \begin{pmatrix} 
u_1 \\
u_2 \\
...\\
...\\
u_n
\end{pmatrix} = \begin{pmatrix} 
f_1 -\frac{g_{0}}{\Delta x^2}\\
f_2 \\
...\\
...\\
f_n-\frac{g_{n+1}}{\Delta x^2}
\end{pmatrix}$$
Here this is easy, as only $u_1$ and $u_n$ depend on boundary values!
In general, this can be annoying to implement.


## Comparison of 1 and 2 
#pdf-note [[BCoflinearsystems.pdf]]


## Option by MFEM: "the large, symmetric system"
the command
```
a.FormLinearSystem(essdof, b, x, A, B, X) 
```
actually enforces a symmetric matrix, so the following happens (ignoring the $\Delta x$ - scaling):
$$\begin{pmatrix}
    ... &   &   &   &   &   &  \\
    1   &-2 &1  &   &   &   &  \\ 
        & 1 &-2 & \textcolor{red}{0} &   &   &  \\ 
        &   & \textcolor{red}{0} & \textcolor{red}{1} &\textcolor{red}{0}  &   &  \\
        &   &   & \textcolor{red}{0} &-2 & 1 &  \\
        &   &   &   &1  &-2 & 1\\
        &   &   &   &   &   &... 
    \end{pmatrix} \cdot
    \begin{pmatrix} 
    ... \\
    u_1 \\
    u_2 \\
    u_3\\
    u_4\\
    u_5 \\
    ...
    \end{pmatrix} = \begin{pmatrix} 
    ... \\
    f_1 \\
    f_2 - \textcolor{red}{g}\\
    \textcolor{red}{g}   \\
    f_4 - \textcolor{red}{g}\\
    f_5 \\
    ...
    \end{pmatrix}$$
summary: not only each ROW, but also each COLUMN corresponding to an entry of essdof is being deleted except for the diagonal element. Every ROW/equation where an entry is deleted results in the subtraction of the boundary value in this ROW at the right hand side vector.

>MFEM implements the larger system, except the off-diagonal entries in the columns associated with the essential BCs are also set to zero (so that the matrix is symmetric), requiring that the right-hand side be modified [...]

See discussion here: https://github.com/orgs/mfem/discussions/3431

In general, this can be annoying to implement, but MFEM does it automatically.
Careful with problems involving multiple unknowns, i.e. $\vec{u} = (\vec{v},\vec{w})$, this can "destroy" the matrix.


## Option by ngsolve and LehrFEM: "the large, reordered system"

Another option is to reorder all equations (and therefore the entries of $\vec{u}$) and then apply Option 1. This way, the matrix looks like this:
$$\begin{pmatrix} I & 0 \\ A_{fD} & A_{ff} \end{pmatrix} \cdot\begin{pmatrix} u_D \\ u_f \end{pmatrix} = \begin{pmatrix} g \\ f\end{pmatrix}$$
where $A_{fD}$ describes how the boundary values influence the free/unknown values of $u$ and $A_{ff}$ describe the dependence of free/unknown values among each other.

(optionally, this can then be reformulated to $A_{ff} u_f = f_f − A_{fD}u_D$, to get a smaller system again)

In general, the reordering can be annoying to implement, but it also works for systems with multiple unknowns.


## Option used in my master thesis: "the large system revisited"
A slightly different variation of the previous method is to first implement the large system (i.e. including the fixed values $u_D$):
$$A u = f$$
then we add equations for the boundary values 
$$\begin{pmatrix}  A \\ A_{D} \end{pmatrix} \cdot \vec{u} = \begin{pmatrix} f \\ g\end{pmatrix}$$
such that $A_D$ only fixes the values $u_D$ to be $g$. The problem now is that $u_D$ is overdetermined, so now we remove the equations corresponding to $u_D$ from $A$. That means, the rows of $A$ and the rows of $f$ corresponding to an entry of $u_D$ will be set to 0. This results in
$$\begin{pmatrix}  A_{f} \\ A_{D} \end{pmatrix} \cdot \vec{u} = \begin{pmatrix} f_f \\ g\end{pmatrix}$$
The system is still rectangular. If this needs to be fixed, one can simply multiply by the transposed of the matrix:
$$\begin{aligned}\begin{pmatrix}  A_{f}^\intercal & A_{D}^\intercal \end{pmatrix} \cdot \begin{pmatrix}  A_{f} \\ A_{D} \end{pmatrix} \cdot \vec{u} = \begin{pmatrix}  A_{f}^\intercal & A_{D}^\intercal \end{pmatrix} \cdot \begin{pmatrix} f_f \\ g\end{pmatrix} \end{aligned}$$
The benefit is, that one doesnt have to reorder $u$. Removing rows/entries from $A_f$ and $f_f$ is rather simple. The result of $A_D$ is something like this:
$$A_D=\begin{pmatrix}
     1  & 0 & 0 & 0 & 0 & 0 &0 &... \\
     0  & 1 & 0 & 0 & 0 & 0 &0 &...\\ 
     0  & 0 & \textcolor{red}{0} & \textcolor{red}{0} & 1 & 0 & 0 &... \\ 
     0  & 0 & 0 & 0 & 0 & \textcolor{red}{0} & 1&...\\
     0  & 0 & 0 & 0 & 0 & 0 & 0&...\\
\end{pmatrix}$$
this matrix results in $u_f=(u_3,u_4,u_6)$ and  $u_D=(u_1,u_2,u_5,u_7)$.

This method is very similar to basic option 1, "the large system", only it works better for problems with multiple unknowns, i.e.: $\vec{u} = (\vec{v},\vec{w})$.
If e.g. we need to fix $v_3$ and $w_3$, then "the large system" is very annoying to implement.





