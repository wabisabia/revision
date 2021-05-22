# 2D Graphics Primitives

## Drawing 2D Graphics Primitives

- Lines

  - \\( y = mx +c\\) - m slope, c intercept
    - \\( m = \frac{\Delta y}{\Delta x} \\)
    - \\( c = y_i - \frac{\Delta y}{\Delta x}x_i\\)
  - Parametric form: \\( p(t) = e_0 + t(e_1 - e_0)\\)
    - t between 0 and 1
    - \\(x\_{max} = x_0 + t(x_1 - x_0)\\)
    - \\( y\_{max} = y_0 + t(y_1 - y_0)\\)
  - Digital Differential Analyser

    - \\( y(x) = mx + c \implies\\)

    \\( dy = y(x+dx) - y(x) = y'(x)dx \implies \\)

    \\( y(x+dx) = y(x) + y'(x)dx \\)

    dx = 1 and Replace y'(x) with m, \\(0 \leq m \leq 1 \\):

    \\( \implies y\_{k+1} = y_k + m \\)

- Circles
  - \\(x^2 + y^2 = r^2 \\)
- Ellipses
- Other curves
- Polygons
- Characters

## Scan Conversion

- Rasterisation
- Convolution between ideal math function and object the size and shape of a pixel
