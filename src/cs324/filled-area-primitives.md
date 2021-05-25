# Filled Area Primitives

## Two basic methods

- Colour points of scan lines that are inside the object
- Start from an inside point and colour neighbouring pixels until you reach the object boundary (object edge)

## General Knowledge

### Polygon types

- Convex polygon - All interior angles < \\( 180 \\) (triangles)

- Concave polygon - All interior angles > 180

- Self-intersecting polygon - Edges cross each other

### Bounding box

- Smallest rectangle that can enclose the whole triangle

- All points in bounding box put under insidedness test

### Ceiling box

- Contains the ceiling values of all x,y values in bounding box
