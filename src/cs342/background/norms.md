# Norms

Measures of distance

## Norms on Residuals

Norms that act on a residual vector \\(\mathbf{r}=\parallel\mathbf{x}_i-\mathbf{x}_j\parallel\\)

Norm|Definition|Intuition
-|-|-
\\(L_0\\)|\\(\sum_{j=1}^d{\begin{cases}1&r_j\neq0\\\\0&r_j=0\end{cases}}\\)|# of non-zero elements
\\(L_1\\)|\\(\sum_{j=1}^d{\|r_j\|}\\)|Taxicab/Manhattan distance
\\(L_2\\)|\\(\sqrt{\sum_{j=1}^d{r_j^2}}\\)|Euclidean distance
\\(L_\infty\\)|\\(\max_{j\in[1,d]}{r_j}\\)|largest element
\\(L_p\\)|\\(\left(\sum_{j=1}^d{x_j^p}\right)^{\frac{1}{p}}\\)|
Weighted|\\(\sum_{j=1}^d{w_j\|r_j\|}\\)|weights features by relative importance

## Norms on Pairs of Feature Vectors

Norms that act on \\(\mathbf{x}_i\\) and \\(\mathbf{x}_j\\) directly

Norm|Definition|Intuition
-|-|-
Jaccard distance (really a ***similarity***)|\\(J(\mathbf{x}_i,\mathbf{x}_j)=\frac{\|\mathbf{x}_i\cap\mathbf{x}_j\|}{\|\mathbf{x}_i\cup\mathbf{x}_j\|}=\frac{\|\mathbf{x}_i\cap\mathbf{x}_j\|}{\|\mathbf{x}_i\|+\|\mathbf{x}_j\|-\|\mathbf{x}_i\cap\mathbf{x}_j\|}\\)|ratio of overlapping to distinct elements
Hamming distance|\\(HD(\mathbf{x}\_i,\mathbf{x}\_j)=\sum_{k=1}^d{\begin{cases}1&x_{ik}\neq x_{jk}\\\\0&x_{ik}=x_{jk}\end{cases}}\\)|# of elements that differ