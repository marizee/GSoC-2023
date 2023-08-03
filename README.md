
## Project overview

### Subject description
Sage incorporates state-of-the-art libraries for exact linear algebra computations, such as matrix multiplication, reduced echelon form, linear system solving, when the coefficients are in an exact domain such as the integers or finite fields.  
However, several aspects make the integration of these libraries not yet fully satisfactory. For example, working over a prime field with a prime below about 20 bits, the mere creation of a zero matrix in SageMath takes roughly as long as the call of the underlying fast reduced echelon form procedure (performed by LinBox / FFLAS-FFPACK in this case). Still about FFLAS-FFPACK: several available tools in this library are not offered through the Sage interface, constraining the user experience; for example, some pivoting strategies are not available, despite their usefulness in some situations e.g. when one is interested in the preservation of some rank profile properties. Finally, the integration of linear algebra implementations from Flint has been initiated, with a good amount of work already done, but is not fully finalized and has not been merged into Sage.  
This project aims to make this kind of enhancements, which would lead to more efficient and more versatile finite field linear algebra operations in Sage.

### Links to contributions

## ?

### MAX_MODULUS

### Zero matrix creation

### Identity matrix and diagonal matrices

### Submatrices
