# Liang-Barsky

Derived from Cyrus and Beck's (1975) algorithm for clipping against arbitrary polygon

Adapted for clipping rectangle with sides parallel to system coordinates

## Point Clipping Conditions

Written as

\begin{align}
x\_{min}&\leq x_A+t\Delta x\leq x\_{max}\\\\
y\_{min}&\leq y_A+t\Delta y\leq y\_{may}
\end{align}

Yielding 4 inequalities of the form \\(tp_k\leq q_k\\):

\begin{align}
p_1&=-\Delta x
\end{align}
