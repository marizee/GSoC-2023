<p align="center">
    <a href="https://summerofcode.withgoogle.com/">
        <img src="gsoc.svg">
    </a>
    <a href="https://www.sagemath.org/index.html">
        <img src="sagemath.png">
    </a>
</p>

## Project description

### Enhancements in linear algebra in SageMath

**Mentor** : M. Vincent NEIGER

SageMath incorporates state-of-the-art libraries for exact linear algebra computations, such as matrix multiplication, reduced echelon form, linear system solving, when the coefficients are in an exact domain such as the integers or finite fields.

However, several aspects make the integration of these libraries not yet fully satisfactory. For example, working over a prime field with a prime below about 20 bits, the mere creation of a zero matrix in SageMath takes roughly as long as the call of the underlying fast reduced echelon form procedure (performed by LinBox / FFLAS-FFPACK in this case). Still about FFLAS-FFPACK: several available tools in this library are not offered through the SageMath interface, constraining the user experience; for example, some pivoting strategies are not available, despite their usefulness in some situations e.g. when one is interested in the preservation of some rank profile properties. Finally, the integration of linear algebra implementations from Flint has been initiated, with a good amount of work already done, but is not fully finalized and has not been merged into SageMath.

This project aims to make this kind of enhancements, which would lead to more efficient and more versatile finite field linear algebra operations in SageMath.


## Contribution

**Link to the forked repository :** [https://github.com/marizee/sage](https://github.com/marizee/sage)



### Updated the value of `MAX_MODULUS` of `Matrix_modn_dense_template` matrices 

* (Merged) [PR #35752][max_mod_float] : Clarification on the `MAX_MODULUS` of float matrices modulo `n`.
* (Merged) [PR #35855][max_mod_double] : Extend `MAX_MODULUS` of `matrix_modn_dense_double.pyx`.

Related issues :

* [Issue #35365][i_max_mod_float] : Misleading maximum `n` value in docstring of `matrix_modn_dense_float.pyx`. (Closed)
* [Issue #35806][i_max_mod_double] : Extend `MAX_MODULUS` for `matrix_modn_dense_double.pyx` from 23 bits to 27 bits. (Closed)

### Accelerated the zero matrix creation

* (Merged) [PR #36068][mat_creation] : Speed-up matrix construction by ensuring MatrixArgs type MA_ENTRIES_ZERO. _submitted by my mentor_
* (Merged) [PR 36093][zero_mat] : Speed-up the creation of a zero matrix of type `Matrix_modn_dense_template`.

Related issues :

* [Issue #36065][i_scalar_creation] : Matrix creation from a scalar fails in some cases. (Closed)
* [Issue #28432][i_mat_creation] : Speed-up constructor of Matrix_modn_dense_template. (Closed)
* [Issue #35961][ii_mat_creation] : Accelerating the construction of matrices of type Matrix_modn_dense. (Closed)
* [Issue #36104][i_fail_input] : Matrix construction over prime field fails for some types of inputs. (Open)  
  _small bug detected during the study of zero matrix creation_


### Speeded-up the creation of submatrices of `Matrix_modn_dense_template` matrices

* (Merged) [PR #36059][submatrices] : Speed up the creation of submatrices of `Matrix_modn_dense_template` matrices.

## What is left to do

The matrix creation issue took longer than expected. Although we are satisfied with the amount of enhancements done this summer, there are remaining issues to be treated given the original project proposal.

* Handle the small bug in [Issue #36104][i_fail_input]
* Resolve the zero matrix copy issue .
* Incorporate additional FFLAS-FFPACK or Flint routines/functionalities into SageMath, such as pivoting strategies.
* Improve sparse matrices computations.


[max_mod_float]: https://github.com/sagemath/sage/pull/35752
[max_mod_double]: https://github.com/sagemath/sage/pull/35855
[mat_creation]: https://github.com/sagemath/sage/pull/36068
[zero_mat]: https://github.com/sagemath/sage/pull/36093
[submatrices]:https://github.com/sagemath/sage/pull/36059

[i_max_mod_float]: https://github.com/sagemath/sage/issues/35365
[i_max_mod_double]: https://github.com/sagemath/sage/issues/35806
[i_scalar_creation]: https://github.com/sagemath/sage/issues/36065
[i_mat_creation]: https://github.com/sagemath/sage/issues/28432
[ii_mat_creation]: https://github.com/sagemath/sage/issues/35961
[i_fail_input]: https://github.com/sagemath/sage/issues/36104
