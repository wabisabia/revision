# Cohen-Sutherland

Uses simplifying tests and simple description of region in which a point lies

Efficient for two cases:

- Large clipping rectangle for TRIVIAL <span style="color:#4cc73c">ACCEPT</span>s
- Small clipping rectangle for TRIVIAL <span style="color:red">REJECT</span>s

## Regions

4-bit **_outcodes_** \\(C=[b_3, b_2, b_1, b_0]\\) where

\\[
\begin{align}
b\_3&=y>y\_{max}\\\\
b\_2&=y<y\_{min}\\\\
b\_1&=x<x\_{min}\\\\
b\_0&=x>x\_{max}\\\\
\end{align}
\\]

Properties:

- Central region shares no bits with any other region
- Vertically or horizontally aligned regions share at least one bit

<center><img src="regions.png" width="300px"></center>

## Trivial Cases

For points \\(A\\) and \\(B\\)

| Outcome                                   | Condition                    | Explanation             |
| ----------------------------------------- | ---------------------------- | ----------------------- |
| <span style="color:#4cc73c">ACCEPT</span> | \\(C_A\lor C_B=[0000]\\)     | Both in central region  |
| <span style="color:red">REJECT</span>     | \\(C_A\land C_B\neq[0000]\\) | Both in aligned regions |

e.g. for the example above:

<center><img src="trivial-regions.png" width="300px"></center>

## Non-Trivial Cases

Not trivial \\(\land\\,b_i=1\\) \\(\implies\\) intersects relevant clip box edge

1. Until trivial test with \\(C_A\\) and \\(C_B\\) passes
1. Scan outcodes in parallel from MSB until bit \\(b_i=1,\\,b_i\in C_P\\)
1. Compute intersection \\(P'\\) with relevant edge
   - Compute new point
     \\[
     P'=\begin{cases}(x',y\_{max/min})&i=3/2\\\\(x\_{min/max},y')&i=1/0\end{cases}
     \\]
     where
     \begin{align}
     x'&=x_P+t(x\_{P\_{other}}-x_P)&=x_P+(\frac{y\_{max/min}-y_P}{y\_{P\_{other}}-y_P})(x\_{P\_{other}}-x_P)\\\\
     y'&=y_P+t(y\_{P\_{other}}-y_P)&=y_P+(\frac{x\_{min/max}-x_P}{x\_{P\_{other}}-y_P})(y\_{P\_{other}}-y_P)
     \end{align}
1. Compute \\(P'\\)'s outcode
1. Do trivial test with \\(P'\\) and \\(P\_{other}\\)
