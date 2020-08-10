# godot-linalg GDNative Plugin
### *Naive implementation in C++ using godot-cpp*

*For information on how to build the GDNative plugin, check HOW_TO_BUILD.md.*

All methods exchange `PoolRealArrays` or `Dictionaries` and operate on `real_t` (synonymous with `float` in most cases).
Conditional branches are avoided where possible.
The names are coded to reflect the type of data used: s = scalar, v = vector and m = matrix. So

    dot_mv

is a dot product between matrix and vector (in that order).
In-place function variants do not instantiate new PoolRealArrays (but may resize them).

Matrices are represented as Dictionaries of `PoolRealArray`, `real_t`, `real_t` representing a two-dimensional matrix in one-dimensional row-major order and its dimensions, m and n.

This is *NOT* a replacement for proper BLAS libraries and routines. Do not use this in production code.
There is no sparse matrix implementation, and none of these functions work on parallel or use special vector instructions.
Consider supporting the author in writing a wrapper for your favourite Linear Algebra library!