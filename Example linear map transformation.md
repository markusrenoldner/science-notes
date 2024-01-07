# Example linear map transformation

Given three bases:
$$
    E=\left \{ e_1,e_2 \right \}, \quad B=\left \{ \begin{pmatrix}1\\1\end{pmatrix}, \begin{pmatrix}1\\0\end{pmatrix}  \right \}, \quad C=\left \{ \begin{pmatrix}4\\7\end{pmatrix}, \begin{pmatrix}4\\8\end{pmatrix} \right \}
$$

and the following linear map $L$ and vector $v$, represented in $E$:
$$
    L_E=\begin{pmatrix}1&2\\3&-1\end{pmatrix},\quad v_E=\begin{pmatrix}8\\15\end{pmatrix}, \quad L(v) = L_E v_E = \begin{pmatrix}38\\9\end{pmatrix}
$$

Find $L_B$, and $L_C$, v_B, and v_C, and L(v) in these bases.

1. $b_i=e_j {F^j}_i$
$(b_1,b_2)=(e_1,e_2)\cdot F_B \implies F_B=\begin{pmatrix}1&1\\1&0\end{pmatrix}, \quad B_B=F^{-1}=\begin{pmatrix}0&1\\1&-1\end{pmatrix}$
Then we get $L_B = B_B L_E F_B = \begin{pmatrix}2&3\\1&-2\end{pmatrix},\quad L_B v_B = \begin{pmatrix}9\\29\end{pmatrix}$ 
Check: $F_B L_B v_B = \begin{pmatrix}38\\9\end{pmatrix} \equiv L_E v_E$

2. $c_i=e_j {F^j}_i$
$(c_1, c_2) = (e_1,e_2)\cdot F_C \implies F_C= \begin{pmatrix}4&4\\7&8\end{pmatrix}, B_C=\begin{pmatrix}2&-1\\-7/4&1\end{pmatrix}$
Then we get $L_C=B_C L_E F_C=\begin{pmatrix}31&36\\-53/2 & -31\end{pmatrix},\quad L_C v_C = \begin{pmatrix}67\\-115/2\end{pmatrix}$ 
Check: $F_C L_C v_C = \begin{pmatrix}38\\9\end{pmatrix}\equiv L_E v_E$

3. Extra problem: Find $L_C$ from $L_B$
$c_i=b_j {F^j}_i$
$(c_1, c_2)=(b_1,b_2)\cdot F_X \implies F_X=\begin{pmatrix}7&8\\-3&-4\end{pmatrix}, \quad B_X=\begin{pmatrix}1&2\\-3/4&-7/4\end{pmatrix}$
Then we get $L_C = B_X L_B F_X=\begin{pmatrix}31&36\\-53/2&-31\end{pmatrix}$
Or alternatively as a check:
$L_C=B_C L_E F_C = B_C(F_B L_B B_B) F_C = (B_C F_B) L_B (F_B F_C) \equiv B_X L_B F_X$


