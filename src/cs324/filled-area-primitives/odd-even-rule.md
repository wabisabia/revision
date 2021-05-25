# Odd-Even Rule

- Line drawn from point to distant point outside the polygon (outside bounding box)
- Count edge intersections
  - If odd, point **inside**
  - if even, point **outside**
- Can simplify by translating the point to the origin and always draw the line towards the right
- If x-intercept of edge to the left of origin, no crossing
- If x-intercept to the right of origin, crossing, so Crossing number incremented

## x-Intercept

- \\( ax + c = 0 \\)
- \\( x = \frac{x_0y_1 - y_0x_1}{y_1 - y_0} \\)
