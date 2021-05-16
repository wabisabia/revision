# Entropy

Goal: maximise information gain \\(IG\\) at each split:

\\[ \underset{\text{feature, threshold}}{\text{argmax}}IG=\underset{\text{feature, threshold}}{\text{argmin}}\text{entropy} \\]

## Entropy

Measure of randomness or lack of order in data.

- Low entropy \\(\Rightarrow\\) predictable
- High entropy \\(\Rightarrow\\) random

When random variable \\( X \\) is categorical with \\( C \\) possible values

\\[ \text{entropy}=-\sum_{c=1}^C{p_c\log_2{p_c}} \\]

## Score Function

\\[
    \text{information gain}=\text{entropy}(y)-\frac{n_{yes}}{n}\text{entropy}(y_{yes})-\frac{n_{no}}{n}\text{entropy}(y_{no})
\\]