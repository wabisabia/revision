# Non-Zero Winding Number Rule

- Count number of edge intersections and also the direction of the crossing
  - If cross bottom -> top \\( \implies \\) increment count
  - If cross top -> bottom \\( \implies \\) decrement count
- Translate point to origin
- Draw the line towards the right

- Compute whether edge cross happens and the direction
  - Vector cross product
    - \\(e = v_1 - v_0\\)
    - \\( u \times e > 0 \implies R to L cross \implies count++\\)
    - \\( u \times e < 0 \implies L to R cross \implies count--\\)
  - Vector dot product
    - \\(e = v_1 - v_0\\)
    - \\( e^T \times u^{\perp} > 0 \implies R to L cross \implies count++\\)
    - \\( e^T \times u^{\perp} < 0 \implies L to R cross \implies count--\\)
