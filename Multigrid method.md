
# Multigrid method


## Main idea

We want to solve the matrix system $$Ax = b.$$ 
with an initial guess $x^0$.

Iterative methods (e.g. Gauss-Seidel) provide smoothing of the local error. This means they filter out high-frequency oscillations of the local error. But they converge slowly, as boundary information takes long time to propagate from boundary

The idea behind multigrid methods is that a slowly converging low-frequ error on a fine grid is a faster converging high-frequ error on a coarse grid.

## Algorithm

Correction $\Delta x^k$ from $k$-th solution update $x^k$ to true discrete sol $x$  defined as 
$$\Delta x^k \equiv x -x^k.$$

From this we define the residual $r^k$
$$A\Delta x^k =A(x -x^k) = Ax-Ax^k = b - Ax^k\equiv -r^k$$

Now define two operators:
$$\begin{aligned}
    I_{res} &\quad... \text{restriction to coarse grid}\\
    I_{pro} &\quad...\text{interp./prolongation two fine grid}
\end{aligned}$$



Two level scheme:

1. on fine grid, compute $x^{k,f}$ using $k$ iterations. This is called "smoothing" on wikipedia, as it already reduces some high-frequ. oscillations of the numeric error. Apparently this works, as Gauss-Seidel uses the most recent available update $k$ of all components $x^{k,f}_i$ for $i\neq j$ to compute a component $x_j^{k,f}$. 
2. compute residual $r^{k,f}=Ax^{k,f}-b$ on fine grid
3. restrict $r^{k,f}$ to coarse grid $r^{k,c} = I_{res}[r^{k,f}]$, e.g. by only taking every other point. (This is somehow filtering high-frequency errors, so that we only have low-frequency errors left. Makes sense intuitively, we cant represent high-frequency oscillations on a coarse grid, as coarse grids dont have enough grid points.)
4. on coarse grid, compute $\Delta x^{k,c}$ based on $A\Delta x^{k,c} = -r^{k,c}$ using $k$ iterations. Starting value $\Delta x^0 = 0$.
5. interpolate $\Delta x^{k,c}$ to fine grid $\Delta x^{k,f}=I_{pro}[\Delta x^{k,c}]$
6. correct the sol on fine grid using $x^{k,f} \leftarrow x^{k,f} + \Delta x^{k,f}$ and go to step 1.

At the end of step 1 convergence is checked!

The work of the multigrid method is estimated to be $\mathcal{O} (N log N)$!


## Interpretation of algorithm and connection to main idea

The error, which converges slowly on the fine grid, converges faster when transferred to the coarse grid. By iteratively solving for $\Delta x^{k,c}$ on the coarser grid (step 4), we efficiently handle the low-frequency, making it a high-frequency error on the coarse grid.

## Source

- Prof. Henning, KTH lecture on CFD, Appendix A, section A1
- [wikipedia multigrid methods](https://en.wikipedia.org/wiki/Multigrid_method)

