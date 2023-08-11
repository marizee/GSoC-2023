<p align="center">
    <img src="sagemath.png" height="200">
</p>

## Project overview

### About SageMath

### Subject description
Sage incorporates state-of-the-art libraries for exact linear algebra computations, such as matrix multiplication, reduced echelon form, linear system solving, when the coefficients are in an exact domain such as the integers or finite fields.

However, several aspects make the integration of these libraries not yet fully satisfactory. For example, working over a prime field with a prime below about 20 bits, the mere creation of a zero matrix in SageMath takes roughly as long as the call of the underlying fast reduced echelon form procedure (performed by LinBox / FFLAS-FFPACK in this case). Still about FFLAS-FFPACK: several available tools in this library are not offered through the Sage interface, constraining the user experience; for example, some pivoting strategies are not available, despite their usefulness in some situations e.g. when one is interested in the preservation of some rank profile properties. Finally, the integration of linear algebra implementations from Flint has been initiated, with a good amount of work already done, but is not fully finalized and has not been merged into Sage.

This project aims to make this kind of enhancements, which would lead to more efficient and more versatile finite field linear algebra operations in Sage.

## Contribution

**Link to the forked repository :** https://github.com/marizee/sage

### Updated the value of `MAX_MODULUS` of `Matrix_modn_dense_template` 

* (Merged) [PR #35752][max_mod_float] : Clarification on the `MAX_MODULUS` of float matrices modulo `n`.
* (Merged) [PR #35855][max_mod_double] : Extend `MAX_MODULUS` of `matrix_modn_dense_double.pyx`.

Linked issues :

* [Issue #35365][i_max_mod_float] : Misleading maximum `n` value in docstring of `matrix_modn_dense_float.pyx`.
* [Issue #35806][i_max_mod_double] : Extend `MAX_MODULUS` for `matrix_modn_dense_double.pyx` from 23 bits to 27 bits.

### Accelerated the zero matrix creation

* (Not merged) [PR #36068][mat_creation] : Speed-up matrix construction by ensuring MatrixArgs type MA_ENTRIES_ZERO.

Linked issues :

* [Issue #28432][i_mat_creation] : Speed-up constructor of Matrix_modn_dense_template.
* [Issue #35961][ii_mat_creation] : Accelerating the construction of matrices of type Matrix_modn_dense.


### Speeded-up the creation of submatrices of `Matrix_modn_dense_template` matrices

* (Not merged) [PR #36059][submatrices] : Speed up the creation of submatrices of Matrix_modn_dense_template matrices.


## What is left to do




[max_mod_float]: https://github.com/sagemath/sage/pull/35752
[max_mod_double]: https://github.com/sagemath/sage/pull/35855
[mat_creation]: https://github.com/sagemath/sage/pull/36068
[submatrices]:https://github.com/sagemath/sage/pull/36059

[i_max_mod_float]: https://github.com/sagemath/sage/issues/35365
[i_max_mod_double]: https://github.com/sagemath/sage/issues/35806
[i_mat_creation]: https://github.com/sagemath/sage/issues/28432
[ii_mat_creation]: https://github.com/sagemath/sage/issues/35961
