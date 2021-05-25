# Three-half planes

- Triangle is intersection of three half-planes
- For any single plane:

  - \\( L(x,y) = ax + by + c \\)
  - \\( L(x,y) < 0 \implies \\) x,y point inside
  - \\( L(x,y) = 0 \implies \\) x,y point on half-plane
  - \\( L(x,y) > 0 \implies \\) x,y point outside

- Line equation:

  - \\( f(x) = x^T \hat{u} - \rho \\)
  - \\( \hat{u} \\) - unit vector perpendicular to \\( v_1 - v_0\\)
  - \\( v_1 - v_0\\) - points of intersection with half-planes
  - \\( \rho \\) - offset
  - \\( f(x) > 0 \\) outside
  - \\( f(x) = 0 \\) on
  - \\( f(x) < 0 \\) inside

- \\( f_1(x) = x(y_1 - y_0) + y(x_0 - x_1) + y_0x_1 - x_0y_1 \implies\\)

  - \\( a = (y_1 - y_0) \\)
  - \\( b = (x_0 - x_1) \\)
  - \\( c = y_0x_1 - x_0y_1 \\)
