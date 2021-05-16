# Naïve Bayes

## Probability Model

Assuming each \\(x_{j}\\), \\(j\in[1,d]\\) is ***conditionally independent*** given label \\(y\\)

The probability that \\(\mathbf{x}\\) belongs in class \\(C_k\\) may be estimated

\\[
    \begin{align}
        p(y=C_k\mid \mathbf{x})&\propto p(y=C_k)p(\mathbf{x}\mid y=C_k)\\\\
        &\propto\prod\_{j=1}^d{p(y=C\_k)p(x\_j\mid y=C\_k)}\\\\
        &\propto p(y=C\_k)\prod_{j=1}^d{p(x\_j\mid y=C\_k)}
    \end{align}
\\]

## Classifier

Predict **most probable** class- *maximum a posteriori* (MAP) decision rule

\\[
    \hat{y}=\underset{k\in[1,K]}{\text{argmax}}\\,p(y=C_k)\prod_{j=1}^d{p(x_j\mid y=C_k)}
\\]

To calculate these values, training estimates

\\[
    \begin{align}
        p(y=C_k)&=\frac{\text{# occurrences of }y=C_k}{n}\\\\
        p(y=C_k,x_j=\text{value})&=\frac{\text{# occurrences of }y=C_k\land x_j=\text{value}}{n}\\\\
        p(x_j=\text{value}\mid y=C_k)&=\frac{p(y=C_k,x_j=\text{value})}{p(y=C_k)}
    \end{align}
\\]

## MAP Alternative

Cost of mistakes may differ

Instead, predict class that minimises

\\[
    \mathbb{E}[cost(\hat{y},\tilde{y})]
\\]