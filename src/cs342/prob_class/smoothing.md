# Additive Smoothing

## Unseen Values

If a \\(C_k\\) and value of \\(x_j\\) do not occur in \\(\mathbf{X}\\), probability estimate of

\\[
    p(x_j=\text{value}\mid y=C_k)=\frac{\text{# occurrences of }y=C_k\land x_j=\text{value}}{\text{# occurrences of }y=C_k}
\\]

will be 0

Naïve Bayes will always predict 0 probability for all classes on unseen values of \\(x_j\\)

## Lidstone Smoothing

Add implicit pseudo-count

\\[
    p(x_j=\text{value}\mid y=C_k)=\frac{(\text{# occurrences of }y=C_k\land x_j=\text{value})+\alpha}{(\text{# occurrences of }y=C_k)+\alpha d}
\\]

Laplace smoothing: \\(\alpha=1\\)