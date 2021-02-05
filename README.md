# ParallelMatrix

The aim of this project is to implement various optimized algorithm for matrix inversion and multiplication, using the C language and the openMP library.
Simple analytical algorithms for multiplication or inversion (as the row-column product or the inversion using the determinant) are very expensive in terms of memory
and time. This fact is critical when the dimensions of the matrices start to growing. Even with few elements (100x100 matrix and less for the case of the inversion)
a simple C program that implements these simple algortihm risks to be stucked.


