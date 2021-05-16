# Greedy Recursive Splitting

Greedy algorithm for recursively generating a decision tree for a dataset

1. For every possible feature-threshold pair
    1. Score the split it creates
    1. Maintain the maximum scoring pair
1. Split data with the decision stump that uses the maximum pair
1. Repeat