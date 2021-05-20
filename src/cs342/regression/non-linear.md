# Introducing Non-Linearities

Used to model alternate dimensional interactions in training data

## Feature Transformation

Non-linearities can be introduced via a change of basis

\\[
    \mathbf{X}'=\begin{bmatrix}1&x_{11}&\dots&x_{1d}&x_{11}^2&\dots&x_{1d}^2\\\\\vdots&\vdots&\ddots&\vdots&\vdots&\ddots&\vdots\\\\1&x_{n1}&\dots&x_{nd}&x_{n1}^2&\dots&x_{nd}^2\end{bmatrix}
\\]

Predictions are made by transforming the data similarly

\\[
    \hat{y}=\mathbf{x}'\mathbf{w}
\\]

Can be extended to polynomial of degree \\(p\\)

\\[
    \mathbf{X}'=\begin{bmatrix}1&x_{11}&\dots&x_{1d}&x_{11}^2&\dots&x_{1d}^2&\dots&x_{11}^p&\dots&x_{1d}^p\\\\\vdots&\vdots&\ddots&\vdots&\vdots&\ddots&\vdots&\dots&\vdots&\ddots&\vdots\\\\1&x_{n1}&\dots&x_{nd}&x_{n1}^2&\dots&x_{nd}^2&\dots&x_{n1}^p&\dots&x_{nd}^p\end{bmatrix}
\\]

## High Degree Polynomials and Overfitting

As \\(p\\) increases, \\(E_{train}\\) decreases, but \\(E_{approx}\\) increases, i.e. \\(E_{test}\\) increases

We use validation/cross-validation to select \\(p\\)

Moreover, higher degree polynomials are sensitive to data

We use regularisation to minimise \\(\parallel W\parallel\\)