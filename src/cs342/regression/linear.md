# Linear Regression

Fits hyperplane defined by \\(h(\mathbf{X};\mathbf{w})=\mathbf{Xw}\\) to dataset

Does this by minimising loss/cost function \\(\mathcal{L(\mathbf{w})}\\)

## Least Squares

\begin{align}
    \mathcal{L}(\mathbf{w})&=\frac{1}{2}\parallel\mathbf{Xw}-\mathbf{y}\parallel^2\\\\
    \mathcal{L}'(\mathbf{w})&=\mathbf{X}^T\mathbf{Xw}-\mathbf{X}^T\mathbf{y}
\end{align}

When \\(\mathcal{L}'(\mathbf{w})=0\\)

\begin{align}
    \mathbf{X}^T\mathbf{Xw}-\mathbf{X}^T\mathbf{y}&=0\\\\
    \mathbf{X}^T\mathbf{Xw}&=\mathbf{X}^T\mathbf{y}\\\\
    \mathbf{w}&=(\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T\mathbf{y}
\end{align}