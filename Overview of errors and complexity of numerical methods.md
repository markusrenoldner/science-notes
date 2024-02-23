# Overview of errors and complexity of numerical methods

[[Numerical analysis]]


How to produce convergence plots: [[Linear, polynomial and exponential functions in log-log plots]]

## interpolation


| Method   | Construction       | Evaluation         |
| :--------- | -------------------- | -------------------- |
| Lagrange | $\mathcal{O}(n^2)$ | $\mathcal{O}(n^2)$ |
| Horner   | $\mathcal{O}(n^2)$ | $\mathcal{O}(n)$   |

Error:

$$
\vert f-p_m\vert \leq Ch^{m+1}

$$

## Integration

Gauss Quadrature is exact for $\mathcal{P}^{2n+1}$
Error:

$$
\left\lVert \int f - Q[f] \right\rVert  \leq 4\min_v \left\lVert f-v \right\rVert_\infty

$$

Trapezoidal rule is better for periodic functions.

## Solving linear systems


| Method        | Construction                  | Comment            |
| :------------ | ----------------------------- | ------------------ |
| LU            | $\mathcal{O}(\frac{2}{3}n^3)$ |  |
| Crout         | $\mathcal{O}(\frac{2}{3}n^3)$ |  |
| Cholesky      | $\mathcal{O}(\frac{1}{3}n^3)$ | if matrix spd |
| QR Housholder | $\mathcal{O}(\frac{4}{3}n^3)$ | but well conditioned |
| QR Givens     | $\mathcal{O}(\frac{8}{3}n^3)$ | "but touches only single points" |


