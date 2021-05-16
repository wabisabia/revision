# Error

## Training and Test Error

Supervised learning:

1. Partition dataset into a *training set* and *test set*
1. Train model on training set to ***minimise*** training error \\(E_{train}\\)
1. Test model on test set to ***ascertain*** test error \\(E_{test}\\)

Goal: minimise \\(E_{test}\\)

Test data ***cannot influence*** training

Overfitting/Optimisation Bias: low \\(E_{train}\\), high \\(E_{test}\\)

Underfitting: high \\(E_{train}\\)

## Approximation Error

How well \\(E_{train}\\) approximates \\(E_{test}\\)

\\[ E_{approx}=E_{test}-E_{train} \\]

## Validation Error

\\(E_{validate}\\) approximates \\(E_{test}\\) with validation set \\(\mathbf{X_{validate}}\subset \mathbf{X}\\)

*Unbiased* estimation of \\(E_{test}\\) if computed *once*

Assumes training data is [IID](iid.md)

Used in [cross validation](cross_validation.md)