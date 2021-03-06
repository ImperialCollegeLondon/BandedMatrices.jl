# BandedMatrices.jl
A Julia package for representing banded matrices

[![Build Status](https://travis-ci.org/JuliaMatrices/BandedMatrices.jl.svg?branch=master)](https://travis-ci.org/JuliaMatrices/BandedMatrices.jl)

[![](https://img.shields.io/badge/docs-stable-blue.svg)](https://JuliaMatrices.github.io/BandedMatrices.jl/stable)
[![](https://img.shields.io/badge/docs-latest-blue.svg)](https://JuliaMatrices.github.io/BandedMatrices.jl/latest)



This package supports representing banded matrices by only the entries on the
bands.  

One can create banded matrices of type `BandedMatrix` as follows:

```julia
BandedMatrix(Zeros(m,n), (l,u))    # creates a banded matrix of zeros, with l sub-diagonals and u super-diagonals
brand(m,n,l,u)     # creates a random banded matrix, with l sub-diagonals and u super-diagonals
BandedMatrix(Ones(m,n), (l,u))     # creates a banded matrix of ones, with l sub-diagonals and u super-diagonals
BandedMatrix(Eye(n), (l,u))        # creates a banded  n x n identity matrix, with l sub-diagonals and u super-diagonals
```

Specialized algebra routines are overriden, include `*` and `\`:

```julia
A = brand(10000,10000,4,3)  # creates a 10000 x 10000 matrix with 4 sub-diagonals
                            # and 3 super-diagonals
b = randn(10000)
A*b  #   Calls optimized matrix*vector routine
A*A  #   Calls optimized matrix*matrix routine
A\b  #   Calls optimized matrix\vector routine
```
