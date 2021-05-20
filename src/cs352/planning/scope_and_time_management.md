# Scope and Time Management

## Project Network Diagrams

Derived from dependency chart:

Task|Dependencies
-|-
A|-
B|-
C|A, B
D|B

Activity on Node:

<center><img src="pnd_activity_on_node.png"></center>

Activity on Edge:

<center><img src="pnd_activity_on_edge.png"></center>

## Critical Path Method

Critical path - Activity sequency from first to last. Delaying critical path activity extends project duration

Duration \\(D\\) - activity length

Earliest Start \\(ES\\) - Earliest time activity can start.

\\[
    ES=\underset{p\in pred(activity)}{argmax}\\, EF(p)
\\]

Earliest Finish \\(EF\\)

\\[
    EF=ES+D
\\]

Latest Finish \\(LF\\) - Latest time activity can finish.

\\[
    LF=\underset{p\in succ(activity)}{argmin}\\, LS(p)
\\]

Latest Start \\(LS\\):

\\[
    LS=LF-D
\\]

Total Float \\(TF\\) - Time task can be delayed without delaying project

\\[
    TF=LS-ES=LF-EF
\\]

### Algorithm

1. Construct PND
1. Forward pass calculates:
    - \\(ES\\)
    - \\(EF\\)
1. Backward pass calculates:
    - \\(LF\\)
    - \\(LS\\)
    - \\(TF\\)

## Program Evaluation and Review Technique (PERT)

- Probabilistic version of CPM that factors in ***uncertainty***
- Skeptical of time estimates
- Variation of CPM using ***three-point*** estimation
    - Shortest possible time (\\(a\\))
    - Most likely time (\\(m\\))
    - Longest possible time (\\(b\\))
- Either \\(\beta\\) distribution
    - \\(\mu=\frac{a+4m+b}{6}\\)
    - \\(var=\sigma^2=(\frac{b-a}{6})^2\\)
- Or triangular distribution
    - \\(\mu=\frac{a+b+m}{3}\\)
    - \\(var=\sigma^2=\frac{a^2+b^2+m^2-ab-am-bm}{18}\\)

<center><img src="pert-distribution.png"></center>

Add 5 extra columns to dependency chart:

Task|Dependencies|\\(a\\)|\\(m\\)|\\(b\\)|\\(\mu\\)|\\(\sigma\\)
-|-|-|-|-|-|-
A|-|2|5|8|5|1
B|A|1|2|9|3|\\(\frac{4}{3}\\)
C|A|0.25|0.5|3.75|1|\\(\frac{7}{12}\\)
D|B|1|1|7|2|1
E|B, C|1|2|9|3|\\(\frac{4}{3}\\)
F|D, E|1|3|11|4|\\(\frac{5}{3}\\)

Work out critical path as before:

<center><img src="pert-pnd.png"></center>

Expected project duration is sum of means along the critical path:

\\[
    E(\mu)=\sum_{a\in P_{critical}}{\mu(a)}=5+3+3+4=15
\\]

Expected project variance is sum of ***squares of*** \\(\sigma\\) along the critical path:

\\[
        E(var)=\sum_{a\in P_{critical}}{\sigma(a)^2}=1+\frac{16}{9}+\frac{16}{9}+\frac{25}{9}=\frac{66}{9}
\\]

So \\(\mu=15\\), \\(\sigma=\sqrt{\frac{66}{9}}=\frac{\sqrt{66}}{3}\approx2.7\\)

Or, *"The project will take 15 days \\(\pm\\) 2.7 days"*

PDF gives confidence level that project will be completed before a certain time

***But***:

- Assumes normally distributed
- Requires uncertainty estimation
- False sense of precision