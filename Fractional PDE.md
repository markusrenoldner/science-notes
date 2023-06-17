are partial [[Differential equations]] involving differential operators with non-integer power.

Example: find $u$ st.
$$(-\Delta)^2 u = f, \quad s\in(0,1)$$
i.e. $s$ does not have to be an integer. How is this defined for $s$ not being an integer?
One possible definition is formulated as an integral operator.


## Fractional differential operators as integral operators
$$(-\Delta)^2 u(x):=C\int_{\mathbb{R}^d} \frac{u(x)-u(y)}{|x-y|^{d+2s}}dy$$
This is a nonlocal operator. The numerical approximation produces a dense matrix. Applications are in image compression and computational finance.
This problem can also be solved with [[Finite Element Method (FEM)]].


## Source:
- Prof. Faustmann
