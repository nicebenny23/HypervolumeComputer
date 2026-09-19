# Convex Hypervolume Computer

A C++ program for computing the hypervolume of convex geometric objects in arbitrary dimensions.

## Overview

This project explores computational geometry and algorithms for discretizing and calculating the volume/hypervolume of convex shapes from their geometric representation.
## What It Does
### Given a convex geometric object, described by a support function, the program can:

Convert it into a polyhedral mesh with vertices and facets using the beneath-beyond algorithm.

Generate facets of the shape.  

Compute the volume/hypervolume of the resulting polyhedron.
  
## Optimal Meshing
The program converts the support function into a polyhedral mesh with both vertices and facets, using the beneath beyond algorithm.
By using the support function we can find faces which would provide a great benefit to the mesh, ensuring the mesh is as small as it can be.
### Sphere benchmarks
| Dimension | Input Size | Compute Time |Volume Ratio |
|---:|---:|---:|---:|
| 3D | 2,000 | 9.00s | 99.8% |
| 4D | 2,000 | 23.00s | 98% |
## Facet Meshing
the program can also generate Facets of the shape without optimizing for size
### Sphere benchmarks
| Dimension | Input Size | Compute Time |Volume Ratio |
|---:|---:|---:|---:|
| 3D | 2,000 | 3.7s | 99.5% |
| 4D | 2,000 | 4.0s | 94% |

Volume Ratio: the ratio of a spheres volume to the volume of the generated mesh.

These benchmarks demonstrate a tradeoff between computation time and geometric accuracy. The optimal meshing approach takes longer but produces a closer approximation of the original sphere, while direct facet meshing is substantially faster with a lower volume ratio.
## Volume computation:
Given all the faces of a Polyhedron, the program computes its Chebyshev Center.
The implementation then derives the average distance traveled by rays originating from the Chebyshev center and uses this geometric information to calculate a volume measurement.


## Architecture
The project is implemented in C++ with a focus on generic geometry algorithms and numerical computation.

## Floating-Point Type
By being fully generic based on the float type, the program can strategically use precise floats during the least numerically stable parts of the process whilst maintaining performance elsewhere.

## Goals
The primary goal of the project is to explore computational geometry through direct implementation of the underlying algorithms.
The current implementation is experimental and prioritizes exploring the algorithms and their numerical behavior rather than being a fully optimized or production-ready geometry library.
