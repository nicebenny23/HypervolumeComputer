# Convex Hypervolume Computer

A C++ program for computing the hypervolume of convex geometric objects in arbitrary dimensions.

## Overview

This project explores computational geometry and algorithms for discretizing and calculating the volume/hypervolume of convex shapes from their geometric representation.
## What It Does
Given a convex geometric object, the program can
## Optimal Meshing
The program converts it into a polyhedral mesh with both vertices and facets using the beneath beyond algorithm.
By using the support function we can find faces which would provide a great benefit to the mesh, ensuring the mesh is as small as it can be.
| Dimension | Input Size | Compute Time |Volume Ratio |
|---:|---:|---:|---:|
| 3D | 2,000 | 9.00s | 99.8% |
| 4D | 2,000 | 23.00s | 98% |
## Facet Meshing
the program can also generate Facets of the shape. 
## Volume computation:
Given all the faces of a Polyhedron, the program computed its Chebyshev Center.
The program is able to derive the average distance a ray has to travel from the Chebyshev Center, which can be converted into a volume measurement.
