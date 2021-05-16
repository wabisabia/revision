# Notation

## Matrices

Term|Notation
-|-
feature value|\\(x_{ij}\\), \\(i^{th}\\) sample \\(j^{th}\\) feature
feature vector/sample|\\(\mathbf{x}\_i=\begin{bmatrix}x_{i1}&\dots&x_{id}\end{bmatrix}\\), \\(d\\) = number of features
training samples|\\(\mathbf{X}=\begin{bmatrix}\mathbf{x}\_1\\\\\vdots\\\\\mathbf{x}\_n\end{bmatrix}=\begin{bmatrix}x_{11}&\dots&x_{1d}\\\\\vdots&\ddots&\vdots\\\\x_{n1}&\dots&x_{nd}\end{bmatrix}\\), \\(n\\) = number of samples
label|\\(y_i\\)
labels|\\(\mathbf{y}=\begin{bmatrix}y_1\\\\\vdots\\\\y_n\end{bmatrix}\\)
dataset|\\(\mathbf{X}\|\mathbf{y}=\left[\begin{array}{c\|c}\mathbf{x}\_1&y\_1\\\\\vdots&\vdots\\\\\mathbf{x}\_n&y\_n\end{array}\right]=\left[\begin{array}{ccc\|c}x_{11}&\dots&x_{1d}&y_1\\\\\vdots&\ddots&\vdots&\vdots\\\\x_{n1}&\dots&x_{nd}&y_n\end{array}\right]\\)

## Models

Term|Notation
-|-
prediction|\\(\hat{y}_i\\)
hyper-parameter|\\(\theta\in\Theta\\)

## Classification

Term|Notation
-|-
classes|\\(C_k\\), \\(k\in[1,K]\\)