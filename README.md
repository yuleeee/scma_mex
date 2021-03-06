# Log-MPA decoder for Sparse Code Multiple Access (SCMA)

The mex realization of Log-MPA decoder for [Sparse Code Multiple Access (SCMA) scheme demonstration](https://github.com/klimentyev/scma)

## Objectives

To provide **C** implementation of **Log-MPA** and **Max-Log-MPA** (branch `max_log_mpa`, 6x times faster, but needs additional testing) decoders.

## Description

The main features of project:

* C MEX API R2018a with the [interleaved complex API](https://www.mathworks.com/help/matlab/matlab_external/matlab-support-for-interleaved-complex.html)

* Parameters of SCMA system in `/src/scma_parameters.h`, the size of arrays is defined there (not dynamically).

* Input arrays would be a complex (even coefficients for AWGN channel (complex type with zero imaginary part)).

* `Niter` var in MATLAB should be `int32` type.

* The implementation in 1.5x faster than MATLAB 2018a mex code generation (GCC 7.3, Intel Core i7-4790K) for single core mode.

* Support GCC, Clang, Intel Compiler. Intel Compiler 2018 in 2.75x faster than GCC 7.3 for single core mode.

* OpenMP for SCMA signals loop (outer loop)

* `intel_compiler_opt` branch with additional oprimization for Intel Compiler (the fatest results)

## Build

* Edit `MATLAB_DIR` in Makefile.

* Run `make`.

## Future work

Improve of performance.

## Contact

Vyacheslav P. Klimentyev, vklimentyev@gmail.com

## Contributions

Thanks to Alexander B. Sergienko, PhD, Prof., Saint Petersburg Electrotechnical University "LETI", Saint Petersburg, Russia.
