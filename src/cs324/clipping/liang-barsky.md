\\[
\def\line#1{{\overset{{\small\longleftrightarrow}}{#1}}}
\def\lineseg#1{{\overline{#1}}}
\\]

# Liang-Barsky

Derived from [Cyrus and Beck's (1975)](https://en.wikipedia.org/wiki/Cyrus%E2%80%93Beck_algorithm) algorithm for clipping against arbitrary polygon

Adapted for clipping rectangle with sides parallel to system coordinates

## Point Clipping Conditions

Written as

\begin{align}
x\_{min}&\leq x_A+t\Delta x\leq x\_{max}\\\\
y\_{min}&\leq y_A+t\Delta y\leq y\_{max}
\end{align}

Yields 4 inequalities \\(tp_i\leq q_i\\) where

\begin{align}
p_0&=-\Delta x&q_0=x_A-x\_{min}\\\\
p_1&=\Delta x&q_1=x\_{max}-x_A\\\\
p_2&=-\Delta y&q_2=y_A-y\_{min}\\\\
p_3&=\Delta y&q_3=y\_{max}-y_A
\end{align}

| Variable  | Interpretation                                                                                                               |
| --------- | ---------------------------------------------------------------------------------------------------------------------------- |
| \\(p_i\\) | \\(x\\)/\\(y\\)-offset between \\(A\\) and \\(B\\)                                                                           |
| \\(q_i\\) | \\(x\\)/\\(y\\)-offset between \\(A\\) and any point on \\(\line{XY}\_i\\): the extension of clip edge \\(\lineseg{XY}\_i\\) |

Note:

- \\(p\_{2k}=-p\_{2k+1}\\), i.e.
  \begin{align}
  p_0&=-p_1\\\\
  p_2&=-p_3
  \end{align}
  So to check \\(p_i=0\\) just check \\(p_0=0\\) and \\(p_2=0\\)
- \\(x\_{min}\leq x\_{max}\\) and \\(y\_{min}\leq y\_{max}\\) so
  \begin{align}
  sign(q_0)&=-1\implies sign(q_1)=1\\\\
  sign(q_1)&=-1\implies sign(q_0)=1\\\\
  sign(q_2)&=-1\implies sign(q_3)=1\\\\
  sign(q_3)&=-1\implies sign(q_2)=1
  \end{align}

## Algorithm

- \\(p_i=0\land q_i<0\\): TRIVIAL <span style="color:red">REJECT</span>
  - \\(p_i=0\implies\line{AB}\parallel\line{XY}\_i\\)
  - \\(q_i<0\implies\line{AB}\\) "outside" \\(\line{XY}\\)
- \\(p_i\neq0\\), so \\(\line{AB}\\) intersects \\(\line{XY}\_i\\) at \\(r_i=\frac{q_i}{p_i}\\)
  - Compute two inner intersections with extended edges of clip box
    \begin{align}
    r&=max\\{r_i\mid\forall i\in[0,3]:p_i<0\\}\cup\\{0\\}\\\\
    s&=min\\{r_i\mid\forall i\in[0,3]:p_i>0\\}\cup\\{1\\}
    \end{align}
    - If \\(r>s\\), line is outside clip box so <span style="color:red">REJECT</span>
    - Otherwise, compute end-points from \\(r\\) and \\(s\\)
