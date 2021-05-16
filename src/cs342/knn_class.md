# \\(k\\)-Nearest Neighbour Classifiers

Classify \\(\mathbf{x}\\) with most common \\(C_k\\) of nearest \\(k\\) neighbours

Uses Lipschitz condition: if \\(\parallel x_i-x_j\parallel\\) is small, \\(y_i\\) and \\(y_j\\) are likely to be the same

No training, instead predictions are costly: \\(O(nd)\\)/prediction