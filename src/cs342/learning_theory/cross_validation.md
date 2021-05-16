# Cross Validation

Tuning \\(\Theta\\) with \\(\mathbf{X}\_{validate}\\) and \\(E_{validate}\\) typically overfits less

But, it can overfit if applied several times: no longer unbiased

Optimisation bias decreases as \\(X_{validate}\\)'s size increases

Options:

- Grow \\(\mathbf{X}_{validate}\\)
- Use \\(\mathbf{X}_{validate}\\) conservatively

## \\(k\\)-Fold Cross Validation

Data-efficient method of estimating \\(E_{test}\\)

1. Partition \\(\mathbf{X}_{train}\\) into \\(k\\) equally sized datasets
1. Train on \\(k-1\\) of these, validate on the remaining set
1. Repeat \\(k\\) times

Leave-Out-One (LOO) validation: \\(k=n\\)