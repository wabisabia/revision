# Scan Converting Polygons

## Scanline Algorithm

- Horizontal line sweeps from bottom of polygon to top
- Crossing number of pixels on the same line is the same
- Edge encounters flip inside/outside classification
- Data structures:
  - Edge list (EL)
    - Sorted data on edges for polygon
    - Entry
      - \\(y\_{max}\\) - upper y of edge - used for bucket sort of edges for every scanline
      - \\(x\_{min}\\) - lower x of edge - sorting of edges within bucket
      - 1/m - step in x for scanline
  - Active Edge list (AEL)
    - Sorted data of polygon edges intersecting the sweep/scan line
    - Sorted by x-intercept
    - Updated when scanline is moved up (remove edges no longer intersected, add new intersecting edges)
- Algorithm:
  - set y to smallest y in EL
  - Init AEL as empty
  - do until EL AND AEL empty
    - move edges from EL to AEL where \\(y_min = y\\)
    - remove edges from AEL where \\( y = y_max\\)
    - fill in pixels on scanline using coords from AEL
    - y++
    - Update x with new y
- \\( x\_{y+1} = x_y + \frac{1}{m}\\), where \\( \frac{1}{m} = \frac{x\_{max} - x\_{min}}{y\_{max} - y\_{min}}\\)
- Calculate new x-intercept for intersected edge

## Boundary / Flood Fill

- Start with some interior point
- Check if it's not boundary AND not already coloured
- Colour point
- Call yourself
