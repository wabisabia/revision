# Linear Regression

Fits hyperplane defined by \\(h(\mathbf{X};\mathbf{w})=\mathbf{Xw}\\) where

\\[
    \mathbf{w}=\begin{bmatrix}w_1\\\\\vdots\\\\w_{d+1}\end{bmatrix}
\\]

Goal: minimise loss/cost function \\(\mathcal{L(\mathbf{w})}\\)

## Bias Column

Model \\(y\\)-intercept by adding bias column

\\[
    \mathbf{X}'=\begin{bmatrix}1&x_{11}&\dots&x_1d\\\\\vdots&\vdots&\ddots&\vdots\\\\1&x_{n1}&\dots&x_{nd}\end{bmatrix}
\\]

## Least Squares

\begin{align}
    \mathcal{L}(\mathbf{w})&=\frac{1}{2}\parallel\mathbf{Xw}-\mathbf{y}\parallel^2\\\\
    \mathcal{L}'(\mathbf{w})&=\mathbf{X}^T\mathbf{Xw}-\mathbf{X}^T\mathbf{y}
\end{align}

When \\(\mathcal{L}'(\mathbf{W})=0\\)

\begin{align}
    \mathbf{X}^T\mathbf{Xw}-\mathbf{X}^T\mathbf{y}&=0\\\\
    \mathbf{X}^T\mathbf{Xw}&=\mathbf{X}^T\mathbf{y}\\\\
    \mathbf{w}&=(\mathbf{X}^T\mathbf{X})^{-1}\mathbf{X}^T\mathbf{y}
\end{align}

Predict with \\(\mathbf{w}\\)

\\[
    \hat{y}=\mathbf{xw}
\\]

### Issues

- Sensitive to outliers
- \\(\mathbf{X}^T\mathbf{X}\\) large
- Computationally expensive: \\(O(nd^2+d^3)\\)
    - Computing \\(\mathbf{X}^T\mathbf{X}\\) costs \\(O(dnd)=O(nd^2)\\)
    - Solving system of linear equations with \\(d\\) variables costs \\(O(d^3)\\)
- Can predict values outside range of \\(y\\)
- Assumes linear relationship between \\(\mathbf{X}\\) and \\(\mathbf{y}\\)
- Solution may not be unique, e.g. two features are *collinear*
    - Increasing and decreasing their weights respectively maintains predictions